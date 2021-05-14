# WebHID BlinkStick Demo

[Live demo](https://subzey.github.io/blinkstick-webhid/)

How to control a [BlinkStick](https://www.blinkstick.com/) with [WebHID](https://wicg.github.io/webhid/).

This is **not** an official API reference. But should be enough for you to get started.

This is not a ready to use library. But the API is not too complicated and you could use it without any libraries.

## Unofficial Feature Reports Table

|   | sendFeatureReport               | receiveFeatureReport       | report size (bytes)                                      |
|---|---------------------------------|----------------------------|----------------------------------------------------------|
| 1 | Set color of the 1st pixel      | Get color of the 1st pixel | 3: `R`, `G`, `B`                                         |
| 2 | ?                               | ?                          |                                                          |
| 3 | ?                               | ?                          |                                                          |
| 4 | ?                               | ?                          |                                                          |
| 5 | Set color of 1 arbitrary pixel  | ?                          | 5: `channel`, `index`, `R`, `G`, `B`                     |
| 6 | Set colors of 8 pixels at once  | ?                          | 1 + 8 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ...  |
| 7 | Set colors of 16 pixels at once | ?                          | 1 + 16 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 8 | Set colors of 32 pixels at once | ?                          | 1 + 32 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 9 | Set colors of 64 pixels at once | ?                          | 1 + 64 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
