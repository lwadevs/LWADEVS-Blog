---
title: "Security-Enhanced Linux (SELinux)"
date: 2022-01-16
categories: 
  - "redhat"
  - "selinux-security-enhanced"
coverImage: "selinux.png"
---

## Overview

**Security-Enhanced Linux (SELinux)** is a security architecture for **Linux® systems** that allows administrators to have more control over who can access the system. It was originally developed by the United States National Security Agency (NSA) as a series of patches to the **Linux kernel** using Linux Security Modules (LSM).  

SELinux was released to the open source community in 2000, and was integrated into the upstream Linux kernel in 2003.

## How does SELinux work?

<figure>

![](images/selinux_decision_process.png)

<figcaption>

RedHat Customer Portal

</figcaption>

</figure>

**SELinux** defines access controls for the applications, processes, and files on a system. It uses security policies, which are a set of rules that tell SELinux what can or can’t be accessed, to enforce the access allowed by a policy. 

When an application or process, known as a subject, makes a request to access an object, like a file, SELinux checks with an access vector cache (AVC), where permissions are cached for subjects and objects.

If SELinux is unable to make a decision about access based on the cached permissions, it sends the request to the security server. The security server checks for the security context of the app or process and the file. Security context is applied from the SELinux policy database. Permission is then granted or denied. 

If permission is denied, an "avc: denied" message will be available in /var/log.messages.

https://www.youtube.com/watch?v=\_WOKRaM-HI4

### **How to configure SELinux** 

There are a number of ways that you can configure SELinux to protect your system. The most common are targeted policy or multi-level security (MLS).

Targeted policy is the default option and covers a range of processes, tasks, and services. MLS can be very complicated and is typically only used by government organizations. 

You can tell what your system is supposed to be running at by looking at the /etc/sysconfig/selinux file. The file will have a section that shows you whether SELinux is in permissive mode, enforcing mode, or disabled, and which policy is supposed to be loaded.

### **SELinux labeling and** **type enforcement** 

Type enforcement and labeling are the most important concepts for SELinux.

SELinux works as a labeling system, which means that all of the files, processes, and ports in a system have an SELinux label associated with them. Labels are a logical way of grouping things together. The kernel manages the labels during boot.

Labels are in the format user:role:type:level (level is optional). User, role, and level are used in more advanced implementations of SELinux, like with MLS. Label type is the most important for targeted policy. 

SELinux uses type enforcement to enforce a policy that is defined on the system. Type enforcement is the part of an SELinux policy that defines whether a process running with a certain type can access a file labeled with a certain type.

<figure>

![](images/en-selinux-summary-05.png)

<figcaption>

SELinux - How it works...

</figcaption>

</figure>

### **Enabling SELinux**

If SELinux has been disabled in your environment, you can enable SElinux by editing /etc/selinux/config and setting SELINUX=permissive. Since SELinux was not currently enabled, you don’t want to set it to enforcing right away because the system will likely have things mislabeled that can keep the system from booting.  

You can force the system to automatically **relabel the filesystem** by creating an empty file named .autorelabel in the root directory and then rebooting. If the system has too many errors, you should reboot while in permissive mode in order for the boot to succeed. After everything has been relabeled, set SELinux to enforcing with /etc/selinux/config and reboot, or run setenforce 1. 

If a sysadmin is less familiar with the command line, there are graphic tools available that can be used to manage SELinux. 

**SELinux** provides an additional layer of security for your system that is built into **Linux distributions**. It should remain on so that it can protect your system if it is ever compromised.

## Discretionary access control (DAC) vs. mandatory access control (MAC)

Traditionally, Linux and UNIX systems have used DAC. SELinux is an example of a MAC system for Linux. 

With DAC, files and processes have owners. You can have the user own a file, a group own a file, or other, which can be anyone else. Users have the ability to change permissions on their own files.

The root user has full access control with a DAC system. If you have root access, then you can access any other user’s files or do whatever you want on the system. 

But on MAC systems like SELinux, there is administratively set policy around access. Even if the DAC settings on your home directory are changed, an SELinux policy in place to prevent another user or process from accessing the directory will keep the system safe. 

SELinux policies let you be specific and cover a large number of processes. You can make changes with SELinux to limit access between users, files, directories, and more.

## How to handle SELinux errors

When you get an error in SELinux there is something that needs to be addressed. It is likely 1 of these 4 common problems:

1. **The labels are wrong.** If your labeling is incorrect you can use the tools to fix the labels.
2. **A policy needs to be fixed.** This could mean that you need to inform SELinux about a change you’ve made, or you might need to adjust a policy. You can fix it using booleans or policy modules.
3. **There is a bug in the policy.** It could be that a bug exists in the policy that needs to be addressed.
4. **The system has been broken in to.** Although SELinux can protect your systems in many scenarios, the possibility for a system to be compromised still exists. If you suspect that this is the case, take action immediately.

### What are booleans?

![](images/basic-selinux-commands-05.png)

![](images/enable-disable-selinux-boolean.png)

Booleans are on/off settings for functions in SELinux. There are hundreds of settings that can turn SELinux capabilities on or off, and many are already predefined. You can find out which booleans have already been set in your system by running getsebool -a.

**All notes and relavant documentation is from RedHat**: **https://www.redhat.com/en/topics/linux/what-is-selinux -** there is so much to this subject, where by excellent reading literature and books are available from many sources, that go into greater depth on the specifics and technical details of this SE-Linux security subject.

<figure>

![](images/redhat-linux.jpeg)

<figcaption>

by lwalinux

</figcaption>

</figure>
