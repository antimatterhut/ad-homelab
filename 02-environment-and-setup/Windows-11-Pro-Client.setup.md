
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

Upon opening the Virtual Machine, the windows installation will happen. Make sure to pick Windows 11 Pro Desktop edition. The professional version is essential because it allows for Active Directory domain joining. Desktop edition because students and teachers use desktops, not command line clients. 

There will be a menu that says Install Driver to show hardware in the windows setup. When this menu appears, click browse, go to your Virtio drivers, go to the folder amd64 and click on the w11 folder. These are the correct drivers. 

After this, install windows to your drive of choice. The installation should take a few minutes, after you should be ready to go. 
---

## 💻 2. Initial Configuration

After installation, I performed the following:

- Changed the machine name to `school`
- Set a **static IP address**: `192.168.0.221`

Here are powershell scripts that verify this on my client machine:


![image of setup](/05-screenshots/clienthostname.png)

![image of setup](/05-screenshots/clientip.png)

---

## 🧱 3. Domain Joining

- With this domain join, I can test a variety of users from my AD using this virtual machine. I can login as a teacher, a student, whatever.
- The first thing to do in order to complete the Domain join is my configuring DNS to point to the IP address of the Domain Controller (`192.168.0.220`)
- Here is a screenshot using Get-DnsClientServerAddress -AddressFamily IPv4 that verifies it.

![image of dns](/05-screenshots/clientdns.png)

- The second thing to do is to join the domain
- Look up computer name in the windows bar
- In this tab, there should be an option to join a domain
- Write in the domain name, for me it was rbphs.local
- Log in using the credentials of an administrator
- You should be domain joined!

---

## 🧪 4. Post-Installation Checks

- In order to check if everything is running, we need to login as a user we created on the Domain
- We will login as student Chris Griffin using Chris Griffins credentials

- Here is a screenshot of the chris griffin user I have created

![image](/05-screenshots/cguser.png)

- Here is proof that I logged in as Chris Griffin

![image](/05-screenshots/whoamicg.png)

- I want to see if this also works for another OU. Lets also login as a teacher.
- We will login with Jason Good, an english teacher

- Here is a screenshot of the Jason Good user I have created

![image](/05-screenshots/jasongood.png)

- Here is proof that I logged in as Jason Good

![image](/05-screenshots/jgwhoami.png)

- And that pretty much proves that this computer is all setup and domain joined to my main DC rbphs.local.


---

## 📦 5. Summary

In this document, I setup a Windows 11 Pro Client on Proxmox to act as a lab computer for my School Active directory environment. This involved installing Windows 11 Pro with the necessary VirtIO drivers, configuring the machine's hostname and static IP address, and pointing DNS to the domain controller (`192.168.0.220`) so the client could locate and join the `rbphs.local` domain. 

Once domain-joined, I verified the setup by logging in as two different types of AD users. The first, a student (Chris Griffin) and a teacher (Jason good). Successfully authenticating both accounts confirms that the client is properly domain-joined.

---
