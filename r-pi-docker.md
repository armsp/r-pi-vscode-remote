---
layout: default
title: Installing Docker on Raspberry Pi 4
---

# Installing docker
<!-- Read these two blogs to get srated
- https://www.docker.com/blog/happy-pi-day-docker-raspberry-pi/
- https://blog.alexellis.io/getting-started-with-docker-on-raspberry-pi/ -->

I performed the following based on the [official docs](https://docs.docker.com/install/linux/docker-ce/debian/#install-using-the-convenience-script) -

1. SSH to your Pi using - `ssh pi@raspberrypi.local`
2. Install some dependencies using - `sudo apt-get install apt-transport-https ca-certificates software-properties-common -y`
3. Get the installation script - `curl -fsSL https://get.docker.com -o get-docker.sh`
4. Run the script - `sudo sh get-docker.sh`
5. To run Docker without root add yourself to the group using - `sudo usermod -aG docker pi` OR `sudo usermod -aG docker $USER`
6. Reboot - `sudo reboot`
7. Execute a docker command - `docker run hello-world`
   ```console

   Hello from Docker!
   This message shows that your installation appears to be working correctly.

   To generate this message, Docker took the following steps:
   1. The Docker client contacted the Docker daemon.
   2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
      (arm32v7)
   3. The Docker daemon created a new container from that image which runs the
      executable that produces the output you are currently reading.
   4. The Docker daemon streamed that output to the Docker client, which sent it
      to your terminal.

   To try something more ambitious, you can run an Ubuntu container with:
   $ docker run -it ubuntu bash

   Share images, automate workflows, and more with a free Docker ID:
   https://hub.docker.com/

   For more examples and ideas, visit:
   https://docs.docker.com/get-started/

   ```

If it still doesn't start you can try the following -
- `sudo systemctl start docker`
- `sudo systemctl enable docker`

[BACK](./)