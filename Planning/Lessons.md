# The lesson plan for a one day NeCTAR "train the researcher" event.

## Target Audience

Researchers and their assistants  who want to use the cloud. They must have some familiarity with computers and the 
command line, but no knowledge of the cloud/virtualization.

## Overall Objective

To give the target audience a better understanding of how the cloud and virtualization work, and to understand the 
trade offs that they are making in running applications on the cloud.

## Philosophy

We are trying to create a teaching experience that makes the students more active, and in which they get to 
organize the material they learn themselves. [Because...](http://mindhacks.com/2011/10/24/make-study-more-effective-the-easy-way/)

# On the day

(* Click through the lessons below for learning plans *)

> 9am - Start 

* [Lesson I: OpenStack, mapped by the dashboard](#lesson-i)
* [Lesson II: Your free computer: up and running](#lesson-ii)
* [Lesson III: Accessing and updating your new computer](#lesson-i)

> 10h30am - 11h00am: Morning Tea

* [Lesson IV: Moving data to and from your new computer](#lesson-iv)
* [Lesson V: We can still run our graphical applications](#lesson-v)

> 12h00am - 1h00pm: Lunch

* [Lesson VI: Snapshots: Backups, vertical scaling](#lesson-vi)
* [Lesson VII: transient storage (don’t rely on it!) and sharing](#lesson_vii)

> 3h00pm - 3h30: Afternoon Tea

* [Lesson VIII: The object store](#lesson-viii)
* [Lesson IX: Securing and maintaining your instance](#lesson-ix)

If time permits, possibly a "bringing it all together" grand exercise?

> 4h30pm - Day end.

We have a list of [stretch goals](stretch_goals.md) that we thought we might get to if time permitted. It would
appear that time doesn't permit...

#Lesson I 

**Topic:** OpenStack, mapped by the dashboard

## Learning objectives 

By the end of this lesson participants will be familiar with the basic parts of OpenStack and be able to 
locate them on the dashboard. They will also understand that the machines they launch are virtual.

## Motivation

A researcher needs to understand the Dashboard and the underlying parts of OpenStack, in order to use it.

## Story

To motivate the students:

Two researchers blow 20K of grant money on computers - that they didn't have to, had NeCTAR been around!

##Tasks

To find and map the parts of the dashboard to  their respective OpenStack components. Done as a guided tour of 
the dashboard, rather like a tour guide would do...
 
## Covers

All major OpenStack components, Horizon, the AAF & Allocations, and how to get support if help is needed. 

## Concepts

Modular nature of OpenStack, Glance, Nova, Allocations, Virtualization, Key Pairs, Security Groups, IP allocation.

## Notes 


## To discuss

The basics of virtualization, the parts of OpenStack at a very high level, and the allocations screen. 

How the image is passed from Glance to Nova.

Its worthwhile driving home that to use the cloud, you do need to get your head around some key concepts; and that they 
are not difficult

Where to go to get help if you need it.

Introduce the concepts of Key Pairs and Security Groups, and IP allocation.

## Links for students


## Supporting material


## Preconditions

* an AAF account
* a web browser


#Lesson II

**Topic:** Your free computer: up and running

##Learning objectives

By the end of this lesson, participants will be able to locate and launch an image on the NeCTAR cloud.

##Motivation 

These are the basic steps required to successfully run a VM on the NeCTAR cloud. 

##Story

A researcher, Anna Prentice wants to set up a simple website, to share some data with the world. 

Now knowing the parts of the NeCTAR cloud, Anna decides to see if she can find an image available on the 
NeCTAR cloud can do this for her - and launch and play with it.

##Tasks

Create a security group, find the correct image, spin it up, connect to it with a web browser and then take it down

##Covers

Glance, Nova, Security Groups, Key Pairs, but now hands on.

##Concepts

Just goes over Lesson I again, but cover Security Groups in more detail

##Notes 

We'll do this by creating and using checklists to get the students through the steps.


##To discuss 

Security groups and CIDR's 

##Links for students 

* [An introduction to checklists](http://www.newyorker.com/magazine/2007/12/10/the-checklist)

##Supporting material

* An image that will launch a server of some kind (res_os_drupal7), made by the following recipe:
  [Creating The Image For The Workshop](../Resources/CreatingTheIMageForTheWorkshop.md)
* Checklists, placed in the [Resources](../Resources/) directory.

##Preconditions

* A web browser. Preferably a modern one that renders the PDF checklists.

#Lesson III

**Topic:** Accessing and updating your new computer

##Learning objectives 

By the end of this lesson, participants will be able to securely access a running VM via ssh (without using passwords).
They will also be able to update their Ubuntu/Debian based VM's to the latest versions of the installed software, and
know how to add and remove rules to their security groups, hence blocking and allowing access to the VM.

##Motivation 

In order to work with NeCTAR VM's, researchers need to know to access their VM's so that they can do basic
maintenance.

They will also know the commands to use on Debian and Ubuntu based VM's to keep the installed software up to date.
Hence improving the security of their VM's.

This knowledge is also a foundation for securely moving files between a VM and the researchers desktop, which is
covered in a later lesson.

##Story

Anna Prentice has found that her Drupal instance is suitable for the publishing that she wants to do. 

But she is becoming a little worried that she hasn't done any security upgrades on it since she launched it. 

##Tasks

The students will relaunch the machine that they shut down in the previous example, then they will ssh into it, and
perform the needed security upgrades.

##Covers

SSH, `apt-get`, `sudo`, bash commands

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

Cygwin isn't the best solution: there are possibly other, easier solutions for us to use...

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

* An image that will launch Drupal (res_os_drupal7), made by the following recipe:
  [Creating The Image For The Workshop](../Resources/CreatingTheIMageForTheWorkshop.md)

##Preconditions 

* A web browser
* Ssh/scp support in a command line shell on the students desktop.
* Some disk space.
* If on windows, the ability to install Cygwin

#Lesson IV

**Topic:** Moving data to and from your new computer

##Learning objectives 

By the end of this lesson, participants will be able to securely move files to and from a running VM using scp and 
Cyberduck. This knowledge means that from now on moving data to and from NeCTAR servers should be simple to do!

##Motivation 

In order to work with NeCTAR VM's, researchers need to know how to securely move files between a VM and their desktop.

##Story

Anna Prentice knows that there are files on the VM that should be backed up off of the machine. 
So she uses Cyberduck to bring them down to her local desktop, where they can be kept as an off-site backup.

##Tasks

The students will first move a file to the server from their local machine by means of scp.

Next they will install Cyberduck, and use it to move files between the two machines.

##Covers

SCP, Cyberduck

##Concepts

Using the shell to transfer files, and using Cyberduck to move files.

##Notes 



##To discuss 



##Links for students 

 [CyberDuck](https://cyberduck.io/)

##Supporting material 

* An image that will launch Drupal (res_os_drupal7), made by the following recipe:
  [Creating The Image For The Workshop](../Resources/CreatingTheIMageForTheWorkshop.md)

##Preconditions 

* A web browser
* Ssh/scp support in a command line shell on the students desktop.
* Some disk space.
* The ability to install CyberDuck

#Lesson V

**Topic:** We can still run our graphical applications

##Learning objectives 

By the end of this lesson participants will know that they can, if need be, use graphical applications on the remote
systems.

##Motivation 

This is of use if a researcher wants to

* run an graphical application on a data set on the remote server
* browse the internet from the remote server (can avoid local blocks)
* etc.
 
##Story

Anna Prentice wants to view a website that her local institution has blocked. She realizes that she can do this via
her remote server, so this is what she sets out to do.

Anna then wants to edit a file she finds on the remote server. Rather than doing this with a command line editor she
opts to use a one of the nice friendly GUI editors that she is familiar with.

##Tasks

How to install applications on the server in the NeCTAR cloud, and how to run graphical ones using XWindows over ssh.

##Covers

SSH, X-windows, `apt-get install`

##Concepts

How to install applications on the server, how to use X-windows to run applications that require graphics support. 

##Notes 



##To discuss 



##Links for students 

https://help.ubuntu.com/community/SSH/OpenSSH/PortForwarding

##Supporting material 



##Preconditions 

* ssh/scp support in a command line shell on the students desktop.
* Some disk space.
* The ability to install XWindows


#Lesson VI

**Topic:** Snapshots, backups and vertical scaling

##Learning objectives 

By the end of this lesson participants will understand what happens when you make a snapshot of a running instance.
They will know why snapshots are a somewhat imperfect backup medium.

They will also see how to scale their machine to a larger one, and of course, shrink it down again. 

##Motivation 

The ability to make a copy of a running instance confers a whole lot of benefits: the ability to switch to a larger
machine if needed, the ability to share copies with others, and to make somewhat imperfect backups. 

##Story

Anna is aware that she needs to make backups of her site: so she chooses to do this using snapshots, even though its
not an ideal way of doing this.

Her kitten picture is taking the internet by storm, and she needs to move to a bigger server to cope with the load.
She does this by scaling her instance up.

##Tasks

They will make a snapshot of a running VM.

##Covers

Snapshots, vertical scaling.

##Concepts

That a snapshot is simply a copy of the images file system: but that making them does have an impact on the instance.
Not only that, if there are writes to the drive in progress, they can leave the copy in a faulty state. So to get a
high quality snapshot, disk activity has to be stopped and any buffers flushed. 

Snapshots can be used to move to a larger or smaller machine (vertical scaling).

##Notes 

Snapshots can take a fair amount of time depending on the system load. So the lesson might drag out because of this :(

##To discuss 



##Links for students 

http://wiki.libvirt.org/page/Snapshots
http://docs.openstack.org/openstack-ops/content/snapshots.html
http://physics.stackexchange.com/questions/32663/what-are-the-effects-of-cosmic-rays-on-consumer-electronics

##Supporting material 



##Preconditions 


#Lesson VII

**Topic:** Transient storage (don’t rely on it!) and sharing

##Learning objectives 

By the end of this lesson participants will know that transient storage is not saved when a snapshot is made.

They also learn how to share their snapshots with the greater world.

##Motivation 

Transient storage can take even experienced developers by surprise. Researchers should know that whilst it's
a great resource, it's not one that should be taken for granted: there is the risk that if you use transient
storage you could lose your data. Not something you would desire!

##Story

Disaster strikes: Anna had some notes on the transient file store. When her server dies, she finds that they are no
longer on the replacement instance. Oh woes!

Then a colleague wants to user her site has a foundation for his own kitten extravaganza. Anna gladly shares her backup
with him.

##Tasks

They will write a file to transient storage, then snapshot their instance. After that they will kill the instance
and then start up a new one based on the snapshot. The file on transient storage will be gone.

##Covers

Transient storage and sharing snapshots.

##Concepts

Transient storage is not captured as part of the snapshot process.

Snapshots can also be shared.

##Notes 

Snapshots can take a fair amount of time depending on the system load. So the lesson might drag out because of this :(

The effort required to create the file on the transient storage is large. Can it be simplified in any way?

##To discuss 



##Links for students 

http://wiki.libvirt.org/page/Snapshots
http://docs.openstack.org/openstack-ops/content/snapshots.html
http://physics.stackexchange.com/questions/32663/what-are-the-effects-of-cosmic-rays-on-consumer-electronics

##Supporting material 



##Preconditions 


#Lesson VIII

**Topic:** The object store

##Learning objectives 

By the end of this lesson participants will understand and be able to use the object store, and know some of the 
advantages that it confers.

##Motivation 

Having seen the horrors of transient storage, the researchers now want a more secure location for their data. 
The object store it is!

##Story

Anna Prentice wants a more secure storage location for her data. Knowing that the Object store makes redunant copies
she decides to put her data there.

##Tasks

The students need to upload their backup that they downloaded to their desktop to the Swift 
object repository. 

To do this this time they will user CyberDuck

## Covers

Using CyberDuck to connect to the object store.

## Concepts

Object Storage, redundancy etc..

## Notes 

## To discuss 

Swift, its three copies, out of 5, its eventually consistent nature, the differences between Swift and a hard drive. 
Also, the importance of an off site copy and the encryption of backups.

##Links for students 

* https://trac.cyberduck.io/wiki/help/en/howto/openstack
* https://community.runabove.com/kb/en/object-storage/how-to-distribute-static-content-with-object-storage.html

##Supporting material 

CyberDuck needs to be configured to work with Swift

##Preconditions 

#Lesson IX

**Topic:** Securing and maintaining your instance

## Learning objectives 

By the end of this lesson participants will understand the concept of a 'shared' security partnership. That
NeCTAR do a best effort attempt to secure the infrastructure, but that the instances themselves, and the backing up
of data on them is totally the researchers responsibility. The final responsibility for security lies with the 
researcher.

They will be a little more paranoid than they were coming into the lecture.

And will also have some some insight into how they can best maintain and secure their instances.

They can do this by knowing what they are running in the cloud, and they will learn of the need to monitor for 
updates and patches, that they can then apply.

## Motivation 

It's a scary world out there. Every new server that goes up is going to have automated scans hitting it regularly, all
looking for weaknesses.

## Story

What is the story that we giving our students to help explain the motivation?

## Tasks

What will the student do to learn this topic?

Configure ssh:

* Check and disable password-based SSH authentication (already done on NeCTAR's base images)

* Check and disable root account remote login (why is this not done by default? Why is it set to PermitRootLogin without-password ?)

* Explicitly allow/deny SSH for users (too complex)

* Use a non-standard port  (I'm not sure how valid this is these days?)

Configure sudo:

* Only allow sudo access for specific users (too complex)

* Ensure password access for sudo command (why is this not enabled? why are there multiple lines)

```bash
sudo visudo -f /etc/sudoers.d/90-cloud-init-users
```

And set to `ubuntu ALL=(ALL) ALL`

Enable automated security updates. (why a different command ie: apt-get upgrade vs apt-get dist-upgrade?)

Find the notification mailing lists for the software they are using, and know how to subscribe.

## Covers

What material is covered?

## Concepts

What concepts are covered?

## Notes 

Anything that the presenter should be aware of.

## To discuss 

The points of knowledge that the students should understand in order to master the topic

## Links for students 

[A brief history of ssh](https://servercheck.in/blog/brief-history-ssh-and-remote-access)
[Securing ssh and sudo on your server](http://lowendbox.com/blog/securing-your-server-ssh-and-sudo/)
[NeCTAR security recommendations](https://support.rc.nectar.org.au/docs/security-guidelines)
http://askubuntu.com/questions/27559/how-do-i-disable-remote-ssh-login-as-root-from-a-server
https://help.ubuntu.com/community/SSH/OpenSSH/Configuring
http://askubuntu.com/questions/81585/what-is-dist-upgrade-and-why-does-it-upgrade-more-than-upgrade

## Supporting material 

What is needed to do the task

## Preconditions 

What the students need to bring to the table.

