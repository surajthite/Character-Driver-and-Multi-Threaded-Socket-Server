This repository contains custom character driver designed to read the device file and revert back to the user space implementing circular buffer and a multi-threaded socket server accepting multiple incomming connections and updating the device file in the user space. 

## aesd-char-driver
This folder contains the character driver developed and implemented using C. Unit Test cases are also written along with scripts to load and unload the module. 

## server
This folder consists of C files for designed socket server which implements multi-threading to manage multiple clients. Mutexes are used to provide mutual exclusion to access the device file along with POSIX queues to manage threads upon reception of the termination signals. 

The  sockettest.sh tests the socket server while the drivertest.sh tests the character drivers.

The above binaries have been cross compiled for aarch64 system and emulated on QEMU. 

Simply use the makefile in the parent directory inorder to build the binaries and test them using the test scripts.
