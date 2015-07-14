#Lesson III: Accessing and updating your new computer (30 min)

##Learning objectives 

By the end of this lesson, participants will be able to securely access a running VM via ssh (without using passwords).
They will also be able to update their Ubuntu/Debian based VM's to the latest versions of the installed software, and
know how to add and remove rules to their security groups, hence blocking and allowing access to the VM.

##Motivation 

In order to work with NeCTAR VM's, researchers need to know to access their VM's so that they can do basic maintenance.
They will also know the commands to use on Debian and Ubuntu based VM's to keep the installed software up to date. Hence
improving the security of their VM's.
This knowledge is also a foundation for securely moving files between a VM and the researchers desktop, which is covered
in the next lesson, Lesson IV.

##Story

Anna Prentice has found that her Drupal instance is suitable for the publishing that she wants to do. 

But she is becoming a little worried that she hasn't done any security upgrades on it since she launched it. 

##Tasks

The students will relaunch the machine that they shut down in the previous example, then they will ssh into it, and
perform the needed security upgrades.

##Covers

SSH, `apt-get`, `sudo`

##Concepts

The shell, some shell commands, how to update a linux server, and the power of `sudo`

##Notes 

The problem with passwords (sample password guessing program?)

* http://www.hashhunters.net/
* http://www.md5hashgenerator.com/

Bash guide:

* http://mywiki.wooledge.org/BashGuide
* http://steve-parker.org/sh/sh.shtml 
* http://code.tutsplus.com/articles/10-terminal-commands-that-will-boost-your-productivity--net-14105

##To discuss 

 Password access, its downsides, keys and ssh, encryption of network access (and why) scp. 
 
 In discussing passwords, do discuss why passwords are deemed acceptable for web sites, but not here. 
 Discuss automated attacks, how passwords are salted, and how they easy they are to reverse engineer these days. 
 Perhaps run a demo password cracking program to frighten them... 
 
 Also point out that it’s the whole machine at risk here, not just a users account. 
 When discussing ssh access, make sure to point out that we are connecting to the remote machine via the network. 
 That the keyboard isn’t driving the VM locally: that the terminal is more a screen scrape of a remote machine.

##Links for students 

* http://code.tutsplus.com/tutorials/ssh-what-and-how--net-25138
* http://software-carpentry.org/v5/novice/shell/index.html
* http://software-carpentry.org/v4/shell/ssh.html
* http://en.wikipedia.org/wiki/Secure_Shell
* [NeCTAR's image catalogue](https://wiki.rc.nectar.org.au/wiki/Image_Catalog)
* http://en.wikipedia.org/wiki/Superuser
* http://www.slashroot.in/secure-shell-how-does-ssh-work
* https://www.digitalocean.com/community/tutorials/understanding-the-ssh-encryption-and-connection-process

A great link on debugging ssh issues on the NeCTAR cloud:
https://espaces.edu.au/vwrangler/nectar-topics/troubleshooting/troubleshooting-ssh-access-to-a-nectar-instance


##Supporting material 

An image that has Drupal and a backup script on it.

##Preconditions 

* A web browser
* Ssh/scp support in a command line shell on the students desktop.
* Some disk space.
* If on windows, the ability to install Cygwin

