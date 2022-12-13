## Introduction

Let's investigate persistent variables for the Arduino and how to use them, and then see how we can do so in WLED.


Normally, for a given Arduino sketch you can define variables as follows:

```
  uint8_t var1 = 5;                 // A persistent global variable that is defined once.

  void setup() {
    Serial.begin(115200);
  }

  void loop() {
    routine1();
  }

  void routine1() {
    uint8_t var2;                   // A non-persistent local variable.
    static uint8_t var3;            // A persistent local variable.

    Serial.print(var1); Serial.print("\t"); Serial.print(var2); Serial.print("\t"); Serial.println(var3);

    var1 = 7;
    var2 = 10;
    var3 = 25;

    delay(1000);
  }
```


The first time you run through the loop, we'll see the following, where only var1 has been assigned a non-zero value:

```
  5    0     0
```

At the end of the first loop, all the variables were assigned values. The second time through the loop, var1 was already changed to 7 in the first loop, while var2 is non-persistent and has yet to have a value assigned in this loop. The variable var3 is a 'persistent' local variable, with a value assigned in the first pass of the loop. Output will be:

```
  7    0    25
```

So, we have global and local variables, as well as persistent and non-persistent ones. Local variables require the 'static' keyword in order for them to keep their values (or be persistent) between function calls, while ALL global variables are persistent.


## Enter WLED . . . 

Although you CAN use the static keyword in a WLED animation to define a persistent variable, that variable will have the same value for ALL of the segments, and may not result in the desired properties. As a result, you may need to define a persistent variable unique to each SEGMENT.

WLED has a SEGMENT runtime structure that supports persistency. The only problem is that it has a limited number of pre-defined variables for generic use by animations (in FX.cpp). The readily available variables (as defined in FX.h) are:

```
uint16_t SEGENV.aux0;               // Available for your routine.
uint16_t SEGENV.aux1                // Available for your routine.
byte* SEGENV.data;                  // Available for your routine.
```

SEGENV.aux0 and SEGENV.aux1 are both unsigned 16 bit values, which you can use as persistent variables in your routines and will be unique for each SEGMENT. The question is, what if you need:

* A floating point or long variable?
* An array?
* A structure?

At that point, you'll need to make use of that *byte SEGENV.data pointer and allocate memory for it and then redefine how it's used. Let's examine some methods to do so and review some of the animations in FX.cpp to do so. WLED has a method called SEGENT.allocateData() which allocates memory for your animation. Here's some examples of how to use that.

## Basic Memory Allocation

In its simplest form, the routine mode_dynamic() just performs a basic request to allocate space for the length of a given SEGMENT with:

`  if (!SEGENV.allocateData(SEGLEN)) return mode_static();           // If it fails, WLED runs mode_static().

It doesn't make use of additional variables and is probably a good idea to implement on other animations, especially in a limited environment such as the ESP01 and with a considerable number of LED's.

## An Array

Next up is mode_multi_comet(), which reserves space for 8 uint16_t values for an array of comets.

```
  if (!SEGENV.allocateData(sizeof(uint16_t) * 8)) return mode_static(); //Allocates based on the size of 8 uint16_t variables

  uint16_t* comets = reinterpret_cast<uint16_t*>(SEGENV.data);          // It then redefined that byte* pointer to uint16_t comets[16].

  Now you can use things like:

  for (int i=0; i<8; i++) {
    comets[i] = 65535;          // Or other uint16_t value.
  }
```

## A Structure

Finally, we'll look into ripple_base(), which allocates persistent memory for a 'Ripple' structure. First off, we define the structure externally to the animation and call it 'ripple'.

```
  typedef struct Ripple {
    int8_t state;
    uint8_t color;
    uint16_t pos;
  } ripple;
```

From within the ripple_base() routine, we determine the number of ripples we want to support for each segment. In this case, we'll say:

` uint16_t maxRipples = 1 + (SEGLEN >> 2);

Next, we determine how much memory we need, where 'sizeof' returns number of bytes occupied by a variable of a given type.

 `  uint16_t dataSize = sizeof(ripple) * maxRipples;

Next, we allocate the memory, and then re-define it as our structure:
```
  if (!SEGENV.allocateData(dataSize)) return mode_static();
  Ripple* ripples = reinterpret_cast<Ripple*>(SEGENV.data);
```

Now, we can use our structure, up to maxRipples-1:

```
  for (uint16_t i = 0; i < maxRipples; i++) {
    ripples[i].pos   = ???;  // uint16_t
    ripples[i].state = ???;  // int8_t
    ripples[i].color = ???;  // uint8_t
  }
```

## A Floating Point Variable

As an exercise, let's just allocate a single floating point variable:

```
  if (!SEGENV.allocateData(sizeof(float))) return mode_static();
  float* expAdj = reinterpret_cast<float*>(SEGENV.data);          // We then redefine that byte* pointer to a float.
```

We should now be able to use the persistent floating point variable 'expAdj' with our routine and it should work with ALL segments indepently of each other.

```
  expAdj = 1.2345;
```


