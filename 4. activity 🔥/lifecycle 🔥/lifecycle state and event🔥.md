# Lifecycle Event and State

![Lifecycle Event and State Flow](https://developer.android.com/static/images/topic/libraries/architecture/lifecycle-states.svg)

Lifecycle State is a state which are an activity running on. While Lifecycle Event is the process happened between state that an activity invoke.

For example :

First of all, an activity is stated as `Lifecycle.State.INITIALIZED`, and then `Lifecycle.Event.ON_CREATE` is invoked (on activity, is called `onCreate()`) and then the activity is running at `Lifecycle.State.CREATED`. And so on.

## Lifecycle State

There are 5 Lifecycle States :

1. `Lifecycle.State.INITIALIZED` (initial state)

    Initialized state for an activity. This is the state when it's constructed, but not invoked `onCreate()` yet.

2. `Lifecycle.State.CREATED`

    Created state for an activity. This state reached between these two cases :
    - **after** `onCreate()` invoked.
    - **before** `onStop()` invoked.

3. `Lifecycle.State.STARTED`

    Started state for an activity. This state reached between these two cases :
    - **after** `onStart()` invoked.
    - **before** `onPause()` invoked.

4. `Lifecycle.State.RESUMED`

    Resumed state for an activity. This state reached **after** `onResume()` invoked.

5. `Lifecycle.State.DESTROYED` (dead state)

    Destroyed state for an activity. This state reached **right before** `onDestroy()` invoked. After an activity reached this state, it won't dispatch any more events.

## Lifecycle Event

There are 7 Lifecycle Events :

1. `Lifecycle.Event.ON_CREATE`

    Called when the activity moving from `Lifecycle.State.INITIALIZED` to `Lifecycle.State.CREATED`.

2. `Lifecycle.Event.ONSTART`

    Called when the activity moving from `Lifecycle.State.CREATED` to `Lifecycle.State.STARTED`.

3. `Lifecycle.Event.ON_RESUME`

    Called when the activity moving from `Lifecycle.State.STARTED` to `Lifecycle.State.RESUMED` .

4. `Lifecycle.Event.ON_PAUSE`

    Called when the activity moving from `Lifecycle.State.RESUMED` back to `Lifecycle.State.STARTED`.

5. `Lifecycle.Event.ON_STOP`

    Called when the activity moving from `Lifecycle.State.STARTED` back to `Lifecycle.State.CREATED`.

6. `Lifecycle.Event.ON_DESTROY`

    Called when the activity moving from `Lifecycle.State.CREATED` back to `Lifecycle.State.DESTROYED`.

7. `Lifecycle.Event.ON_ANY`

    Called every the activity state is moved from any state to any other state.

We can utilize `Lifecycle.Event` and `Lifecycle.State` to create `Lifecycle-aware Component`. For the example of that component, visit this [repository](https://github.com/ajiedwi/lifecycle-aware-component).