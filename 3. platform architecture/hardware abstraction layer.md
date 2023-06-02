# Hardware Abstraction Layer (HAL)

`HAL` is a programming or code layer that allows for communicating between software and hardware in a system. It may be utilized on a number of OSes in a variety of applications and scenarios.

The Android HAL standard offers a standardized interface for hardware makers to implement lower-level driver updates. You can use a `HAL` to add functionality to a higher-level framework without affecting or modifying it. Your Android device will load the implementations in modules at the appropriate moment. Android relies on `HAL` apps to obtain hardware support. Android HAL is a C/C++ language supply layer. It supports an Android application or the framework order by using functions provided by the lower-layer Linux kernel.

Android `HAL` connects hardware and software. Java APIs, not by system calls, are used by the Android application/framework to connect with the underlying hardware. Linux, on the other hand, can only handle system calls from applications.

The conclusion is `HAL` is a driver interface that enables software to communicate with the hardware.