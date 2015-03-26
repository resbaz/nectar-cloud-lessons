#Lesson III Accessing, and moving data to and from the VM (45min)

**Objective:** 

By the end of this lesson, participants will be able to securely access a running VM via ssh (without using passwords), 
and be able to move files to and from it using scp.

**Motivation:** 

In order to work with NeCTAR VM's, researchers need to know to access their VM's so that they can do basic maintenance.
They also need to know how to transfer files between their desktop and their VM. 

**Story**

Anna Prentice has been working on her RStudio server instance for a while. And is becoming a little worried that she
hasn't done any security upgrades. She also knows that there are files on the VM that should be backed up off of the 
machine. There is also a data set that she wants to move onto the machine. 

**Task**

The students will relaunch the machine that they shut down in the previous example, then they will ssh into it,
create a 'backup', then scp the backup onto the researchers client machine. Finally they will scp a file from their
machine onto the VM.

**Covers**

SSH, SCP

**Concepts**

The shell, moving files between machines.

**Notes:** 

The problem with passwords (sample password guessing program?)

* http://www.hashhunters.net/
* http://www.md5hashgenerator.com/

Bash guide:

* http://mywiki.wooledge.org/BashGuide
* http://steve-parker.org/sh/sh.shtml 
* http://code.tutsplus.com/articles/10-terminal-commands-that-will-boost-your-productivity--net-14105

**To discuss:** 

 Password access, its downsides, keys and ssh, encryption of network access (and why) scp. 
 
 In discussing passwords, do discuss why passwords are deemed acceptable for web sites, but not here. 
 Discuss automated attacks, how passwords are salted, and how they easy they are to reverse engineer these days. 
 Perhaps run a demo password cracking program to frighten them... 
 
 Also point out that it’s the whole machine at risk here, not just a users account. 
 When discussing ssh access, make sure to point out that we are connecting to the remote machine via the network. 
 That the keyboard isn’t driving the VM locally: that the terminal is more a screen scrape of a remote machine.

**Links for students:** 

* http://code.tutsplus.com/tutorials/ssh-what-and-how--net-25138
* http://software-carpentry.org/v5/novice/shell/index.html
* http://software-carpentry.org/v4/shell/ssh.html


**Supporting material:** 

An image that has RStudio server on it.

**Preconditions:** 

* A web browser
* Ssh/scp support in a command line shell on the students desktop.
* Some disk space.

