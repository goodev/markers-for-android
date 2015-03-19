# Introduction #

Markers is compatible with Android API level 5 (Eclair) and greater. Most Android devices released since Eclair have capacitive touchscreens that report multiple touches and some basic size/pressure data, encoded in the [MotionEvent](http://developer.android.com/reference/android/view/MotionEvent.html) data structure for apps like Markers to use.

## Devices without pressure/size touch support ##

There are a few devices that do not report pressure/size information, however; it's unclear whether this is a function of the hardware or its drivers. Devices known to be pressure-insensitive:

  * Samsung Galaxy Tab 10.1
  * Amazon Kindle Fire (unconfirmed?)

#### Weak (but usable!) pressure support ####

These devices report pressure and/or size information, but the range of reported values is very small. The trick is to scribble for at least a couple of minutes so that Markers has enough time to observe the actual range of these pressure values and recalibrate itself automatically.

  * Motorola Droid X
  * Samsung Galaxy S III

#### Unusable pressure support ####

These devices report some data but it's truly unusable for one reason or another, to the point where Markers cannot correct for it with auto-calibration.

  * ASUS Transformer Pad TF300T (reports only 2 or 3 distinct pressure values, resulting in unpredictably blobby lines)

## Devices with “duotouch” support ##

Many early Android devices support some multitouch gestures (like "pinch") without accurately capturing multiple independent finger positions. On these devices, touching the display with two fingers will generate unpredictable results, such as X/Y coordinates being swapped between the two touches. (More information [here](http://developer.android.com/reference/android/content/pm/PackageManager.html#FEATURE_FAKETOUCH_MULTITOUCH_DISTINCT).)

  * Motorola Droid/Milestone
  * HTC Nexus One

## Other device notes ##

  * Some users have reported that the Nexus 7 occasionally reports high pressure values briefly, causing very broad “drips” along an otherwise uniform thin line. While I'd like to say that this is some sort of highly realistic leaky-fountain-pen simulation, it does seem that this is a problem with that device. Workaround: press the "undo" arrow and re-draw the stroke.