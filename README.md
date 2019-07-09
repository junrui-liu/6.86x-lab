# Lab Environment for 6.86x

This repository contains recipes for building and running a dockerized lab environment for [6.86x: Machine Learning with Python](https://courses.edx.org/courses/course-v1:MITx+6.86x+1T2019/course/).

## Prerequisites
- Docker server and client installed.

## Instructions
- To build the image, run the script `./build` in the terminal. It might take a couple of minutes to download the required images and packages.
- To run the container, run the script `./run`.
  - This, by default, starts a Jupyter Lab server container called `6.086x`, which you can interact with via a host browser at `0.0.0.0:8888`.
  - Files are shared between the host and the running container through the `projects` folder.
  - When done, run the command `docker kill 6.086x`.