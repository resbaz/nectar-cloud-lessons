-- *Slide* --

# Lesson III: Accessing and updating your new computer (30 min)

-- *Slide End* --

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

-- *Slide* --

## Anna wants to run

```bash
apt-get update && apt-get -y upgrade
```

-- *Slide End* --

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

-- *Slide* --

## Question 1

Those running Microsoft Windows...

Yes, You!

Did you install Cygwin?

-- *Slide End* --

Hold up a Red sticky note if you didn't.

**A** We are hoping to see none. If there are some, well. Sigh.  Get them to install it whilst we plough on.

To all you Windows users: the Windows command line doesn't work with the Linux operating system that Anna is using on 
the Research Cloud.

Microsoft are planning to change this, but for the time being Windows users have to follow an alternate path.

That's why in the prerequisites we asked Windows users to install Cygwin. It's a tool that gives you a terminal you
can use on Linux computers.

Ok: Before we go any further, we are going to perform a very bad play.

-- *Slide* --

# A Play!

-- *Slide End* --


I need at least 8 volunteers. 

**Activity** Hand out copies of the [play](https://github.com/resbaz/nectar-cloud-lessons/blob/master/Resources/Play.md)

Run through the play.

-- *Slide* --

## Exercise 1

Find and run the terminal program, or command line, on your computer.

OSX users can do a Spotlight Search for 'terminal'. 

Cygwin users simply click on the Cygwin desktop icon.

-- *Slide End* --

-- *Slide* --

## Exercise 2

Once you've opened it, remember PWD in our play?

Try the following command:

```bash
pwd
```

`pwd` is shorthand for **p**rint **w**orking **d**irectory

-- *Slide End* --

The working directory is simply the folder within your file system that you are currently positioned in.

Remember that Finder or File Explorer gives you a hierarchical tree view of your file system. 

> (Demonstrate by opening the finder and clicking through on some of the folders)

As the terminal can't give you the same view, it simply has the concept of being positioned in one of those folders. 
And that's the working directory that you see with the `pwd` command.

-- *Slide* --

## Exercise 3

We are going to replay our play!

There's a command line cheat sheet at: http://tinyurl.com/command-line-cheat-sheet

Use it to step the through the following tasks:  http://tinyurl.com/play-task

-- *Slide End* --

As ever, hold up a Green card when you're done.

And a Red card if you need help. But remember to ask your neighbours first!

Commands issued via terminals have the following advantages:

* They are terse
* If you know what you’re doing it’s faster to type than to point with a mouse
* They keep a history of your commands
* You can easily replay commands
* It is simple to automate

But the main advantage for us is that your terminal program can also be used to connect to another computer.

So Anna's hope comes in the form of the terminal application: She can run it on her local machine, and connect to 
her remote Drupal server.

Now in the last session we shut down own servers. If we're going to follow in Anna's footsteps, we need to relaunch
our Drupal servers.

-- *Slide* --

## Exercise 6

Gentle people, start your servers!

-- *Slide End* --

Remember, this time round we don't need to create a security group or a key: they are already there. So reuse them
when launching your VM.

Hold up a Green Card when you're ready to move on,
And a Red card if you need help.

-- *Slide* --

## ssh

The program we are going to connect to the server with is: 

```bash
ssh
```

`ssh` stands for **s**ecure **sh**ell. 

-- *Slide End* --

It connects a terminal on one machine to another target machine, thus allowing 
you to use the text based interface on the target machine. It kind of teleports the target machine terminal to yours…

You can think of `ssh` as your cloud login command.

`ssh` uses public key cryptography to connect with the target machine. 

Remember those public/private key pairs I've been going on about?

This is where they come in to play. Remember: 

"When NeCTAR fire up a machine for you, they inject the public key into your machine. Anyone with the private key will 
be able to communicate and control that machine. ... You want to keep your private key in a secure location."

**Demo**

Ask for two volunteers. Give the second one the two envelopes, one inside the other. 

The first volunteer is going to shout at the second "Oi - I want to talk to you!"

The second volunteer then passes the two envelopes to the first volunteer. 

Make the point that they have used the public key to encrypt the message, and only someone with the private key can
unwrap it. Hence only the first volunteer can!

Which he/she does. And then puts a message into the second envelop: which is then passed back to the second volunteer.

They read the message and put a new one in and pass it back. 

Make it clear that they are the only two people who can read what's in that inner envelop. Edward Snowden tells us
that this is still true!

And they can go on using that inner envelope for the rest of the conversation.

This is essentially what ssh is doing with the public and private key pairs.

Thank the volunteers.
 
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

-- *Slide* --

## ssh

```bash
ssh  -i <key> <user>@<address>
```

Eg: Along the lines of:

```bash
ssh -i tut_dev.pem ubuntu@144.6.225.224
```

-- *Slide End* --

So here:

* the `key` is the path to and the key file itself
* the `user` is the name of the user account on the remote machine that we are connecting as.  
  Different operating systems have different default user accounts.
* the `address` is the IP address of the Virtual Machine that we read off of the dashboard.

-- *Slide* --

## Question 2

Research Cloud have a catalogue that gives information about the images that they provide. It can be found at:

https://wiki.rc.nectar.org.au/wiki/Image_Catalog
 
Have a look at it. What operating system do you think the Drupal server is based on?

1. Fedora
1. Debian
1. Centos
1. Ubuntu
1. Scientific Linux

-- *Slide End* --

**Answer 2**

    D. Ubuntu

**Exercise 3**

-- *Slide* --

## Connect to your remote instance via ssh. E.G.:

```bash
ssh -i tut_dev.pem ubuntu@144.6.225.224
```

### PS: Windows users... 

To find your key file, 
prefix `/cygdrive/c/` to the directory 
that you saved your key file in...

-- *Slide End* --

If everyone could try to connect to their server using the ssh command, that would be wonderful.
BTW, I'm hoping that you all fail - with the error message!
 
 Hold up a Green card when you've reached this error message.
 And a Red card if you need help

-- *Slide* --

## Is this your error message?

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

-- *Slide End* --

Hold up a Green card when you've reached this error message.
And a Red card if you need help.

What's going on here? Anyone want to hazard an explanation?

The error message is very descriptive. ```ssh``` is rejecting your key file because anyone who has access to your
machine can read it. You need to tighten up the permissions on this file so that only you can access it.

Hit control-c to exit the password prompt.

This is where `chmod` comes to the rescue!

In my case, allowing me (the current **u**ser) to be able to **r**ead and **w**rite the file, and to exclude the 
**g**roup and **o**thers from being able to **r**ead, **w**rite or try to run (e**x**ecute) it, the command would be:

-- *Slide* --

## Exercise 7

This works for me:

```bash
chmod u=rw,go-rwx keys/tut_dev.pem 
```

Modify the permissions on your key file so that only you can read or write it.

-- *Slide End* --

Then issue the `pwd` command to see what directory you are in.

Retry the ssh command.

-- *Slide* --

## When you are asked:

```bash
The authenticity of host '144.6.225.224 (144.6.225.224)' can't be established.
RSA key fingerprint is d8:14:f5:85:5f:52:cb:f2:53:56:9d:b3:0c:1e:a3:1f.
Are you sure you want to continue connecting (yes/no)?
```

simply type "yes".

-- *Slide End* --

Hopefully, you are now met with something along following lines

-- *Slide* --

## Does this look familiar?

```bash
Welcome to Ubuntu 14.04.2 LTS (GNU/Linux 3.13.0-36-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
Last login: Mon Mar 30 01:27:13 2015 from hqrouter.vpac.org
ubuntu@drupal:~$ 
```

-- *Slide End* --

Re-issue the `pwd` command to convince yourself that are indeed now teleported into the remote machine.

Hold up a Green card when you are convinced you have a shell into the remote machine.
And a Red card if you need help.

-- *Slide* --

## Exercise 8

Finally, we are going try and update our web server. Try to execute the first command in the set:

```bash
apt-get update
```
-- *Slide End* --
-- *Slide* --

## Help!

Again, something dread full has gone wrong! You should be met with the message:

```bash
E: Could not open lock file /var/lib/apt/lists/lock - open (13: Permission denied)
E: Unable to lock directory /var/lib/apt/lists/
E: Could not open lock file /var/lib/dpkg/lock - open (13: Permission denied)
E: Unable to lock the administration directory (/var/lib/dpkg/), are you root?
```

-- *Slide End* --

Hold up a Green card when you've reached this error message.
And a Red card if you need help.

You are seeing this error because you are trying to perform system administration, and the ubuntu user you signed in 
as is not the super user normally allowed to do system administration.

But don't panic!

-- *Slide* --

## Exercise 8

The `sudo` command (**s**uper **u**ser **do**) comes to your help. It allows the ubuntu user to run commands with
the security privileges of the super user.

Try to execute the command again, this time with `sudo`:

```bash
sudo apt-get update
```

-- *Slide End* --

You should now see a whole lot of gets scrolling by, as the operating system updates its lists of installed and 
available software.

Once done, execute the command:

-- *Slide* --

## Exercise 9

```bash
sudo apt-get upgrade
```

If your system has software on it that needs an upgrade you will be met by a request to perform the upgrade. Something
like:

```bash
After this operation, 4,096 B of additional disk space will be used.
Do you want to continue? [Y/n]
```
-- *Slide End* --

In this case, reply, 'Y'.

Hold up a Green card when you've done this.
And a Red card if you need help.

Now we've replicated the steps Anna had to undertake in order to run the upgrade on her machine.

`apt-get` is the front end for a program called a package manager. Its rather like the appstore on your phone, and
allows you to add, remove, and update applications.

When you are finished working on your virtual machine, do the following:

-- *Slide* --

## Exercise 10

Type `exit`

You should see the following:

```bash
logout
Connection to <some_ip_number> closed
```
-- *Slide End* --

You have now closed the ssh connection to the remote machine. If you are not convinced, type `pwd` to see that your
terminal is now back on your local machine. The teleportation magic is over!

Hold up a Green card if you are back on your local machine.
And a Red card if you are not.

**Exercise 11**

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

It is a good idea to remove the ssh rule from the security group when you don't kneed it. This stops hackers from 
trying to access your machine.

-- *Slide* --

## Question 3

You remove ssh from a security group shared by many servers. 
Will you be able to ssh into any of the servers?

**Choices**

1. Yes
1. No
1. Only if there is another security group applied to the server that has ssh enabled.

-- *Slide End* --

**Answer 3**

    C. A server can have multiple security groups, and if anyone of them allows a port, then that port is allowed.

## Man in the middle attacks

**Demo**

Ask for three volunteers. Ask the first to write a message to the second on a sticky note, then place it into an envelope. 
And give it to you. Place the third person, (preferably male) in between the first and the second person.

You then carry it to the third person. 

Make the point that as before, the envelope is the encryption wrapper. And only someone with the private key can 
unwrap it and see it. But that the third person has actually convinced the first person that he is the second person.

Get the third person to read the message, perhaps change it a bit, then put it into a different coloured envelop,
and give it back to you. 

You then take it to the second person, who writes a reply and puts in back into the envelop. You return it to the third
person, who opens it, reads it, and perhaps changes it again. Then you put it back into the original envelop, and take 
it back to the orginator.

Make the point that the man in the middle has tricked the two on either side, and is listening to everything they say 
and do.

Thank the volunteers.

How ssh stops this from happening is that in every communication with a server, the first thing the server sends 
is a unique fingerprint to you. That was when you got asked the question:

-- *Slide* --

## Remember this?

```bash
The authenticity of host '144.6.225.224 (144.6.225.224)' can't be established.
RSA key fingerprint is d8:14:f5:85:5f:52:cb:f2:53:56:9d:b3:0c:1e:a3:1f.
Are you sure you want to continue connecting (yes/no)?
```

-- *Slide End* --

When you replied 'yes' that fingerprint for the server was stored as a line in a file called the known_hosts file.

From this point on, whenever you connect to the server, that fingerprint checked against the entry in
the known_hosts file. If they remain in sync, then everything is sweet.

But if they change, then ssh will refuse to give you a connection, showing the error:

-- *Slide* --

## There is possibly a man in the middle!

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the RSA key sent by the remote host is
45:ed:0b:42:16:b7:6c:dd:49:05:8d:b4:2b:16:7c:64.
Please contact your system administrator.
Add correct host key in /Users/martinpaulo/.ssh/known_hosts to get rid of this message.
Offending RSA key in /Users/martinpaulo/.ssh/known_hosts:14
RSA host key for 115.146.85.98 has changed and you have requested strict checking.
Host key verification failed.
```

-- *Slide End* --

The error message is very helpful: it even gives you the location of your known hosts file.

**Q**

How likely are you to see this error on the Research Cloud?

Hold up a Red sticky note if you think the answer is 'lots', 
Otherwise hold up a Green sticky note.

**A**

Lots. The Reds have it correctly. Remember I mentioned that NeCTAR recycle IP numbers? If you kill an instance and
restart it, then the chances are that new instance will have the same IP number as the old one.

-- *Slide* --

## Exercise 12

The command to fix this problem is:

```bash
ssh-keygen -R <hostname>
```

Where `<hostname>` can also be the IP number of your affected machine.

-- *Slide End* --

This command is in your cheat sheet: remember it - because you will need it!

To recap: in this lesson we learnt about terminals and how to use one to connect to a running system using ssh, and 
then how to update the software on the Ubuntu based system using the package manager. 

Remember, updating the software keeps your server more secure and thus safe. 

Each operating system type has its own package management program: so if you aren't on an Ubuntu system, you need to 
find out what the update command is. Ask a friendly Linux person to show you the right command. And remember to 
update often!

You also learnt to switch rules on and off on the security group, thus controlling access to the VM.