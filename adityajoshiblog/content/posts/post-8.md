---
title: "Intro to Dockerfile"
date: 2023-03-16T20:39:18+05:30
tags: ["docker", "podman"]
draft: false
---

 A __Dockerfile__ is a text document that contains all the commands a user could call on the command line to assemble an image.

 In otherwords, it will have commands that you want to run to build your docker image.

 Example file -

 ```docker
 # This image is based on python:3.9 docker image
 from python:3.9

 # install pandas in the base image.
 RUN pip install pandas

 # Make the entrypoint for this image as bash.
 # Same as docker run -it -entrypoint=bash python:3.9
 # This will run docker image and instead of python prompt you will get bash.
 ENTRYPOINT [ "bash" ]
 ```

