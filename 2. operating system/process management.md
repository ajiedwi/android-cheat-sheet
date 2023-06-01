# Process Management

Android provides several means on different layers to compose, execute and manage applications.

1. **Foreground Process**: This is the app currently in use by the user. Other processes can be considered foreground processes if they are interacting with the process that is currently in the foreground.

2. **Visible Process**: This is a process that ism't in the fpregeound but is still affecting what is seen on the screen. For example, a foreground process maybe a dialog but the visible process is the app in the background of the screen which triggered the dialog.

3. **Service Process** This is a process that isn't tied to any app on screen but is still doing something in the background such as playing music or downloading files.

4. **Background Process**: These are processes that are currently not visible to the user and therefore do not have any impact on the user experience. These are apps that are paused and are kept in memory for quick access in the future. They don't use valuable CPU time and any other resources from it.

5. **Empty Process**: This does not contain any app data anymore. They are kept around for caching purposes to speed launch later but maybe killed by the system if necessary.

Ussually, Android **only** kills background and empty processes so the user experience not affected. This is happen **only** when memory usage goes too high, but usually Android doesn't kill app.

Processes can contain multiple threads such as in Linux based systems. Most Android applications implement thread to separate the UI from input handling and I/O operations or long running calculations.