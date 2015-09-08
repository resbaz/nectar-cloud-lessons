# Command Line Cheat Sheet


| Command   | Abbreviation For                        | Is/Does |
|-----------|-----------------------------------------|---------|
| `apt-get` | **A**dvanced **P**ackage **T**ool - get | the command line app store |
| `cd`      | **C**hange working **D**irectory        | changes directory |
| `chmod`   | **Ch**ange file **MOD**e                | protects your junk |
| `echo`    | **ECHO**                                | just echos a string |
| `exit`    | EXIT                                    | terminates the current process |
| `ls`      | **L**i**S**t directory contents         | lets you see whats in the directory |
| `man`     | **MAN**ual                              | gives help |
| `more`    | **MORE**                                | list the contents of a file |
| `pwd`     | **P**rint **W**orking **D**irectory     | shows where you are |
| `rm`      | **R**e**M**ove                          | remove a file or directory |
| `scp`     | **S**ecure **C**o**P**y                 | copy files securely between computers |
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

### echo <string>

```bash
echo "hello there!" # puts "hello there" on the console...
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

### more <filename>

```bash
more temp.txt   # display the contents of more.txt
```

### pwd 

```bash
pwd         # show the current directory I'm positioned in
```

### rm <filename>

```bash
rm notes.txt    # delete the file named notes.txt
```

### scp <from> <to>

```bash
scp ubuntu@144.6.226.144:notes.txt .  # copy the file named notes.txt from the home directory of the ubuntu user on the
                                      # remote machine to the current directory on the local machine
scp notes.txt ubuntu@144.6.226.144:   # copy the file named notes.txt from the current directory on the local machine
                                      # to the home directory of the ubuntu user on the remote machine 
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

```bash
sudo apt-get update # run the apt-get update command as the super user
```

## Useful keyboard short cuts

`TAB`       When entering paths and file names will autocomplete. If not working, hit twice to see all posible matches.

`CTRL+A`    Move the caret to the beginning of the line<br />
`CTRL+E`    Move the caret to the end of the line<br />
`CTRL+K`    Delete all characters after the caret<br />
`CTRL+J`    Delete all characters before the caret<br />
`CTRL+L`    Clear the screen<br />
`CTRL+C`    Cancel the running command<br />

`ARROW-UP` and `ARROW-DOWN` Step through your previous commands



