# Lesson III Accessing, and moving data to and from the VM (45min)

Anna Prentice has now had her RStdio server up and running for a few weeks. And she's very happy! 

But on opening her newspaper one morning, she finds that there's a major Internet scare - hackers have found a 
weakness that they are exploiting!

Remembering that she is responsible for her RStudio server, she decides that the software running on the machine needs 
to be urgently updated.

Remembering the checklist used to launch a machine performs an update by issuing the following commands:

```bash
apt-get update && apt-get -y upgrade
```

She knows that she has to issue this set of commands again.

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

The program we are going to connect to the server with is: 

```bash
ssh
```

`ssh` stands for **s**ecure **sh**ell. It connects a terminal on one machine to another target machine, thus allowing 
you to use a text based interface on the target machine. It kind of teleports the target machine terminal to yours…



