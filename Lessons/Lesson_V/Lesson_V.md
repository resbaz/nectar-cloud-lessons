# Lesson V: We can still run our graphical applications (30min)

> Anna Prentice needs to view a remote web site. However, on trying to access it, she finds that her institutions
> IT services has mistakenly blocked the site. Rather than trying to go through the paperwork to sort it out, she
> wonders if perhaps she can simply use her machine on the NeCTAR cloud to access the site.

## X11

To be able to do this magic Anna needs to install some software on her local machine. 

She is running osx.

Go to https://support.apple.com/downloads/X11_for_Mac_OS_X_1_0 and select the **X11 for Mac OS X 1.0** package.

Download and install the package.

Once that's installed, she will need to connect to the server once again via ssh.

This time however, she's going to add -Y to the `ssh` command.


```bash
ssh -i key.pem -Y ubuntu@115.146.84.207
```

**Question 1**

Using the `man ssh` command, what is the -Y flag adding to the `ssh` command

**Choices**

    A. Forces ssh to use IPv4 addresses only
    B. Specifies the user to log in as on the remote machine
    C. Enables trusted X11 forwarding
    D. Asks ssh to display the version number and exit
    E. Forces ssh into quiet mode.

**Answer 2**

    C. Enables trusted X11 forwarding.

_What on earth is X11 forwarding?_, I hear you ask.

X-Windows is the name of the presentation system used on the NeCTAR servers. One of the cool things about it is that it
allows an application to run on one machine, and the applications graphical user interface to appear on another. Here
the X refers to X-Windows. 11 refers to the version of X windows. X11 forwarding simply means that `ssh` will allow
the X11 software installed on your local machine to render the graphical application being run on the remote machine.

## Browsing the web via Firefox

Having connected to her remote server, Anna then needs to install Firefox, a web browser. To do this she simply uses
the package manager, and asks it to install Firefox for her.

```bash
sudo apt-get install firefox
```

Once Firefox is installed, she simply needs to run it, and automagically, although it is running on her remote server,
the interface appears on her local machine!

```bash
firefox
```

**Exercise 1**

Connect to your running server via ssh, and install and run Firefox.

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

# Editing Files

> Anna noticed that the people who set up her Drupal server have left a file named 'today.txt' in the home directory
> of the ubuntu user. Curios to know what's in it, she decided to install a graphical editor to view and edit it.

```bash
sudo apt-get install gedit
```

**Exercise 2**

Install gedit and edit today.txt as you see fit using the command:

```bash
gedit today.txt 
```

Once you've done this, save the file and exit gedit. Confirm that your changes have have been saved by using the 
`more` command:

```bash
more today.txt
```

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

> Knowing that her server is a small one, Anna decided to remove gedit before she exits the ssh session.

She does this using 

```bash
sudo apt-get remove gedit
```

**Exercise 3**

Remove gedit from your systems, and exit your ssh sessions.

Hold up a Green card when you've managed to do this.
And a Red card if you need help.

What you've learned to do in this session is to install and remove packages using the ubuntu package manager. You've
also learnt how to connect via ssh in such a way as to run graphical applications on the remote server, with their
screen appearing on your local machine.
