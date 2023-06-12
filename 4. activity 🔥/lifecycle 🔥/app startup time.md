# App Startup Time

App launch can take place in one of three states, each affecting how long it takes for your app to become visible to the user: cold start, warm start, or hot start. In a cold start, your app starts from scratch. In the other states, the system needs to bring the running app from the background to the foreground. To optimize your app for faster startup, it's useful to understand what's happening at the system and app levels, and how they interact, in each of these states.

## Cold start

A cold start refers to an app's starting from scratch: the system's process has not (until this start) created the app's process. Cold starts happen in cases for example when we open our app for the first time after we reboot the device or since the system killed the app.

At the beginning of a cold start, the system has three tasks. These tasks are :

1. Loading and launching the app
2. Displaying a blank starting window for the app immediately after launch
3. Create the app process

As soon as the system creates the app process, the app process is responsible for the next stages :
1. Creating the app object
2. Launching the main thread
3. Creating the main activity
4. Inflating views
5. Laying out the screen
6. Performing the initial draw

## Warm start

A warm start encompasses some subset of the operations that take place during a cold start, at the same time, it represents more overhead than a hot start. There are many potential states that could be considered warm starts. For example :
- The user backs out of your app, but then re-launches it. The process may have continued to run, but the app must recreate the activity from scratch via a call to `onCreate()`
- The system killed your app from memory, and then the user re-launches it. The process and the activity need to be restarted, but the task can benefit somewhat from the saved instance state bundle passed into `onCreate()`.

## Hot start

 A hot start of your application is much simpler and lower-overhead than a cold start. In a hot start, all the system does is bring your activity to the foreground. If all of your application's activities are still resident in memory, then the app can avoid having to repeat object initialization, layout inflation, and rendering.