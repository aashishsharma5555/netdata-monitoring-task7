# Netdata Monitoring with Docker on Linux VM (Access from Windows)

This project demonstrates how to set up *Netdata, a real-time system monitoring tool, on a Linux Virtual Machine (VM) using **Docker. The Netdata dashboard is made accessible from the **Windows host* through *port forwarding* using VirtualBox.

---

## What is Netdata?

[Netdata](https://www.netdata.cloud/) is a distributed, real-time health and performance monitoring tool. It provides:

- Beautiful, interactive web dashboards
- Real-time insights into CPU, RAM, disk, network, Docker containers, and more
- Lightweight, low-overhead monitoring
- Alerts and anomaly detection

It's perfect for monitoring servers, containers, and applications with zero configuration.

---

## Steps Followed

### 1. *Install Docker inside your Linux VM*

Ensure Docker is installed and running inside your Linux virtual machine.

sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker

# Run Netdata container
docker run -d --name=netdata -p 19999:19999 netdata/netdata
-d run container in detached mode
--name=netdata names your container "netdata"
-p 19999:19999 maps port 19999 of container
netdata/netdata pulls and run the netdata image from docker hub

#set VM network setting in port forwarding 
name, protocol, hostIP, guestIP, guestPORT
save ENTER
run in default browser http://localhost:19999 and http://127.0.0.1:19999
