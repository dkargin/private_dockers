# private_dockers #

Collection of docker recipes for personal usage

## alpine-cmake ##

Alpine-based image with C++ and CMake for my local CI purposes

 - alpine-cmake:v0.1 - based on alpine:3.14
 - alpine-cmake:v0.2 - based on alpine:3.15 and brings update to cmake version.
 - alpine-cmake:v0.3 - based on alpine:3.16 updates cmake to v3.23.1

## alpine-cmake-doxygen ##

This image extends `alpine-cmake` with doxygen and latex

 - alpine-cmake-doxygen:v0.1 - based on alpine-cmake:v0.1
 - alpine-cmake-doxygen:v0.2 - based on alpine-cmake:v0.2
 - alpine-cmake-doxygen:v0.3 - based on alpine-cmake:v0.3

## cuda-cmake ##

Ubuntu-based image with both cuda11 and cmake:

 - cuda-cmake:latest
 - cuda-cmake:v0.2
 - cuda-cmake:v0.3 - added conan build to image
 - cuda-cmake:v0.4 - updated cmake.
 - cuda-cmake:v0.5 - updated base image to cuda:12.0.0-devel-ubuntu20.04 and used default C++ compiler.

### cuda-cmake:v0.4 ###

Key packages: cmake 3.21.4, gcc-10, ninja

## cuda-physics ##

Image for physics project.

 - cuda-physics:v0.3
 - cuda-physics:v0.4 - added more python files
 - cuda-physics:v0.4.1 - fixed mesa-3d requirements
 - cuda-physics:v0.5 - updated cuda-cmake version and added alembic library.

## cuda-cmake-open3d ##

cuda-cmake-open3d:v0.2 - working image for open3d-based project