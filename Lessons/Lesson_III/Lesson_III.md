# Lesson III: Accessing, and moving data to and from your new computer (45min)

> Anna Prentice has now had her Drupal web server up and running for a few weeks. And she's very happy! 
> 
> But on opening her newspaper one morning, she finds that there's a major Internet scare - hackers have found a 
> weakness that they are exploiting!
>
> Remembering that she is responsible for her web server, she decides that the software running on the machine needs 
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

**Q** Anna's virtual machine in the cloud has no keyboard, monitor or mouse. Does she have any hope of updating the 
software on her machine?

Hold up a Red sticky note if you think that she is stuck.
and a Green one if you think that, somehow, somewhere, there is hope for her.

**A** The Greens have it: there's always hope!

In the old days, because computing was so expensive, many people would share a single computer by means of terminals. 
A terminal was a keyboard and a screen, and many terminals could be attached to a single computer.
 
These terminals supported a basic text based interface that allowed you to do work on the computer it was attached to.

You'll be unsurprised to learn that with the passage of time, people wrote programs that emulated these terminals. So 
one computer could act as the terminal for another computer - or even itself!

So you can run a terminal application on your computer to do work on your own computer. You might recognize it as the
"Command Line"

**Q** Who here is running MS-Windows? 

Hold up a Red sticky note if you are.
and a Green one if you are aren't.

**Exercise 1a**

The windows command line doesn't work with the Linux operating system that Anna is using on the NeCTAR cloud.

Microsoft are planning to change this, but for the time being Windows users have to follow an alternate path.

So we are going to have take a short break for the Windows users to install CygWin (http://cygwin.com/install.html) -
making sure to include the `openssh` package as part of the installation.

Once that's done hold up a green card.

**Exercise 1b**

Find and run the terminal program, or command line, on your computer.

OSX users can do a Spotlight Search for 'terminal'

**No: this won't work with cygwin!**

Once it's running try the following commands:

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

So Anna's hope comes in the form of the terminal application: She can run it on her local machine, and connect to 
her remote Drupal server.

**Exercise 2**

Now in the last session we shut down own servers. If we're going to follow in Anna's footsteps, we need to relaunch
our Drupal servers.

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
you to use the text based interface on the target machine. It kind of teleports the target machine terminal to yours…

Think of `ssh` as your cloud login command.

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
* Cascade to other devices if *you* use the same password across devices. And if you’re spawning multiple computers
  on the cloud are you going to give them all the same password, or somehow ‘remember’ different ones?

If it’s your machine, what happens if you forget your password? There is no higher authority to unlock it for you…

And if it’s your machine, it’s granting access to the whole machine. If someone hacks it you could find
the security services knocking on your door at some early hour. And if that prospect doesn't scare you, you're a 
better person than I!

Ok. This is the basic form our `ssh` command will take:

```bash
ssh  -i <key> <user_id>@<address>
```

So here:

* the `key` is the path to and the key file itself
* the `user_id` is the name of the user account on the remote machine that we are connecting as.  
  Different operating systems have different default user accounts.
* the `address` is the IP address of the Virtual Machine that we read off of the dashboard.

In my case that would be:

```bash
ssh -i keys/tut_dev.pem ubuntu@144.6.225.224
```

**Question 1**

Nectar have an image catalogue that gives information about the images they provide. It can be found at:

https://wiki.rc.nectar.org.au/wiki/Image_Catalog
 
Have a look at it. What operating system do you think our Drupal server is based on?

**Choices**

A Fedora
B Debian
C Centos
D Ubuntu
E Scientific Linux

**Answer 1**

D

**Question 2**

Ok: a bit of a more challenging question. What is the default user for the Ubuntu OS?

**Choices**

A ubuntu
B windows
C debian
D fedora
E ec2-user 

**Answer 1**

A

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
chmod u=rw,go-rwx keys/tut_dev.pem 
```

**Exercise 4**

Modify the permissions on your key file so that only you can read or write it.
Then issue the `pwd` command to see what directory you are in.
Retry the ssh command.

Hopefully, you are now met with something along following lines

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

Finally, we are going try and update our web server. Try to execute the first command in the set:

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

**Exercise 7**

When you are finished working on your virtual machine, do the following:

Type `exit`

You should see the following:

```bash
logout
Connection to <some_ip_number> closed
```

You have now closed the ssh connection to the remote machine. If you are not convinced, type `pwd` to see that your
terminal is now back on your local machine. The teleportation magic is over!

Hold up a Green card if you are back on your local machine.
And a Red card if you are not.

**Exercise 8**

Return to the security group in the dashboard and remove the ssh rule.

Now try to ssh into your virtual machine again.

What happens?

Hold up a Green card if you have managed to teleport into your remote machine..
And a Red card if you haven't.

I'm hoping to see a sea of Red!

**Exercise 9**

Now return to the security group and re-add a rule that allows ssh.

Try to ssh into your virtual machine again.

What happens?

Hold up a Green card if you have managed to teleport into your remote machine..
And a Red card if you haven't.

I'm hoping to see a sea of Green!

The takeaway: Security groups can stop you from accessing your server if they aren't configured properly. 

It is also a good idea to remove the ssh rule from the security group when you don't kneed it. This stops hackers from 
trying to access your machine.

> Whilst on the machine, Anna realises that she doesn't have a backup of the site that she's created. And thinks
> that it would be a good time to create one!

There is a command line program you can use called `scp` (**S**ecure **c**o**p**y)

It can move files to, or fetch files from, different machines. It is built on top of `ssh`.

This `scp` command will copy the file named `notes.txt` from the home directory of the remote machine to the local one:

```bash
$ scp username@remote_machine_address:notes.txt /local/directory 
```

Where of course `username` is the default account on the remote machine, and `remote_machine_address` is either its
IP number or its domain name.

This scp command will copy the file named notes.txt from the local machine to the remote machine:

```bash
$ scp foobar.txt username@remote_machine_address:/remote/directory 
```

Looking at the two commands you can see that the source for the transfer is on the left, and the target on the right.
You can use a wildcard denoted by the asterisk character (*) to copy multiple files in one go.

A gotcha to look out for: if copying a file from your machine to a remote machine, your account on the remote machine 
must have permission to write in the target directory.

**Exercise 8**

I want everyone to create a file named, say, `helpme.txt` and then copy it onto the remote server.

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

**Exercise 9**

SCP is a good tool to have around. But a graphical environment is even better.

Go to [CyberDucks home page](https://cyberduck.io/) and download the client file that is correct for your laptop.

Then run it.

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

**Exercise 10**

![First steps in adding a bookmark](images/AddBookmark.png "First steps in adding a bookmark")

Right click and select "New Bookmark"

![Basic bookmark dialogue](images/BasicBookmark.png "Basic bookmark dialogue")

In the resultant dialogue select SFTP.
Provide a descriptive nickname for the bookmark.

For the Server provide the ip number of the machine read off of the dashboard.
Add 'ubuntu' as the Username.

Expand the 'More Options' drop down.

![Complete bookmark dialogue](images/CompleteBookmark.png "Complete bookmark dialogue")

Select the "Use Public Authentication" checkbox, and in the resultant dialogue select the key file you used when you
launched the server. If in doubt, you can have a look at the server information tab on the dashboard.

Now close the dialogue. To connect to the server right click on the bookmark you've just created and select 
"Connect to Server". All going well, a ruled plain window should replace the pane showing the bookmarks. 

You should now be able to drag and drop files between the two machines! See if you can drag `helpme.txt` back to your
local machine. You can even edit it in place!

Hold up a Green card when you've managed to do this.
And a Red card if you need help.







