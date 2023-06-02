# Native Library

A native library is a library that contains "native" code. Is the code that compiled for a specific hardware architecture or operating system such as x86 or windows. In android, `native library` means a non-Java library that used by the system. It's written on C/C++, etc like normal `DLL`s or libs. We can load these native libraries with `JNI`.