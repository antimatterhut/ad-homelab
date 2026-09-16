
# Windows 11 Server setup

This document is dedicated to me setting up my Domain Controller or my Windows Server 2025 virtual machine. This machine will host my domain ad-rbphs, active directory roles and services, DNS services and other features.  


## 💾 1. Installation

- 1. Downloaded the Windows Server 2025 from https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2025 

- 2. Downloaded the VirtIO drivers from https://fedorapeople.org/groups/virt/virtio-win/direct-downloads/archive-virtio/ 

- 3. Uploaded the ISO to the Proxmox node's local storage, aswell as the VirtIO drivers

- 4. Created a new VM in the Proxmox web UI, configured with settings from this screenshot:
Note: MAKE SURE to tick the box that says add an additional drive for VirtIO drivers. These are your network and storage drivers for Windows virtual machines on proxmox.

![image of server settings](/05-screenshots/serversettings.png)

- 5.  Finally, boot up the virtual machine and run through the installer. Most of the settings are self explanatory. 

- 6. Chose Windows Server 2025 Standard/Datacenter (Desktop Experience) 

- 7. Pick your disk of choice and install 


---

## 💻 2. Initial Configuration

After installation, I performed the following:

- Changed the machine name to `AD-RBPHS`

![image](/05-screenshots/hostnameServer.png)


- Set a **static IP address**: `192.168.0.220`

![image](/05-screenshots/staticipserver.png)

- Set the computer’s **time zone**

![image](/05-screenshots/timezoneDC.png.png)


---

## 🧱 3. Installing AD DS Role

I need to install the active directory and domain services role onto this server. 

Heres how to do that:

1. Click Manage at the top of the server manager, go to add roles and features

![image](/05-screenshots/addroles.png)

2. Check role based or feature based installation

![image](/05-screenshots/role.png)

3. Chose the following AD-DS services aswell as File and Storage Services and DNS if its not there by default.

![image](/05-screenshots/timezoneDC.png)

4. Click Install.


---

## 🏰 4. Promoting to Domain Controller

Now, I need to promote this server to domain controller. This is only possible AFTER you have done the previous steps. You must have set a static IP and installed the AD-DS role.

Heres how to do that:

After installing AD-DS role, you will see a yellow notification flag at the top of the server manager.

Click that, select promote this server to domain controller.

Choose add new forest

Enter your root domain name and supply valid domain administrator credentials when prompted.

Just pick the default for the next couple of screens.

Install. This should take a few minutes.

Upon logging in, you should see your domain/administrator.

Login with the administrator credentials you have chosen.

---

## 🧪 5. Post-Installation Checks



In order to see if you are a domain controller, run Get-WmiObject -Class Win32_ComputerSystem | Select-Object Domain, Roles in powershell and look at the results. 

It should say domain_controller or primary_domain controller as shown here:

![image](/05-screenshots/proofdc.png)


---

## 📦 6. Summary

In this document, I showed you how I setup my domain controller Windows Server 2025 virtual machine.

---
