
# Windows 11 Pro Client setup

This document is dedicated to me setting up my client machine. This client is supposed to be equivalent to a lab computer for a school, where 
students and teachers can login and do work.


## 💾 1. Installation

You will need to download 2 things if you want the lab to work on proxmox.

- Windows 11 Pro ISO file downloaded from the official windows site. 
- VirtIO drivers (necessary for every windows VM on proxmox). 

Here is a screenshot of the settings I chose for the client VM on proxmox.

![image of setup](/05-screenshots/testingsetup.png)

It is important to click the box on add an additional drive for virtio drivers on the menu where you create the VM. 

---

## 💻 2. Initial Configuration

After installation, I performed the following:

(*delete this, replace)
- Changed the machine name to `WinServer2025`
- Set a **static IP address**: `192.168.1.10`

---

## 🧱 3. Domain Joining

- With this domain join, I can test a variety of users from my AD using this virtual machine. I can login as a teacher, a student, whatever.
---

- Configured DNS to point to the domain controllers DNS (`192.168.1.10`)

## 🧪 4. Post-Installation Checks

- I need to confirm that this virtual machine is under the domain 

- Logging in as a Student that I created

(picture of that)

gpresult summary

(picture of that)

---

## 📦 5. Summary

In conclusion, this post was created to show what I did in order to setup my working domain joined Windows 11 pro virtual machine.

---
