---
title: "Ruby on Rails Development Setup for Beginners"
date: 2022-10-23
categories: 
  - "r-o-r-development-setup"
  - "ruby-on-rails"
coverImage: "ruby-on-rails-development-blog-img-main.jpeg"
---

Today, we will install Ruby on Rails (RoR) on my **Dell E7240 Workstation Laptop** **i7 8gb 256 SSD** running a linux operating system ([Ubuntu 22.04.1 LTS](https://releases.ubuntu.com/jammy/)). Moving forward, RoR is compatible with other operating systems ie **Windows, MacOS**. This guide will help in installing RoR with a simple step-by-step process. Your installation may differ, for other operating systems refer to [this site](https://gorails.com/setup).

# Introduction

I am new to developing and have been using Ubuntu 22.04.1 LTS for my future projects. This overview is a reminder of the steps and information needed to get the environment and dependencies installed for RoR so you can get started.

**Ruby on Rails** is an excellent framework for web application development. For those of you who are new to RoR, like me, you will need to install several different applications (referred to as dependencies) to ensure this runs smoothly.

## Tools You Will Need[](https://pagertree.com/2021/04/21/rails-dev-setup/#tools-you-will-need)

Here are the packages, tools, and databases we will be installing:

- git - **A distributed version control system**.

- Create a GitHub account - **Our preferred vendor that allows us to host git repositories in the cloud**.

- SSH Key - **Secure Shell is a protocol that allows users to control and modify their remote servers over the Internet while ensuring security**.

- HomeBrew \- **Software package manager that simplifies the installation process for Mac OSX and Linux**.

- rbenv - **A tool that manages, installs and runs multiple versions of Ruby**.

- Visual Studio Code - **My preferred code editor**.

- Postgres - _A_ [relational database](https://www.codecademy.com/articles/what-is-rdbms-sql) **used for long term storage**.

- Redis\- **A** [key-value database](https://en.wikipedia.org/wiki/Key%E2%80%93value_database) **used for short term storage (caching**).

- NodeJS - **Javascript runtime environment. Runs on the Chrome V8 engine and executes javascript code outside of a web browser.**

- yarn - **A more secure npm (node package manager - gets installed with NodeJS)**.

# Step-By-Step Directions

Here are some steps to get your development environment setup and all of the dependencies installed.

**Quick Note**: For addition help guide go here: [**Linux**](https://gorails.com/setup/ubuntu/22.04) **[MacOS](https://gorails.com/setup/ubuntu/22.04).** **[Windows](https://gorails.com/setup/windows/10)**

## Install git[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-git)

**You will need to run the commands below in your terminal to** **install git**.

```
$ sudo add-apt-repository ppa:git-core/ppa -y
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install git -y
```

Remember git is the program for distributed version control, and **[GitHub](https://github.com/)** is our preferred vendor. So if you haven’t create an account with GitHub.

## Create SSH Key[](https://pagertree.com/2021/04/21/rails-dev-setup/#create-ssh-key)

You will need to [create an SSH key](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) and connect it to GitHub. We will first check to see if there are any existing SSH keys. Run this command to see if there are any pre-existing SSH keys.

```
$ ls -al ~/.ssh
```

**If there are none, you will then run the next commands to generate a new one.**

```
$ ssh-keygen -t ed25519 -C "your_email@example.com"

Quick Note: remember to add the email address used in your GitHub account! 
```

**Next, press** **ENTER**.

```
> Enter a file in which to save the key (/home/you/.ssh/id_ed25519): [Press enter]
```

**Now you need to add your information** **for a passphrase or not if you don't wish too.**

```
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again] 
```

Once you have the SSH key generated you will need to add it to the ssh-agent to manage. In the command line enter:

```
$ eval "$(ssh-agent -s)
> Agent pid 59566
```

**To add it**, **ENTER**.

```
$ ssh-add ~/.ssh/id_ed25519
```

**The final step is to add it to GitHub.** Follow [this guide](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account) to do so.

## Install HomeBrew[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-homebrew)

**[Homebrew](https://brew.sh/)** is a package manager (**similar to apt-get**) that helps us install other packages to our system. To get the **Homebrew** package installed, you will have to run the below command:

**Homebrew** Help go here: **[Linux](https://docs.brew.sh/Homebrew-on-Linux#requirements)** **[MacOS](https://docs.brew.sh/Installation#macos-requirements)** **[Windows](https://docs.brew.sh/Installation#linux-or-windows-10-subsystem-for-linux)**

```
Linux

$ sudo apt install linuxbrew-wrapper  

Quick note: if this dosent work for you then make sure you have $(curl already installed on your system!

MacOS / Linux ( as per the Homebrew Offical Website )

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Installing Ruby Environment[](https://pagertree.com/2021/04/21/rails-dev-setup/#installing-ruby-environment)

### Install rbenv[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-rbenv)

Now things to note, **[rbenv](https://github.com/rbenv/rbenv)** is a tool that will help us manage installing and running multiple version of Ruby. To install rbenv, run the following:

```
$ brew install rbenv ruby-build
```

Now, **rbenv** should be installed, but we also need to add some startup scripts to your bash profile, so that your terminal uses **rbenv** instead of the system wide Ruby version.

```
$ echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
$ source ~/.bash_profile

Quick Note: If your using a new version of MacOS then ./bash_profile will be ./zshrc instead
```

## Install Ruby 3.0.1[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-ruby-301)

So, let’s start by using this (released on December 25th 2020) version of **Ruby (3.0.1)**. To install this version of Ruby, we will use rbenv. Run the following in your terminal:

```
$ rbenv install 3.0.1 -v
$ rbenv rehash
$ rbenv global 3.0.1 # set the global
$ ruby -v

```

## Installing Ruby v3.1.2 - latest version

**Choose the version of Ruby you want to install:**  

**3.1.2** (current release since: 12 April 2022**(Recommended)**   

**Older Versions:** **3.0.4   2.7.6   2.6.10   2.5.9   2.4.10   2.3.8   2.2.10   2.1.10   2.0.0-p648**  

The first step is to install some **dependencies** for Ruby and Rails.

To make sure we have everything necessary for **Webpacker** support in Rails, we're first going to start by adding the **Node.js** and Yarn repositories to our system before installing them.

```
sudo apt install curl
curl -sL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update
sudo apt-get install git-core zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev nodejs yarn
```

### **Next we're going to be installing Ruby using a version manager called** **Rbenv**.

Installing with `**rbenv**` is a simple two step process. First you install `**rbenv**`, and then `ruby-build`:

```
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
```

**To install Ruby and set the default version, we'll run the following commands**:

```
rbenv install 3.1.2
rbenv global 3.1.2
```

**Confirm the default Ruby version matches the version you just installed**.

```
ruby -v
```

**The last step is to install Bundler**

```
gem install bundler
```

rbenv users need to run `rbenv rehash` after installing bundler.

## Install Visual Studio Code[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-visual-studio-code)

You can follow the directions in the [Visual Studio Code](https://code.visualstudio.com/) link to get the correct version installed on your device.

## Install Postgres[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-postgres)

[Postgres](https://www.postgresql.org/) will be our relational database preference for our RoR setup. To install:

```
$ brew install postgresql
```

## Install Redis[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-redis)

[Redis](https://redis.io/) is our key value database that RoR uses for caching.

```
$ brew install redis
```

## Install NodeJS[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-nodejs)

The link will take you through the steps to get the correct version of [NodeJS](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) installed to your device and will give a thorough understanding.

## Install Yarn[](https://pagertree.com/2021/04/21/rails-dev-setup/#install-yarn)

For the final step we will be installing the package manager [Yarn](https://yarnpkg.com/)) by running the command below.

```
$ brew install yarn
```

# Conclusion

Now, RoR is a great development environment. It is easy to navigate, scalable, and is excellent for solo developers wanting to learn Full Stack development and how it all works together.

I will be documenting my path on this developer journey by doing the "[Odin Project - "Ruby on Rails](https://www.theodinproject.com/paths/full-stack-ruby-on-rails?)" track: and also some other learning paths from **Udemy**...

[the-complete-ruby-on-rails-developer-course/](https://www.udemy.com/course/the-complete-ruby-on-rails-developer-course/)

[learn-to-code-with-ruby-lang/](https://www.udemy.com/course/learn-to-code-with-ruby-lang/)

[professional-rails-5-development-course/](https://www.udemy.com/course/professional-rails-5-development-course/)

[comprehensive-ruby-programming-tutorial/](https://www.udemy.com/course/comprehensive-ruby-programming-tutorial/)

I hope that who ever finds this may it guide you on the journey through web & software development.

**lwa.{dev}** for **R.O.R**
