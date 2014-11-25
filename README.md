LightFAT32
==========

A lightweight implementation of the FAT32 filesystem for generally dedicated for embedded systems.
Tested successfully on ATMEGA8, Raspberry Pi, Intel Galileo.

Objective
---------
The purpose of the LightFAT32 is to be an easy to deploy, low-resource FAT32 filesystem for an embedded application.  The idea is not to go for speed or a lot of features, but basic functionality in a library that is *easy to use*.

This is the optional project that is done as part of the course of Operating Systems at National Institute of Technology, Warangal.

Documentation
=============
The main reference documentation has been derived from the DOS file systems FAT documentation published by Microsoft. It is present in this source code as `fatgen103.pdf`. This document / whitepaper has been used for reference to build some of the methods exactly as they've been done in the file system by Microsoft.

Code Base Explanation
=====================

\- build\  : Contains all the build code and object *.o after running the make file.
 - dist \  : Contains the package for distribution after successfully executing the make file.
 - fs   \  : The folder on which the file system has to be mounted. Its empty at first until the test is run.
 - obj  \  : Contains the compiled source objects.
 - scripts\: Contains the shell script implement of `mkfs` in a regular *nix system, implemented as `makefs` for making the
 				file system.
 - src \   : This contains all the source code related to the LightFAT32 file system, it also has support to make it a FAT16.
 .gitignore: This code has been written using Version Control System called `git` built by Linus Trovalds.
 LICENSE  : I have decided to open source this code on the GNU-GPL License after getting it reviewed from the professors.
 Makefile : The setup script that runs using the standard `make` or `cmake` tools in linux to run all the code compilations in
 				order.
 README.md : This Documentation that you're currently reading.
 test.fat32: The FAT32 image. 

 fatgen103.pdf : Reference documentation/whitepaper from Microsoft.


Code Segments
=============

fat32_ui.c : Contains code for FAT entry, support for LFN, Bios Parameter Blocks etc..,

tests.c    : Contains the code tests for Read, Write, root directory using the built file system for checks.
thinfat32.c: Contains the code for the implementation of the embedded file system support and sectors.


include/fat32.h : structure of the FAT32/16 and its backend functions.

include/fat32_ui.h : the functions that is given to run the code as required on the new file system.

include/thinfat32.h : Contains the code for the frontend functions, data and backend functions after decing on the FS types.

include/thinternal.h : Structures for the LFN and the Legacy functions of the *nix platform.

All the code is commented in the code as required cleanly.


