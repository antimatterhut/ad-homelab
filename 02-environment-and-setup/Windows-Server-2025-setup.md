
# Windows 11 Server setup

This document is dedicated to me setting up my Domain Controller or my Windows Server 2025 virtual machine. This machine will host my domain ad-rbphs, active directory roles and services, DNS services and other features.  


## 💾 1. Installation

- 1. Downloaded the Windows Server 2025 from https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025 

- 2. Downloaded the VirtIO drivers from https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/ 

- 3. Uploaded the ISO to the Proxmox node's local storage, aswell as the VirtIO drivers

- 4. Created a new VM in the Proxmox web UI, configured with settings from this screenshot:
Note: MAKE SURE to tick the box that says add an additional drive for VirtIO drivers. These are your network and storage drivers for Windows virtual machines on proxmox.

![image of server settings](/05-screenshots/serversettings.png)

- 5.  Finally, boot up the virtual machine and run through the installer.

- 6. Chose Windows Server 2025 Standard/Datacenter (Desktop Experience) 



---

## 💻 2. Initial Configuration

After installation, I performed the following:

(*delete this, replace)
- Changed the machine name to `WinServer2025`
- Set a **static IP address**: `192.168.1.10`
- Set the computer’s **time zone**

---

## 🧱 3. Installing AD DS Role

I need to install the active directory and domain services role onto this server. 

Heres how to do that:

---

## 🏰 4. Promoting to Domain Controller

Now, I need to promote this server to domain controller.

Heres how to do that:

---

## 🧪 5. Post-Installation Checks

(some command that shows that I am the domain controller)

---

## 📦 6. Summary

In this document, I showed you how I setup my domain controller Windows Server 2025 virtual machine.

---
