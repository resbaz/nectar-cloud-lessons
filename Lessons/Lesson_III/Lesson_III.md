# Lesson III Accessing, and moving data to and from the VM (45min)

> Anna Prentice has now had her RStdio server up and running for a few weeks. And she's very happy! 
> 
> But on opening her newspaper one morning, she finds that there's a major Internet scare - hackers have found a 
> weakness that they are exploiting!
>
> Remembering that she is responsible for her RStudio server, she decides that the software running on the machine needs 
> to be urgently updated.
> 
> Remembering the checklist used to launch a machine performs an update by issuing the following commands:
> 
> ```bash
> apt-get update && apt-get -y upgrade
> ```
> 
> She knows that she has to issue this set of commands again - this time on the instance.

## The Terminal 

**Q** Anna's virtual machine has no keyboard, monitor or mouse. Does she have any hope of updating the software on her
machine?

Hold up a Red sticky note if you think that she is stuck.
and a Green one if you think that, somehow, somewhere, there is hope for her.

**A** The Greens have it: there's always hope!

In the old days, because computing was so expensive, many people would share a single computer by means of terminals. 
A terminal was a keyboard and a screen, and many terminals could be attached to a single computer.
 
These terminals supported a basic text based interface that allowed you to do work on the computer it was attached to.

You'll be unsurprised to learn that with the passage of time, people wrote programs that emulated these terminals.

So you can run a terminal application on your computer to do work on your computer.

**Exercise 1**

Find and run the terminal program on your computer.

Once its running try the following commands:

```bash
pwd
```

`pwd` is shorthand for **p**rint **w**orking **d**irectory

```bash
ls
```

`ls` is shorthand for **l**i**s**t directory contents

```bash
man ls
```

man is shorthand for ***man***ual. Arrow keys scroll, and the 'q' key closes the help.

As ever, hold up a Green card when you're done
And a Red card if you need help.

Commands issued via terminals have the following advantages:

* They are terse
* If you know what you’re doing it’s faster to type than to point with a mouse
* They keep a history of your commands
* You can easily replay commands
* It is simple to automate
* If you can type, you can use it...
* Easy to communicate how to do things with other people.

But your terminal program can also be used to connect to another computer.

So Anna's hope comes in the form of this application: She can run it on her local machine, and connect to the remote
RStudio server.

**Exercise 2**

Now in the last session we shut down own servers. If we're going to follow in Anna's footsteps, we need to relaunch
our RStudio servers.

Remember, this time round we don't need to create a security group or a key: they are already there. So reuse them
when launching your VM.

Hold up a Green Card when you're ready to move on,
And a Red card if you need help.

## ssh

The program we are going to connect to the server with is: 

```bash
ssh
```

`ssh` stands for **s**ecure **sh**ell. It connects a terminal on one machine to another target machine, thus allowing 
you to use a text based interface on the target machine. It kind of teleports the target machine terminal to yours…

`ssh` uses public key cryptography to connect with the target machine. 

Remember those public/private key pairs I've been going on about?

This is where they come in to play. Remember: 

"When NeCTAR fire up a machine for you, they inject the public key into your machine. Anyone with the private key will 
be able to communicate and control that machine. ... You want to keep your private key in a secure location."
 
Why aren't we using passwords?

Well, they have problems:

* One more thing to remember (and forget)
* Need to be ever more complex
* Easy to crack (especially social engineering)
* Prone to being shared
* Cascade to other devices if *you* use the same password across devices. And if you’re spawning multiple VM’s are  
  you going to give them all the same password, or somehow ‘remember’ different ones?

If it’s your machine, what happens if you forget it? There is no higher authority to unlock it for you…

And if it’s your machine, it’s access to the whole machine: not just R scripts. If someone hacks it you could find
the security services knocking on your door at some early hour. And if that prospect doesn't scare you, you're a 
better person than I!

Ok. This is the basic form our `ssh` command will take:

```bash
ssh  -i <key> <user_id>@<address>
```

In my case that would be:

```bash
ssh -i .ssh/tut_dev.pem ubuntu@144.6.225.224
```

So here:

* the `key` is the path to and the key file itself
* the `ubuntu` user is the name of the user on the remote machine that we are connecting as.  
  Different operating systems have different default users. For the RStudio server it is this user.
* the address I'm using is the IP address that we read off of the dashboard.

**Question 1**

Nectar have an image catalogue that gives information about the images they provide. It can be found at:

https://wiki.rc.nectar.org.au/wiki/Image_Catalog
 
Have a look at it. What operating system do you think our RStudio server is based on?

**Choices**

A Fedora
B Debian
C Centos
D Ubuntu
E Scientific Linux

**Answer 1**

D

**Question 2**

Ok: a bit of a more challenging question. What is the default user for the Scientific Linux OS?

**Choices**

A ubuntu
B windows
C debian
D fedora
E ec2-user 

**Answer 1**

E 

**Exercise 3**

If everyone could try to connect to their server using the ssh command, that would be wonderful.
BTW, I'm hoping that you all fail - with the error message along the lines of: 

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0777 for '.ssh/tut_dev.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
bad permissions: ignore key: .ssh/nectar_dev.pem
ubuntu@144.6.225.224's password: 
```

Hold up a Green card when you've reached this error message.
And a Red card if you need help.

What's going on here? Anyone want to hazard an explanation?

The error message is very descriptive. ```ssh``` is rejecting your key file because anyone who has access to your
machine can read it. You need to tighten up the permissions on this file so that only you can access it.

Hit control-c to exit the password prompt.

The command ```chmod``` **ch**ange file **mod**e allows you to set the permissions on your files.

The basic form is

```bash
chmod <mode> <file>
```

So in my case, allowing me (the user) to be able to read and write the file, and to exclude the group and others from
being able to read, write or try to run (execute) it, the command would be:

```bash
chmod u=rw,go-rwx .ssh/tut_dev.pem 
```

**Exercise 4**

Modify the permissions on your key file so that only you can read or write it.
Then issue the `pwd` command to see what directory you are in.
Retry the ssh command.

Hopefully, you are now met with the following

```bash
Welcome to Ubuntu 14.04.2 LTS (GNU/Linux 3.13.0-36-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
Last login: Mon Mar 30 01:27:13 2015 from hqrouter.vpac.org
ubuntu@rstudio:~$ 
```

Re-issue the `pwd` command to convince yourself that are indeed now teleported into the remote machine.

Hold up a Green card when you are convinced you have a shell into the remote machine.
And a Red card if you need help.

**Exercise 5**

Finally, we are going try and update our RStudio server. Try to execute the first command in the set:

```bash
apt-get update
```

Again, something dread full has gone wrong! You should be met with the message:

```bash
E: Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)
E: Unable to lock directory /var/lib/apt/lists/
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
```

Hold up a Green card when you've reached this error message.
And a Red card if you need help.

You are seeing this error because you are trying to perform system administration, and the ubuntu user you signed in 
as is not the super user normally allowed to do system administration.

But don't panic!

The `sudo` command (**s**uper **u**ser **do**) comes to your help. It allows the ubuntu user to run commands with
the security privileges of the super user.

**Exercise 6**

Try to execute the command again, this time with `sudo`:

```bash
sudo apt-get update
```

You should now see a whole lot of gets scrolling by, as the operating system updates its lists of installed and 
available software.

Once done, execute the command:

```bash
sudo apt-get upgrade
```

If your system has software on it that needs an upgrade you will be met by a request to perform the upgrade. Something
like:

```bash
After this operation, 4,096 B of additional disk space will be used.
Do you want to continue? [Y/n]
```

In this case, reply, 'Y'.

Hold up a Green card when you've done this.
And a Red card if you need help.

Now we've replicated the steps Anna had to undertake in order to run the upgrade on her machine.

> Whilst on the machine, Anna realises that she doesn't have a backup of the scripts that she's created. And thinks
> that it would be a good time to create some!













