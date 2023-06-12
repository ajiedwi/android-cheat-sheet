# Tasks and the back stack

A *task* is a collection of activities that users interact with when trying to do something in your app. These activities are arranged in a stack called the back stack in the order in which each activity is opened.

For example, an email app might have one activity to show a list of new messages. When the user selects a message, a new activity opens to view that message. This new activity is added to the back stack. Then, when the user taps or gestures Back, that new activity finishes and is popped off the stack.

## Lifecycle of a task and its back stack

When user open app from the Home menu, that apps task comes to the foreground. If there is no task exists for the app before, then a new task is created and the *Main Activity* become the root activity in the stack. When user start a new activity from *Main Activity*, the new activity will pushed on the top of the stack and take focus. The previous activity remains in the stack but is stopped. 

When an activity is stopped, the system retains the current state of its user interface. When the user performs the back action, the current activity is popped from the top of the stack and destroyed. The previous activity resumes, and the previous state of its UI is restored.

Activities in the stack are never rearranged, only pushed onto or popped from the stack as they are started by the current activity and dismissed by the user through the Back button or gesture. Therefore, the back stack operates as a last in, first out object structure. Figure below shows a timeline with activities being pushed onto and popped from a back stack.

![Figure 1](https://developer.android.com/static/images/fundamentals/diagram_backstack.png)

## Back tap behavior for root launcher activities

**System behavior on Android 11 and lower**

The system finishes the activity

**System behavior on Android 12 and higher**

The system moves the activity and its task to the background instead of finishing the activity. This behavior matches the default system behavior when navigating out of an app using the Home button or gesture. In most cases, this behavioe means that users can more quickly resume your app from a warm state, instead of having to completely restart the app from a cold state.

## Multiple activity instances

An activity can be instantiated twice or more in a tasks. If you start it repeatedly. This happen because the back stack are never rearranged. So the old stack of the same activity will remain while the system pushed another stack of it.

![Multiple instance of activity](https://developer.android.com/static/images/fundamentals/diagram_multiple_instances.png)