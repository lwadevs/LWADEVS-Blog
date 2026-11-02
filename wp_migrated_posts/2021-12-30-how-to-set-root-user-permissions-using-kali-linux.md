---
title: "How to set root user permissions using Kali Linux"
date: 2021-12-30
categories: 
  - "set-root-user-permissions"
coverImage: "img_0144.jpg"
---

![](images/screenshot-2021-12-29-at-18.40.18-1.png)

**ROOT USER / SUPER-USER PRIVILEGES**

The **root user name** or **account** has default permission to all available commands and files on a Linux or any other Unix-like operating system. It is also known as the **superuser**, the **root account**, and the **root** **user**.

Username: “kali” are the standard credentials for logging into the new Kali system. This establishes a session as user “**kali**,” You must use this user password after “**Sudo**” to gain root access. Kali Linux was using the root account by default till recent times.

Root login is restricted in the current versions of Kali, allowing you to utilize your regular user account to access the GUI.

The reasons behind this modification should be clear, but if you are a Kali user, you are presumably already familiar with a Linux system; thus, there is a little risk in allowing you to log in with the root account. We will create a **non-root user** with administrative capabilities while we install Kali Linux. Other Linux distributions follow a similar procedure.

**The default user** in older versions of Kali is **root**.

But first, we must create a regular account before installing Kali Linux. To install any program or package under Kali, we must first log in and then use the **Sudo command**. So, to gain **root access** to Kali Linux, we must follow the appended methods:

## **Method 1:**

If many users share the system, some of them may wish to serve as administrators and manage the system as a whole. So that no direct effect on the system’s operation and easy sharing across users, the suitable users can be granted administrator privileges and others with **non-root privileges**. It will be tough for an attacker to break into the system if there is a root user.

The usage of **sudo** and the disablement of the root account might mislead intruders because they would not know which account had admin privileges. **Sudo policies** can be created and deployed in a corporate network as well as Kali Linux distributions.

Having a root password improves monitoring capabilities because it allows you to see what others users have been doing in the system and whether or not any intrusions are occurring.

**Step 1:** To begin, download the kali-root-login package with the apt package manager.

**$ sudo apt install kali-root-login**

![](images/screenshot-2021-12-30-at-18.49.46.png)

**Step 2:** Next, use the following listed command to configure the program we have just downloaded.

**$ sudo dpkg-reconfigure kali-grant-root**

![](images/screenshot-2021-12-30-at-19.09.33.png)

**Step 3:** Upon the execution of the above command, the following displayed screen will pop up.

![](images/screenshot-2021-12-30-at-19.14.43.png)

**Step 4:** Ensure that “enable password-less privilege escalation” is selected before clicking enter to proceed further.

![](images/screenshot-2021-12-30-at-19.21.35.png)

![](images/screenshot-2021-12-30-at-19.21.49.png)

**Step 6:** It’s as simple as that. You can even use the Sudo command to perform all subsequent commands as root, but you will never require a password. Try logging out and then in, then perform a command that typically requires root access to see whether it works.

**$ sudo apt update**

![](images/screenshot-2021-12-30-at-19.22.06.png)

## **Method 2**

We connect as non-root users by default on Kali Linux 2021, and we must set the root password ourselves. We do not even know the root password in the first session, so we can’t log indirectly. Instead, we have to log in as a non-user, which is established when we install Kali Linux.

**Step 1:** To begin, you must first open the terminal and then use this command to determine the current login user.

**$ whoami**

![](images/screenshot-2021-12-30-at-19.22.22.png)

You can check that the user name is **kalsoom** in our system.

**Step 2:** To change the standard user account to the root account, execute the following cited command into the terminal.

**$ sudo -I**

![](images/screenshot-2021-12-30-at-19.22.34.png)

**Step 3:** You can now verify that you are in the root by using the appended command.

![](images/screenshot-2021-12-30-at-19.22.44.png)

The output displays the user name as “root”.

## Final thoughts...

So, we learned how to:

grant root rights to a regular user in Kali Linux. You can use the instructions in this guide to prefix any command with **sudo** and never have to input a password again. 

When the Kali developers restricted root login in the latest releases, they must have anticipated that some users would be irritated; therefore, they provided numerous options for restoring capability. 

* * *

![](images/tux-penguin-current.jpg)

“Most good programmers do programming not because they expect to get paid or get adulation by the public, but because it is fun to program.”

\- Linus Torvalds.
