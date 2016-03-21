# Window shells

I did a basic evaluation of the following windows shells to see which was most suitable for this course.

In the end we have decided to change the course to use whatever Intersect used in their
training. 

This is Putty for ssh (http://training.nectar.org.au/package07/sections/connectViaSSH.html) and
Xming (http://training.nectar.org.au/package07/sections/guiViaSSH.html)

## [Git Bash](https://git-for-windows.github.io/)

Has ssh, but I can't get it to ssh into a vm?

This is because it is hard wired to use id_rsa as its key choice. See the following
[Stack Overflow](http://stackoverflow.com/questions/17383177/permission-denied-publickey-errors-on-windows-when-using-moovweb)
bug.

Advantage is that it opens its default shell into the users home windows directory.
Disadvantage is that the user is limited to one key.

## [Moba XTerm](http://mobaxterm.mobatek.net/)

Worked flawlessly: but very different experience to regular osx shell.

Disadvantage is that it requires two different lesson streams on the setup instructions.

## [Babun](http://babun.github.io/)

Worked flawlessly.

A wrapper around cygwin

Advantage is that it is so similar to the OSX shell in use we only need one lesson stream.

Disadvantage is the bizarro /cygdrive/c/Users/IEUser/ dance to get to the users home directory.

Disadvantage is that it ignores file permissions [by design](https://github.com/babun/babun/issues/457).
Removing the '`noacl`' flag from `/etc/fstab` fixes this.

To run X11 with Babun, you are supposed to do

`pact install xinit xorg-server`

In a Babun console. However, when I ran it I get 408 errors: and no packages installed.

Despite the above we did trial Babun in a lesson: and found that people struggled with the download times :( 

## [Cmder](http://cmder.net/)

Worked flawlessly.

Disadvantage is that it took forever to unzip (could be the virtual machine disk growing), and that lots
of security advisories popped up...

Disadvantage is that it ignores file permissions.

## [Putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/)

Worked flawlessly.

Downside is as for MobaXTerm: a different experience to the osx shell, hence two different lesson streams.

## [Cygwin](https://cygwin.com/)

Worked flawlessly.

Advantage is that it observes file permissions flawlessly

Downside is the installer, and getting people to step through it in a hurry :(
Disadvantage is the bizarro /cygdrive/c/Users/IEUser/ dance to get to the users home directory.