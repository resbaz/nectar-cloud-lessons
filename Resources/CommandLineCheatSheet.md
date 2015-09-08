# Command Line Cheat Sheet


| Command   | Abbreviation For                        | Is/Does |
|-----------|-----------------------------------------|---------|
| `apt-get` | **A**dvanced **P**ackage **T**ool - get | the command line app store |
| `cd`      | **C**hange working **D**irectory        | changes directory |
| `chmod`   | **Ch**ange file **MOD**e                | protects your junk |
| `exit`    | EXIT                                    | terminates the current process |
| `ls`      | **L**i**S**t directory contents         | lets you see whats in the directory |
| `man`     | **MAN**ual                              | gives help |
| `pwd`     | **P**rint **W**orking **D**irectory     | shows where you are |
| `ssh`     | **S**ecure **Sh**ell                    | teleports you to another machine |
| `ssh-keygen` | **S**ecure **Sh**ell - **KEY** **GEN**erate | Allows you manage your keys |
| `sudo`    | **S**uper **U**ser **DO**               | lets you run administrative commands |

## Examples

### apt-get

```bash
apt-get update              # updates the information about software available
apt-get upgrade             # upgrades the installed software
apt-get install firefox     # installs the firefox application
apt-get remove firefox      # uninstalls the firefox application
```

### cd <directory>

```bash
cd ~        # go to your home directory
cd ..       # go to the parent directory
cd /        # go to the very base of the directory tree
cd /tmp     # go to the directory named tmp that is a child of the very base of the directory tree
cd tmp      # go to the directory named tmp that is a child of the current directory
```

### chmod <mode> <file>

```bash
chmod u=rw,go-rwx tut_dev.pem   # allow the current user to read and write, 
                                # but group and others to not read, not write and not execute
                                # the file named tut_dev.pem
chmod ug=rw,o-rwx tut_dev.pem   # allow the current user and the group to read and write, 
                                # but others to not read, not write and not execute  
                                # the file named tut_dev.pem
```

### ls

```bash
ls          # list current directories contents
ls -l       # give detailed list of current directories contents
```

### man <command>

```bash
man ls      # display the manual for the ls command
man man     # display the manual for the man command
```

### pwd 

```bash
pwd         # show the current directory I'm positioned in
```

### ssh <user@address>

```bash
ssh ec2-user@144.6.226.144                          # ssh into the machine at IP 144.6.226.144 as the ec2-user user
ssh -i ~/.ssh/some_key.pem ubuntu@144.6.226.144     # ssh into the machine at IP 144.6.226.144 as the ubuntu user 
                                                    # using some_key.pem as the key
```

### ssh-keygen -R <hostname>

```bash
ssh-keygen -R 144.6.226.144 # remove all keys belonging to the machine 144.6.226.144 from the known hosts file
````

### sudo <command>

```
sudo apt-get update # run the apt-get update command as the super user
```
