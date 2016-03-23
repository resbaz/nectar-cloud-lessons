# SSH with OSX

Follow the instructions below, step by step.

As ever, hold up a card as follows: 

* <span style="color:red">Red</span> = Won't you please, please help me!
* <span style="color:green">Green</span> = I'm done!

## Open up a terminal session

You can do a Spotlight Search for 'terminal' to find it.

## ssh

The program we are going to connect to the server with is: 

```bash
ssh
```

`ssh` stands for **s**ecure **sh**ell. 

This is the basic form our `ssh` command will take:

```bash
ssh  -i <key> <user>@<address>
```

Eg: Along the lines of:

```bash
ssh -i tut_dev.pem ubuntu@144.6.225.224
```

Remember:

* the `key` is the path to and the key file itself
* the `user` is the name of the user account on the remote machine that we are connecting as.  
* the `address` is the IP address of the Virtual Machine that we read off of the dashboard.

Give it a go!

## When you are asked:

```bash
The authenticity of host '<address> (<address>)' can't be established.
RSA key fingerprint is <some very long number>.
Are you sure you want to continue connecting (yes/no)?
```

simply type "yes".

BTW, I'm hoping that you fail - with an error message!
 
## This should be your error message:

```bash
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0777 for '<key>' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
bad permissions: ignore key: <key>
ubuntu@<address>'s password: 
```

What's going on here? 

The error message is very descriptive. ```ssh``` is rejecting your key file because anyone who has access to your
machine can read it. You need to tighten up the permissions on this file so that only you can access it.

Hit `control-c` to exit the password prompt.

Use Finder to locate and **select** your key file.

Once the file is selected, choose the "Get Info" menu option (File -> Get Info).

At the bottom of the Info window that opens, there will be a section titled "Sharing & Permissions"

If the information in Sharing & Permissions isn't visible, click on the triangle next to it.

If the padlock icon is closed, click on it to unlock it. You will have to enter an administrator name and password.

Select the line that says "everyone" and choose "No Access"

If there is a group between your username and the "everyone" label, select it and then remove it by hitting 
the button with the "-" label. 

You should now be able to try to reissue your `ssh` command in the terminal.

Hopefully, you are now met with something along following lines

```bash
Welcome to Ubuntu 14.04.2 LTS (GNU/Linux 3.13.0-36-generic x86_64)

 * Documentation:  https://help.ubuntu.com/
Last login: Mon Mar 30 01:27:13 2015 from hqrouter.vpac.org
ubuntu@drupal:~$ 
```

Now you can hold up a <span style="color:green">Green</span> card...



