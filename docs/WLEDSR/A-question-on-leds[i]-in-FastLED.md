In order to be able to use leds[i] in WLED, we add the following global variable:

```
uint32_t ledData[MAX_LEDS];                 // See const.h for a value of 1500.
```

In many routines, we are adding the following code so that we don't have lossy data when copying led information from one element to the next:

```
  CRGB *leds = (CRGB*) ledData;

  // leds[i] code in here

  setPixels(leds);
  return FRAMETIME;
```


This works with SEGMENTS in that two different animations don't clash. The questions I have are:

* Am I lucky that they don't clash, in that maybe one routine just overwrites the other in the same memory space?
* Or are we creating a new array of [MAX_LEDS] for each segment.

If the latter, would that not be very inefficient, and if inefficient, would it not make more sense to use:

```
 if (!SEGENV.allocateData(sizeof(CRGB)*SEGLEN)) return mode_static(); //Allocates based on the size of a CRGB
  CRGB* leds = reinterpret_cast<CRGB*>(SEGENV.data);

  // leds[i] code in here

  setPixels(leds);
  return FRAMETIME;
```

That being said, an associate with embedded system support says that dynamic memory allocation is NOT a good thing to perform on embedded systems.

Thoughts?

In the meantime, and I quote: "When allocating memory the danger is always that that memory isn't deallocated properly, and thus leaks memory. Running out of RAM happens very fast on embedded devices that's why it's discouraged."