# Lesson VII: Securing and maintaining your instance (45 min)

## Learning objectives 

By the end of this lesson participants will understand the concept of a 'shared' security partnership. That
NeCTAR do a best effort attempt to secure the infrastructure, but that the instances themselves, and the backing up
of data on them is totally the researchers responsibility. The final responsibility for security lies with the 
researcher.

They will also have some some insight into how they can best maintain and secure their instances.

They can do this by knowing what they are running in the cloud, and they will learn of the need to monitor for 
updates and patches, that they can then apply.

## Motivation 

Why does the researcher need to learn this?

## Story

What is the story that we giving our students to help explain the motivation?

## Tasks

What will the student do to learn this topic?

Configure ssh:

* Check and disable password-based SSH authentication
* Check and disable root account remote login
* Explicitly allow/deny SSH for users
* Use a non-standard port

Configure sudo:

* Only allow sudo access for specific users
* Ensure password access for sudo command

Possibly enable automated security updates.

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
[Fail2ban](http://www.fail2ban.org/wiki/index.php/Main_Page) (is installed by default on NeCTAR images)
https://en.wikipedia.org/wiki/Fail2ban
https://www.digitalocean.com/community/tutorials/how-to-protect-ssh-with-fail2ban-on-ubuntu-12-04

## Supporting material 

What is needed to do the task

## Preconditions 

What the students need to bring to the table.

