# Lesson IX: Securing and maintaining your instance (45 min)

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

