# Accessing your new computer (?min)

-- *Slide* --

## Accessing your new computer

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

-- *Slide* --

### Anna, run this on your machine, ASAP!

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

### Exercise

Gentle people, start your servers! 

PS: *Reuse* your security group and key... 

* <span style="color:red">&#9632;</span> = I'd quite like some help, please!
* <span style="color:green">&#9632;</span> = I'm good to go!

-- *Slide End* --


-- *Slide* --

### ssh

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

Ask for a volunteer. Give them two envelopes, one inside the other.

Then shout at the volunteer "Oi - I want to talk to you!"

The volunteer then passes the two envelopes to the you.

Make the point that they have used your public key to encrypt their response, and only someone with the private key can
unwrap it. Hence only you can!

Which you do.

To reveal the inner envelope: a shared secret wrapper, that is to be used for this conversation only.

And then put a piece of paper with a message into the inner envelope: which you then passed back to
the second volunteer.

They read the message and put a new one in and pass it back. 

Make it clear that the two of you are the only two people who can read what's in that inner envelope.

Edward Snowden tells us that this is still true!

And they can go on using that inner envelope for the rest of the conversation. And that this is done like this
because it's computationally expensive to use public and private keys.

This is essentially what ssh is doing with the public and private key pairs.

**Thank the volunteers**
 
Why aren't we using passwords?

Well, they have problems:

-- *Slide* --

### The problem with passwords

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

### Question

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

### Walk through the following steps

* Apple: [http://tinyurl.com/apple-ssh-md](https://github.com/resbaz/nectar-cloud-lessons/blob/master/Resources/AppleSsh.md)
* Windows: [http://tinyurl.com/windows-ssh-md](https://github.com/resbaz/nectar-cloud-lessons/blob/master/Resources/WindowsSsh.md)

-- *Slide End* --

To recap: in this lesson we learnt about terminals and how to use one to connect to a running system using ssh.