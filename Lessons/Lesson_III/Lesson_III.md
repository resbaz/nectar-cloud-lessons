-- *Slide* --

# Lesson III: Accessing and updating your new computer (45 min)

-- *Slide End* --

> Anna Prentice has now had her Drupal web server up and running for a few weeks. And she's very happy! 
> 
> But on opening her newspaper one morning, she finds that there's a major Internet scare - hackers have found a 
> weakness that they are exploiting!
>
> Remembering that she is responsible for her web server, she decides that the software running on the machine needs 
> to be urgently updated.
> 
> She asks her local IT guru for help: and gets a scribbled bit of paper with a cryptic command set thrust in her 
> direction
> 

-- *Slide* --

## Run this on your machine, ASAP!

```bash
apt-get update && apt-get -y upgrade
```

-- *Slide End* --


## The Terminal 

-- *Slide* --

**Anna's free PC on the cloud has no keyboard, monitor or mouse. Do she have any hope of installing or removing
software on it?**

* <span style="color:red">&#9632;</span> = No, doom and gloom!
* <span style="color:green">&#9632;</span> = Somehow, somewhere, there is hope!

-- *Slide End* --

**Answer:** The Greens have it: there's always hope!

    Try to draw something like the following on a white board as you talk...
    +-----------------------+                  +------------------------+
    |     Local PC          |                  |     Remote PC          |
    |                       |                  |                        |
    |   +----------+        |                  |   +------------+       |
    |   |  Terminal|        |     ssh          |   |  Terminal  |       |
    |   |          +-----------------------------> |            |       |
    |   +----------+        |                  |   +------------+       |
    +-----------------------+                  +------------------------+

In the old days, because computing was so expensive, many people would share a single computer by means of terminals. 
A terminal was a keyboard and a screen, and many terminals could be attached to a single computer.
 
These terminals supported a basic text based interface that allowed you to do work on the computer it was attached to.

You'll be unsurprised to learn that with the passage of time, people wrote programs that emulated these terminals. So 
one computer could act as the terminal for another computer - or even itself!

So you can run a terminal application on your computer to do work on your own computer. You might recognize it as the
"Command Line"

But the main advantage for us is that a terminal program can also be used to connect to another computer.

So Anna's hope comes in the form of a terminal application: She can run it on her local machine, and connect to 
her remote Drupal server.

Now in the last session we shut down own servers. If we're going to follow in Anna's footsteps, we need to relaunch
our Drupal servers.

-- *Slide* --

## Exercise

Gentle people, start your servers! 

PS: *Reuse* your security group and key... 

* <span style="color:red">&#9632;</span> = I'd quite like some help, please!
* <span style="color:green">&#9632;</span> = I'm good to go!

-- *Slide End* --


-- *Slide* --

## ssh

The program/protocol we are going to connect to the server with is: 

```bash
ssh
```

`ssh` stands for **s**ecure **sh**ell. 

-- *Slide End* --

It connects a terminal on one machine to another target machine, thus allowing 
you to use the text based interface on the target machine. It kind of teleports the target machine terminal to yours…

You can think of `ssh` as your cloud login command.

Which is why you've been seeing the `ssh` references in the security groups.

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

Which he/she does. And then puts a message into the second envelope: which is then passed back to the second volunteer.

They read the message and put a new one in and pass it back. 

Make it clear that they are the only two people who can read what's in that inner envelop. Edward Snowden tells us
that this is still true!

And they can go on using that inner envelope for the rest of the conversation.

This is essentially what ssh is doing with the public and private key pairs.

**Thank the volunteers**
 
Why aren't we using passwords?

Well, they have problems:

-- *Slide* --

## The problem with passwords

* One more thing to remember (and forget)
* Need to be ever more complex
* Easy to crack (especially social engineering)
* Prone to being shared
* Cascade to other devices
 
-- *Slide End* --

They cascade if *you* use the same password across devices. And if you’re spawning multiple computers
on the cloud are you going to give them all the same password, or somehow ‘remember’ different ones?

If it’s your machine, what happens if you forget your password? There is no higher authority to unlock it for you…

And if it’s your machine, it’s granting access to the whole machine. If someone hacks it you could find
the security services knocking on your door at some early hour. And if that prospect doesn't scare you, you're a 
better person than I!

-- *Slide* --

## Question

Those running Microsoft Windows...

Yes, You!

Did you download and install PuTTY?

-- *Slide End* --

Hold up a Red sticky note if you didn't.

**A** We are hoping to see none. If there are some, well. Sigh. 

To all you Windows users: the Windows command line is incompatible with the Linux operating system that Anna is using on 
the Research Cloud.

Microsoft are planning to change this, but for the time being Windows users have to follow an alternate path.

That's why in the prerequisites we asked Windows users to download PuTTY. It's a tool that gives you a terminal you
can use on Linux computers.

And so this is where our worlds diverge. Apple computers are compatible and come with the needed 
software already installed.

So we are going to split up into two streams:

-- *Slide* --

## Walk through the following steps

* Apple: [http://tinyurl.com/apple-ssh-md](http://tinyurl.com/apple-ssh-md)
* Windows: [http://tinyurl.com/windows-ssh-md](http://tinyurl.com/windows-ssh-md)

-- *Slide End* --

Ok: now we are going take a break and perform a very bad play.

-- *Slide* --

# A Play!

-- *Slide End* --

I need at least 8 volunteers. 

**Activity** Hand out copies of the [play](https://github.com/resbaz/nectar-cloud-lessons/blob/master/Resources/Play.md)

Run through the play.

-- *Slide* --

## In your ssh session

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
And that's the working directory on the server that you see with the `pwd` command.

-- *Slide* --

## Exercise

We are going to replay our play!

There's a command line cheat sheet at: http://tinyurl.com/command-line-cheat-sheet

Use it to step the through the following tasks:  http://tinyurl.com/play-task

* <span style="color:red">&#9632;</span> = My thespian career needs some help!
* <span style="color:green">&#9632;</span> = I'm done!

-- *Slide End* --

But remember to ask your neighbours first!

Commands issued via terminals have the following advantages:

* They are terse
* If you know what you’re doing it’s faster to type than to point with a mouse
* They keep a history of your commands
* You can easily replay commands
* They are simple to automate

## Exercise

Finally, we are going try and update our web server. Try to execute the first command in the set:

-- *Slide* --

```bash
apt-get update
```
-- *Slide End* --

-- *Slide* --

## Help!

Again, something has gone wrong! You should be met with the message:

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

## Exercise

The `sudo` command (**s**uper **u**ser **do**) comes to your help. It allows the ubuntu user to run commands with
the security privileges of the super user.

Try to execute the command again, this time with `sudo`:

```bash
sudo apt-get update
```

-- *Slide End* --

You should now see a whole lot of gets scrolling by, as the operating system updates its lists of installed and 
available software.

-- *Slide* --

## xkcd 149

<img src="http://imgs.xkcd.com/comics/sandwich.png" title="The power of sudo" alt="Sandwich">

-- *Slide End* --

Think of `sudo` as being like a safety catch. When you find yourself using it, double check what you are about to
do!

Now execute the command:

-- *Slide* --

## Exercise

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
allows you to add, remove, and upgrade applications.

To see how easy it is to use the package manager, install the fortune application.

-- *Slide* --

## Install fortune

```bash
sudo apt-get install fortune-mod
```

* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm ready to move on...

-- *Slide End* --

-- *Slide* --

## Run fortune

```bash
fortune
```

* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm ready to move on...

-- *Slide End* --

So what you've just done is used `apt-get`, the front end to the package manager to update the system
and then to add an application. Feel the power!

When you are finished working on your virtual machine, do the following:

-- *Slide* --

## Exercise

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

**Exercise**

Return to the security group in the dashboard and remove the ssh rule.

Now try to ssh into your virtual machine again.

What happens?

Hold up a Green card if you have managed to teleport into your remote machine..
And a Red card if you haven't.

I'm hoping to see a sea of Red!

**Exercise**

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

## Question

You remove ssh from a security group shared by many servers. 
Will you be able to ssh into any of the servers?

1. Yes
1. No
1. Only if there is another security group applied to the server
   that has ssh enabled.

-- *Slide End* --

**Answer C** A server can have multiple security groups, and if anyone of them allows a port, then that port is allowed.

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

Um: Windows users: that's the: "Do you trust...." dialogue

-- *Slide End* --

When you replied 'yes' that fingerprint for the server was stored as a line in a file.

From this point on, whenever you connect to the server, that fingerprint checked against the entry in
the file. If they remain in sync, then everything is sweet.

But if they change, then ssh will refuse to give you a connection, showing an error:

-- *Slide* --

## There is possibly a man in the middle!

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@    WARNING: REMOTE HOST IDENTIFICATION HAS CHANGED!     @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
IT IS POSSIBLE THAT SOMEONE IS DOING SOMETHING NASTY!
Someone could be eavesdropping on you right now (man-in-the-middle attack)!
It is also possible that a host key has just been changed.
The fingerprint for the ECDSA key sent by the remote host is
20:db:ea:9c:66:9a:ee:07:e6:1b:d8:a4:9d:d0:99:bc.
Please contact your system administrator.
Add correct host key in /root/.ssh/known_hosts to get rid of this message.
Offending RSA key in /root/.ssh/known_hosts:87
  remove with: ssh-keygen -f "/root/.ssh/known_hosts" -R mdcs-256-w14
ECDSA host key for mdcs-256-w14 has changed and you have requested strict checking.
Host key verification failed.
```

Um: Windows users: that's the: "Do you trust...." dialogue

-- *Slide End* --

The error message is very helpful: it even gives you the location of your file, and the
exact command required to fix it!

Note that earlier versions of the ssh software don't show the command required to fix this warning!

**Q**

How likely are you to see this error on the Research Cloud?

Hold up a Red sticky note if you think the answer is 'lots', 
Otherwise hold up a Green sticky note.

**A**

You won't see it that much. The Greens have it correctly. But remember I mentioned that NeCTAR recycle IP numbers? 
If you kill an instance and restart it, then the chances are that at some stage an instance will have the same IP 
number as an old one. It's then that you'll see this error message.

-- *Slide* --

## The fix:

OSX: 

```bash
ssh-keygen -R <hostname>
```

Where `<hostname>` can also be the IP number of your affected machine.

Um: Windows users: Just click the "Yes I Trust This Computer" button.

-- *Slide End* --

This command is in your cheat sheet if you ever need it!

To recap: in this lesson we learnt about terminals and how to use one to connect to a running system using ssh, and 
then how to update the software on the Ubuntu based system using the package manager. 

Remember, updating the software keeps your server more secure and thus safe. 

Each operating system type has its own package management program: so if you aren't on an Ubuntu system, you need to 
find out what the update command is. Ask a friendly Linux person to show you the right command. And remember to 
update often!

You also learnt to switch rules on and off on the security group, thus controlling access to the VM.