
### Milli5 Arduino CoAP Server

### Changes

#### Version 1.4.1
- Released on Dec 14, 2018.
- Added support for the Adafruit Metro M0 Express board.
This board replaces the Arduino M0 Pro board previously shipped with the HDKs.
Please note that all changes are backward compatible.
That is, mshield 1.4.1 will support both boards.
- Significant code cleanups. Many minor bugs were fixed.
- Fixed several memory leaks.
- Cleaned up and added comments to the code developers look at most.
- The code that supports the reference sensor (the DHT11 temperature sensor) has been significantly improved and commented.
It will be much easier to identify what needs to be changed to add a new sensor.
- Added CBOR encoding library to the code base.
- Added the option to CBOR encode the temperature sensor payloads. See the file temp_sensor.h for details.
This allows for supporting developers who need to work with the upcoming "bubble up" capability.
- Added the ability for logging to be picked up after a serial monitor is closed and then re-opened at a later time.
- Fixed issues around intermittent observe notification generation
- Updated the sensor templates.
- Added ability to turn off CBOR encoding.
- Added a define to set the observation frequency (making it easy).

##### Usage Notes
To turn off CBOR encoding in the temp sensor, locate the TEMP_CBOR_PAYLOAD define located in temp_sensor.h and set it to 0. The default is 1 (CBOR on).
 
```
#define TEMP_CBOR_PAYLOAD    1
#define TEMP_CBOR_PAYLOAD    0
```
 
To set the observation frequency, locate the OBSERVATION_FREQUENCY define located in coapsensorobs.h.
The value is the number of seconds between observation notifications. The default is 60 seconds.
 
```
#define OBSERVATION_FREQUENCY  60            // 1m
#define OBSERVATION_FREQUENCY  3600          // 60m
```
