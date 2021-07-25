# What is this
It's a containerized example application (polygons) from the butano c++ library. It outputs a .gba and .elf game file, when run properly.

## What can I do with it
you can copy/paste the dockerfile into your own butano project and copy the makefile structure from the example projects or modify the dockerfile to suit a new makefile with different paths to the butano installation.

If you reference butano in a different location in your makefile these are the lines you want to modify:

```
RUN cp -r butanoPackage/butano-7.2.0/butano /

RUN cp -r butanoPackage/butano-7.2.0/common /
```

No license on my end or anything so do whatever you want with it, but be aware of the other pieces of software in this repo with licenses

## How do I run it
I'm on one of the ARM macs so docker commands are a little different, but this is the command to build the image on my machine:

```
docker buildx build --platform linux/amd64 . -t gba-compiler
```

This is the command to run the container:

```
docker run --rm -ti -v ${PWD}:/gba/src --platform linux/amd64 gba-compiler
```