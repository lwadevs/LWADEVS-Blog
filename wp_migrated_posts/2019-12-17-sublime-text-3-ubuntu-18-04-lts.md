---
title: "Sublime Text 3 &amp; Ubuntu 18.04 lts"
date: 2019-12-17
categories: 
  - "sublime-text-3-ubuntu-18-04"
---

How to install Sublime Text 3 Code Editor on Ubuntu

Sublime Text is a powerful text editor that is mostly used for web and software development. It can be installed and used on multiple platforms ie Windows, Linux, and MAC. Sublime text has a lot of functionalities and it supports many programming and markup languages. You can enhance its functionalities by installing new plug-ins. It is the most preferred editor for many programmers. It is free to download and install on any system. Upon the first installation. You can use its unlicensed free version but with limited functionalities. Although, It has an unlimited evaluation period.

**In this article, we will show you how to install the latest version of Sublime Text (Sublime Text 3) on Ubuntu 18.04 LTS. You can use the same procedure for installing earlier versions too.**

Sublime Text Editor Features:

**Some of the useful features of Sublime Text 3 are:**

- Goto Anything: When you have a large bunch of files, you can use Ctrl + R shortcut that will list them and make them easier to find.
- **Multiple Selections:** Multiple selection features enable you to make extensive changes to the text efficiently
- **Split Editing:** With split editing, you can edit files side by side and get the most out of the widescreen.
- **Cross Platform:** You can use sublime text on multiple platforms i.e. Windows, Linux, and Mac. You will one require one license to use sublime text, it does not depend on which OS you use.
- **Customize Anything:** You can customize it simply the way you need. It gives you the flexibility of configuring it to meet your preferences.
- **Keyboard shortcuts:** You can use a range of handy shortcuts for various functionalities to save time. In addition, you can change the default keyboard shortcuts according to your own preferences.

Installing Sublime Text 3 Editor

**Follow the below steps to install Sublime Text 3:**

Step 1: Installation of the repository key

First, you will need to install GPG key on your system. For that launch the Terminal by using **Ctrl+Alt+T** key shortcut and un the following command in Terminal:

$ wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - 

![](images/word-image-359.png)

Step 2: Add Sublime program repository

Then you will need to add the Sublime Text repository to your package manager.

I am using here sublime text stable repository. After that run the following command in Terminal:

$ echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

![](images/word-image-360.png)

If you want to add Dev repository instead of stable repository, run the following command:

$ echo "deb https://download.sublimetext.com/ apt/dev/" | sudo tee /etc/apt/sources.list.d/sublime-text.list

Step 3: Update your software resources

Now, you will need to update your package manager with the new sublime repositories. Run the following command to update apt repositories:

**$ sudo apt update**

Step 4: Install Sublime Text 3

Now run the following command to install sublime text. It will automatically install the latest version that is sublime text 3.

**$ sudo apt install sublime-text**

![](images/word-image-361.png)

Step 5: Launch Sublime Text 3

Now verify the installation by launching the application from Ubuntu’s Dash menu. Press Windows key, then type **_sublime text._** From the results, click on Sublime Text to launch it.

![](images/word-image-362.png)

That is how you can install Sublime Text 3 on your Ubuntu 18.04 LTS. Now you can use it for advanced editing. However make note that, to use full functional Sublime text, you will need to buy its license. 

![](images/sublime-text-editor.png)

**How to find files on the Ubuntu command line**

A common problem is that you cannot find the files you have placed somewhere. While working under Linux, regardless of the distribution, many GUI options allow you to search for your files. In many cases, however, you will only have the command line terminal, especially if you manage servers or use SSH to access the system. If you cannot find your files, you must search for them using command line applications on Linux.

This article shows you how to find files using the Terminal that is the command line application in Ubuntu OS. There are three well-known methods to search for files on the shell:

1. **Using Find command**
2. **Using Locate command**
3. **Using Grep command**

Find and Locate commands are used to search for the files in the system while grep is used to search file based in the text that it contains. Find is a slower method but contains several search conditions while Locate does not include as many conditions but is much faster than the Find.

Let us get started with the procedure. We will use Ubuntu 18.04 LTS for describing the procedure mentioned in this article.

**Method 1: Using Find command**

Find is a highly flexible command used to search files based on a variety of conditions. It is a very helpful tool when searching a file for which you do not remember the name of the file. Using the Find command you can search based on file and folder name, creation date, modification date, and permissions. You can combine these multiple conditions in a one Find command. It is a very powerful but slower search tool.

The general syntax of the command is:

**$ find /path/to/file/ -iname filename**

![Search for files using find command](images/word-image-87.png)

Search files in a specific directory

You can use the Find command to search for all files in a specific directory. The general syntax would be:

**$ find /path/to/file/**

For instance, to find all the files under the **/home/tin/Downloads/** directory, launch the Terminal by pressing **Ctrl+Alt+T** and then run the following command in Terminal:

**$ find /home/tin/Downloads/**

![Search files in a specific directory](images/word-image-89.png)

Search files in the current directory

To search for files in a current directory, use

**$ find .**

![Search files in the current directory](images/word-image-105.png)

To search for a file named e.g “softwares” under current directory, use the following command in Terminal:

**$ find . -iname Softwares**

![Search files](images/word-image-121.png)

Search using a wildcard

You can also use the wildcard characters to find the files that match the query. The general syntax would be:

**$ find /path/to/file/ -iname filename\***

For instance to search files that start with the word “cent”, run the following command in Terminal:

**$ find /home/tin/** **\-iname cent\***

![Search using a wildcard](images/word-image-107.png)

Search for empty files

You can also search for empty files using the Find command. The general syntax would be:

**$ find /path/to/file/ -iname -empty**

For instance to find empty files under the **/home/tin** directory, run the following command in Terminal:

**$ find /home/tin/ -empty**

![Search for empty files](images/word-image-108.png)

Search based on date and time

Using Find command, you can also search for files depending upon when they were access or modified. There are types of time you can use to search files:

- **mtime (Modification time)**: when the file’s content was modified last time.
- **atime (Access time)**: when the file was accessed last time.
- **ctime (Change time)**: when the file attributes were modified last time.

For instance, to search for files in a current directory that were modified less than 2 days ago, run the following command in Terminal:

**$ find . -mtime -2**

![Search based on date and time](images/word-image-109.png)

To search for files that were accessed less than 2 days ago, run the following command in Terminal:

**$ find . –atime -2**

To search for files that were changed less than 2 days ago, run the following command in Terminal:

**$ find . –ctime -2**

Search based on file size

For instance, to search file whose size is larger than 5MB size, we can use the following command in Terminal:

**$ find . –size +5M\\**

![Search based on file size](images/word-image-112.png)

Search based on file permissions

It is used to find files with specific permission. The general syntax would be:

**$ find /path/to/file/ -type -perm mode**

Where:

**Type** parameter includes **d** or **f** value that are used for specifying type of the file. **d** for directories and **f** for files only.  
**mode** can be either with numeric permission (e.g 777, 655.. etc) or symbolic permission (e.g u=x, a=r+x).

For instance, to search for a file with the permission of 644, we can use the following command in Terminal:

**$ find . –type f –perm 644**

Method 2: Using Locate command

There is another command Locate that can be used to search files in Linux. It does not have as many search conditions as the Find utility offers but it is much better and faster than the Find utility. The reason behind is the background process that actually runs in your system and searches and stores new files in its own database. Unlike Find command, it does not search your local hard disk for files and directories but instead, it searches them in its own database. Its database should be regularly updated for the search utility to work.

Installing Locate

Locate is not installed by default in the Linux OS. You will need to manually install it. Press **Ctrl+Alt+T** to launch the Terminal and then type the following command as sudo to install the Locate utility:

**$ sudo apt-get install locate**

![Install locate command on Ubuntu](images/word-image-114-1024x476.png)

Once the installation is completed, you can use the Locate utility right away.

The general syntax of the command is:

**$ locate –i filename**

Where -i is used to ignore case distinctions.

Searching for a file

For instance, to search for a filename “centos”, use the following command in Terminal:

**$ locate –i centos**

![Search for files using locate command](images/word-image-115.png)

It will search for all the files that include the string “centos” in their filenames.

Search for Multiple files

You can also search for multiple file names simultaneously. For instance, use the following command in Terminal to search for two files “**sdn.txt”** and “**centos”**:

**$ locate –i sdn.txt centos**

![Search for Multiple files using locate](images/word-image-116.png)

Search using Wildcard

You can also use the wildcard character to find the files that match the query. For instance to search for all the files that ends in “.iso”, use the following command in Terminal:

**$ locate –i \*.iso**

![Search using Wildcard](images/word-image-117.png)

Update locate database

Locate command relies on its database to work, so it needs to be updated regularly. Run the following command in Terminal to update the Locate utility database:

**$ sudo updatedb**

![Update locate database](images/word-image-118.png)

Method 3: Using Grep command

Although Grep is not for directly searching files in your system, instead it is used to search text. However, you can use it to display the names of files that contain the particular string of characters that matches your search query. To search for a string, you must enclose it in double quotes.

The general Syntax of the command is:

**$ grep \[options\] \[pattern\] \[/path/to/file\]  
where \[options\] parameter contains generic options to control the search and \[pattern\] contains string that we want to search.**

If you are looking for a file that contains a word, which you suspect might be in your any specific directory, you can search for it using the above command syntax in Terminal.

For instance, to search for a file that contains the word “tintin” and we think that file might be in our **Downloads** folder, we can use the following command to locate that file.

**$ grep -r –i “tintin” /home/tin/Downloads**

![Search for text in files with grep command](images/word-image-119.png)

Where

**\-i is used to ignore case distinctions**

**–r is used to search for the specified directory recursively**

Search for Multiple words

You can also search for multiple strings simultaneously. You have to use backslash “\\” and pipe sign “|” characters among your strings.

For instance to search for two strings “tintin” and “ping”, we can use the following command in Terminal:

**$ grep –r –I “tintin\\|ping” /home/tin/Downloads**

![Search for Multiple words](images/word-image-120.png)

So, that was the brief overview of how you can search for files using the command line in Ubuntu. In this article, we have seen three useful command line methods to search for files. You can choose any one of these methods depending upon the search speed and conditions.
