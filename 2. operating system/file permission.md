# File Permission in Android

File permission on Android are the same as the permission on Linux. This format of file permissions is called **CHMOD (change mode)**. It determines how much access a file should have.

The permission is usually written in number or letters

No permissions : **0** or **---**

Execute Only : **1** or **--x**

Write Only : **2** or **-w-**

Write and Execute : **3** or **-wx**

Read Only : **4** or **r--**

Read and Execute : **5** or **r-x**

Read and Write : **6** or **rw-**

Read, Write, and Execute : **7** or **rwx**

The sort of the written permission is : Owner Group Others

For example, permission `644` is read as below

Owner - `6` 

Group - `4`

Others - `4`

Another example, permission `rw-r-r` is read as below

Owner - `rw`

Group - `r`

Others - `r`

The *read* permission grants the ability to read a file. When set for a directory, this permission grants the ability to read the **names** of files in the directory, but not to find out any further information about them such as contents, file type, size, ownership, permissions.

The *write* permission grants the ability to modify a file. When set for a directory, this permission grants the ability to modify entries in the directory. This includes creating files, deleting files, and renaming files.