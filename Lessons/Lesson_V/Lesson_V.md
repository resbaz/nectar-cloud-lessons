-- *Slide* --

# Lesson V: We can still run our graphical applications (30min)

-- *Slide End* --

> Anna Prentice needs to view a remote web site. However, on trying to access it, she finds that her institutions
> IT services has mistakenly blocked the site. Rather than trying to go through the paperwork to sort it out, she
> wonders if perhaps she can simply use her machine on the Research Cloud to access the site.

## X11

As part of the prerequisites, you were supposed to have installed X11 if you use Apple, or Xming if you use Windows.

Hold up a Green card if you've managed to do this.
And a Red card if you are going to be playing catchup!

Now Anna will need to connect to the server once again via ssh, but this time using X11 forwarding

_What on earth is X11 forwarding?_, I hear you ask.

**Demonstrate** Draw the following on the whiteboard

X-Windows is the name of the presentation system used on the Research Cloud servers. One of the cool things about it
is that it allows an application to run on one machine, and the applications graphical user interface to appear
on another. Here the X refers to X-Windows. 11 refers to the version of X windows. X11 forwarding simply means
that `ssh` will allow the X11 software installed on your local machine to render the graphical application
being run on the remote machine.

It's kind of like TV: the server is broadcasting the user interface to your local machine.

So we need to connect to the remote machine with X11 forwaring enabled.

Sadly again we are going to split up into two streams:

-- *Slide* --

## Walk through the following steps

* Apple: [http://tinyurl.com/apple-x11-md](http://tinyurl.com/apple-x11-md)
* Windows: [http://tinyurl.com/windows-x11-md](http://tinyurl.com/windows-x11-md)

-- *Slide End* --

-- *Slide* --

## Before we get going with Firefox

In your newly opened connection use the package manger to install some apps...

```bash
sudo apt-get install xauth
sudo apt-get install x11-apps
```
* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm ready to move on...

-- *Slide End* --

-- *Slide* --

## Test it all

Run a calulator remotely!

```bash
xcalc &
```

* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm ready to move on...

-- *Slide End* --

Automagically, although it is running on a remote server,
the calculator interface appears on your local machine!

## Browsing the web via Firefox

Having connected to her remote server, Anna then needs to install Firefox, a web browser. To do this she simply uses
the package manager, and asks it to install Firefox for her.

Once Firefox is installed, she simply needs to run it, and automagically, although it is running on her remote server,
the interface appears on her local machine!

-- *Slide* --

# Install and run Firefox

```bash
sudo apt-get install firefox
firefox &
```

* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm browsing the Internet.

-- *Slide End* --

Note that the GLTK errors that are reported are acceptable, and are not of concern. 


-- *Slide End* --

# Editing Files

> Anna noticed that the people who set up her Drupal server have left a file named 'today.txt' in the home directory
> of the ubuntu user. Curious to know what's in it, she decided to install a graphical editor to view and edit it.

```bash
sudo apt-get install gedit
```

-- *Slide* --

## Install gedit and edit today.txt

```bash
sudo apt-get install gedit
gedit today.txt 
```

-- *Slide End* --

Once you've done this, save the file and exit gedit. Confirm that your changes have have been saved by using the 
`more` command:

-- *Slide* --

```bash
more today.txt
```

-- *Slide End* --

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

> Knowing that her server is a small one, Anna decided to remove gedit and firefox before she exits the ssh session.

She does this using 

```bash
sudo apt-get remove gedit
sudo apt-get remove firefox
```

-- *Slide* --

## Exercise

Remove gedit from your systems, and exit your ssh sessions.

-- *Slide End* --

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

What you've learned to do in this session is to install and remove packages using the ubuntu package manager. You've
also learnt how to connect via ssh in such a way as to run graphical applications on the remote server, with their
screen appearing on your local machine.
