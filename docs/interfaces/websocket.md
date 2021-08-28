---
title: WebSocket
hide:
  # - navigation
  # - toc
---

!!! info "Version Info"
    Since WLED 0.10.2, a WebSocket server is enabled by default and can be used to access a subset of the [JSON API](/interfaces/json-api).

The server is available at the `/ws` endpoint, you can access it like `ws://[WLED-IP]/ws`.

You may send any JSON state update to the socket.
On change of the lighting state, the server will send a JSON object containing the state and info objects (this is equivalent to HTTP GET `/json/si`) to all connected clients. This object will also be sent to a client upon connecting.

You can also request a live stream of the LED values (e.g. the "Peek" feature of WLED-UI) by sending `{"lv":true}` to the websocket. The returned format is the same as for `/json/live`. Only one client can receive this at a time, if a new client requests it the stream will stop for the previous client (but the websocket will stay connected).

There can be a maximum of 4 clients connected at a time. If a fifth client connects, a different client will be disconnected. On ESP8266, it is recommended to have no more than 2 clients connected simultaneously.
