adb_trace
=========

Android Debug Bridge + Chrome Tracing

## Compatible versions of Android Chrome ##

* 25 (stable)
* 27 (dev)

## Prerequisites ##

1. Ensure that the Android SDK is installed and that `adb` is in your path
    * http://developer.android.com/sdk/index.html
1. Ensure that your Android device is connected and USB debugging is enabled
    * http://developer.android.com/tools/device.html
1. Ensure that USB debugging is enabled in Chrome
    * https://developers.google.com/chrome-developer-tools/docs/remote-debugging

## Grabbing a capture from a stable Chrome build ##

```
$ python ./adb_trace.py
['SurfaceView', '16954612']
Refresh rate auto-guessed to be 58.981002.
Press enter to stop profiling.

Pulling chrome-profile-results-2013-03-19-014011 to ./chrome.json
```

## Grabbing a capture from a developer Chrome build ##

```
$ python ./adb_trace.py --browser dev
['SurfaceView', '16954612']
Refresh rate auto-guessed to be 58.981002.
Press enter to stop profiling.

Pulling chrome-profile-results-2013-03-19-014011 to ./chrome.json

```

## Viewing a capture ##

On the computer your Android is connected to:

1. Navigate to `about:tracing`
1. Click the *Load* button
1. Select `chrome.json` that was copied to your PC.

## Command Line Options ##

* `--refresh-rate`: The display refresh rate in Hz.
* `--url`: The url to navigate to before capturing the trace. 
* `--browser`: The browser channel: stable, beta, dev, or build.
    * `stable`: The official build of Chrome
    * `beta`: The beta build of Chrome
    * `dev`: The developer/canary build of Chrome
    * `build`: Compiled Chrome yourself? This one is for you.
* `--view`: Runs the `trace-event-viewer` command upon completion.
