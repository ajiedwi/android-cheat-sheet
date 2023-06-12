# Activity State Changes

Different events, some user-triggered and some system-triggered, can cause an `Activity` to transition from one state to another.

## Configuration Changes

The most prominent case for triggering state transition is the changes between portrait and landscape orientations. In this case, the activity is destroyed and recreated again that triggers these following callbacks when destroyed :

1. `onPause()`
2. `onStop()`
3. `onDestroy()`

And when recreating, will triggers these following callbacks again :

1. `onCreate()`
2. `onStart()`
3. `onResume()`

Previous activity's UI state will be destroyed. To save and reapply it to the new orientation, we can combine `ViewModel` instances, `savedInstanceState` method, or persistent local storage depends on the complexity of your UI data, your app use cases and also please consider the speed and memory usage when retrieve the data.

## Handle multi-window cases

When an app enters multi-window mode, available in Android 7.0 (API level 24) and higher, the system notifies the running activity of a configuration change, thus going through the lifecycle transitions described previously.

In multi-window mode, althought there are two apps that are visible to the user, only the one the user is interacting with is in the foreground and has focus. That activity is in the `RESUMED` state, while the app in the other window is in the `PAUSED` state.

When the user switches from app A to app B, the system calls `onPause()` on app A and `onResume()` on app B and vice-versa.

## Activity or dialog appears in foreground

If a new activity or dialog appears in the foreground, taking focus and partially covering the activity in progress, the covered activity loses focus and enters the `PAUSED` state and called `onPause()`. After the new activity or dialog closed and the covered activity returns to the foreground, the system calls `onResume()`.

If a new activity or dialog appears in the foreground, taking focus and completely covering the activity in progress, the covered activity loses focus and enters the `STOPPED` state. The system rapidly calls `onPause()` and `onStop()`. When the same instance of the covered activity return to the foreground, the system rapidly calls `onRestart()`, `onStart()` and `onResume()`.

## User taps or gestures Back

If an activity is in the foreground and the user tap or gestires back, the activity transitions throught the `onPause()`, `onStop()` and `onDestroy()` callbacks. The activity is destroyed and removed from the back stack.

## System kills app process

If an app is in the background and the system needs to free up memory for a foreground app, the system can kill the background app. When the system kills an app, there is no guarantee that `onDestroy()` is called in the app. Thus, we should prepare this by add our methods to save anyting we need on the `onPause()` callback.