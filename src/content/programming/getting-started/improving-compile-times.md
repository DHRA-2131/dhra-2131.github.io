---
title: 'Improving Compile Times'
description: 'Decreasing the time you waste'
---

## Why My Computer Go Slow?

Most modern computers have multiple "Mini-CPU's" called cores inside their Central Processing Unit (CPU). This helps speed up tasks
that may need multiple things processed at once. Unfortunately by default, the compiler in the PROS toolchain defaults to only using 1 core
and processing each file that need to be compiled concurrently. To take advantage of this, we change some flags in the Makefile telling the
compiler to use multiple processors.

## How do I fix?
1. Locate the Makefile File in the root of your project folder
2. Don't be scared
3. Locate the line that says "EXTRA_CXXFLAGS="
4. Directly below that line insert a new line with "MAKEFLAGS+= -j8"

_Note: If your processor happens to have more than 8 cores, change the -j8 flag to the number of cores you would like to use
