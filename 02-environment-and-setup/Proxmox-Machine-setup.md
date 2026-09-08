
# Proxmox

This homelab was built on a proxmox machine. Proxmox VE is a free, open-station platform that lets you turn a single physical computer into many "mini" computers using virtualization. Its essentially a hypervisor and operating system in one, and I can access the web-based interface through the static ip adresss i assigned at port 8006. In the web based interface, I can manage and run my virtual machines. This is how I am running this lab. 

## 💻 Physical Machine Specs

I bought a BeeLink Ser5 mini-pc with 32 gb of ram, AMD Ryzen 5 5500U cpu and 500 GB NVMe SSD.


## 💾 1. Installation

I followed a video on how to install it all and set it all up initially.
https://www.youtube.com/watch?v=jMlo1m7Op7E

Here is a picture of the static ip I assigned to my proxmox machine on my local network.
What we are looking for under vmbr0. 
![image of static ip](/05-screenshots/proxmox-config-static-ip.png)


It is 192.168.0.201
I can access the web based portal by typing in 192.168.0.201:8006, or the ip address at port 8006. 

---

## 💻 2. Virtual Machines

I have many Virtual Machines, but only 2 are used for this lab. 
Here is a picture of both of the virtual machines on the proxmox web-interface. All of the other virtual machines, used for other tinkering and various projects are shutdown.  


![image of 2 Virtual Machines](/05-screenshots/2vm.png)

---

## 3. 🤔 Other options for virtualization

I am using a proxmox machine, however there are other options and its likely that the proxmox is overkill for a project like this. Using any sort of hypervisor such as vmware or virtualbox on a machine with a 16 gigabytes of ram and a decently strong cpu can run this lab. I am just using proxmox because I have a proxmox machine and why not?



