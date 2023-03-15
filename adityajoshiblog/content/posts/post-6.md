---
title: "Docker setup on mx linux"
date: 2023-03-15T18:17:48+05:30
draft: false
---

Steps to setup docker on MX Linux.

1. Follow instructions provided in this [link](https://docs.docker.com/desktop/install/linux-install/) for debian distro.
2. Run ```sudo groupadd docker```
3. Then ```sudo usermod -aG docker $USER```
4. Install apparmor if not already. ```sudo apt install apparmor```
5. Restart services. ```sudo service apparmor restart``` and ```sudo service docker restart```
6. Run ```docker run hello-world``` => this should tell you whether you have installed properly or not.

