# 🛡️ Active Directory Home Lab - Windows Server 2025

This is my lab that attempts to mimic a High School Active Directory System. It uses Windows 2025 Server, and the Clients are on Windows 11 Pro. This lab was created to demonstrate hands on experience managing AD, DNS, GPOs, and security policies.


---


## 🎯 Learning Objectives

- Designing and implementing an OU structure that reflects a real organization (Students by graduation year, Faculty by department, Staff, Administration, Computers, Servers, Groups, Service Accounts).

- Creating and managing user accounts with realistic naming/ID conventions (student vs. teacher numbering, password policies).

- Enforcing role-based restrictions via GPOs — locking down student environments (no Control Panel, Registry Editor, Task Manager, PowerShell, USB storage) while giving faculty broader access.

- Building a shared file infrastructure with two distinct layers: a homework-distribution system (teachers publish, students read-only) and a personal folder-redirection system (each user gets a private, permission-isolated Desktop/Documents folder that follows them across PCs).

- Managing NTFS + share permissions

- Testing and validating each piece against real behavior (logging in as different users, running gpresult, checking whether restrictions/redirections actually took effect) rather than just configuring and assuming it works.

- Documenting as I go using Markdown files, Diagrams, Github, Screenshots

---

## 🔭 Scope

The lab has a moderate scope that covers 


- Identity: students, teachers, staff, admins, service accounts, computer objects, and security/distribution groups.

- Policy enforcement: baseline lab computer restrictions plus separate student/teacher/domain-wide GPOs.

- Storage: a dual-purpose share structure, class/homework folders and personal redirected folders with permissions differentiated by role.

- Validation: real login testing across multiple accounts



---

## 🧰 Hardware & Software

### Host Machine
| Component | Spec |
|---|---|
| CPU | 12 x AMD Ryzen 5 5500U with Radeon Graphics (1 Socket |
| RAM | 32 GB |
| Storage | 512 GB SSD |
| OS | Proxmox |

### Virtualization
- **Platform:** Proxmox
- **Network mode:** Internal Network / NAT Network *(so VMs can talk to each other but you control internet access)*

### Virtual Machines

| VM Name | Role | OS | vCPU | RAM | Disk |
|---|---|---|---|---|---|
| AD-RBPHS | Domain Controller (AD DS, DNS) | Windows Server 2025 | 2 | 8 GB | 64 GB |
| Lab PC | Domain-joined client (lab machine) | Windows 11 Pro | 2 | 4 GB | 64 GB |


### Software / Roles & Features
- **Active Directory Domain Services (AD DS)**
- **DNS Server**
- **File and Storage Services** (shared drives, NTFS permissions)
- **Group Policy Management Console (GPMC)**
- PowerShell / Command Prompt (admin scripting, `gpresult` testing)
- Active Directory Users and Computers (ADUC)

### Domain Details
- **Domain name:** `rbphs.local`
- **Forest/Domain functional level:** e.g. Windows Server 2016+

---

## 🛠️  Project Structure

I can just update this later when the structure is sound.