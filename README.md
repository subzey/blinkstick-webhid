# WebHID BlinkStick Demo

[Live demo](https://subzey.github.io/blinkstick-webhid/)

How to control a [BlinkStick](https://www.blinkstick.com/) with [WebHID](https://wicg.github.io/webhid/).

This is **not** an official API reference. But should be enough for you to get started.

This is not a ready to use library. But the API is not too complicated and you could use it without any libraries.

## I doesn't work on Linux!

You have to grant a reading access for the device. Please see https://github.com/arvydas/blinkstick-node#permission-problems

## Unofficial Feature Reports Table

### sendFeatureReport()

|   | description                     | buffer length (bytes)                                    |
|---|---------------------------------|----------------------------------------------------------|
| 1 | Set color of the 1st pixel      | 3: `R`, `G`, `B`                                         |
| 2 | ? _(writes some data)_          | 32                                                       |
| 3 | ? _(writes some data)_          | 32                                                       |
| 4 | Set mode for BlinkStick Pro     | 1: `mode`                                                |
| 5 | Set color of 1 arbitrary pixel  | 5: `channel`, `index`, `R`, `G`, `B`                     |
| 6 | Set colors of 8 pixels at once  | 1 + 8 * 3:  `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 7 | Set colors of 16 pixels at once | 1 + 16 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 8 | Set colors of 32 pixels at once | 1 + 32 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 9 | Set colors of 64 pixels at once | 1 + 64 * 3: `channel`, `G`, `R`, `B`, `G`, `R`, `B`, ... |

### receiveFeatureReport()

|   | description                       | buffer length (bytes)                                   |
|---|-----------------------------------|---------------------------------------------------------|
| 1 | Get color of the 1st pixel        | 4: `1`, `R`, `G`, `B`                                   |
| 2 | ? _(reads some data back)_        | 34                                                      |
| 3 | ? _(reads some data back)_        | 34                                                      |
| 4 | Get mode for BlinkStick Pro       | 2: `4`, `mode`                                          |
| 5 | Get color of the 1st pixel        | 5: `5`, `0`, `0`, `R`, `G`, `B`                         |
| 6 | Get colors of the first 8 pixels  | 2 + 8 * 3:  `6`, `0`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 7 | Get colors of the first 16 pixels | 2 + 16 * 3: `7`, `0`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 8 | Get colors of the first 32 pixels | 2 + 32 * 3: `8`, `0`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
| 9 | Get colors of the first 64 pixels | 2 + 64 * 3: `9`, `0`, `G`, `R`, `B`, `G`, `R`, `B`, ... |
