# x2go install, setup and usage.

## Start an x2go enabled instance 
1. [ ] Login to the dashboard
1. [ ] Create a new instance
1. [ ] Choose the image: `TPAC core.008 xxxxxxx`
1. [ ] Instance type: `m2.xsmall`
1. [ ] Then allow ssh via Security Group
1. [ ] Use your existing ssh keypair
1. [ ] Note the ip address somewhere
1. [ ] Leave your instance running

stop there.

## Install stuff on your computer
1. [ ] install the x2go client [http://tinyurl.com/x2go-client](http://wiki.x2go.org/doku.php/download:start)
1. [ ] now install the x11 server using one of:

Apple users: [https://www.xquartz.org/](https://www.xquartz.org/)

Windows users: [https://sourceforge.net/projects/xming/](https://sourceforge.net/projects/xming/)

Linux users rock (you have one already)

stop there.

## Setup the x2go client
1. [ ] Start x2go

Then configure the client as follows:

1. [ ] Session > New Session
1. [ ] Session Name: `x2go test`
1. [ ] Host: `your_instance_ip_address`
1. [ ] Login: `ubuntu`
1. [ ] Try auto login: `enabled`
1. [ ] Session type: Custom Desktop .. MATE
1. [ ] Hit OK
1. [ ] Click on the session named `x2go test` to connect 

(or you may need to browse to your ssh key)

please stop there.

## Observe your instance ip address
1. [ ] Start firefox
1. [ ] visit http://www.whatismyip.com
1. [ ] Leave firefox running
1. [ ] Quit x2go
1. [ ] Leave your instance running

stop there.

## Detaching and resuming sessions
1. [ ] Connect to your instance using x2go
1. [ ] Notice firefox still running?
1. [ ] Start calculator and do some math
1. [ ] Do some random stuff
1. [ ] Quit the x2go client
1. [ ] Connect using x2go
1. [ ] Check your stuff is still running OK.

stop there.

## Advanced, launching from the terminal
1. [ ] Start x2go

Then configure the client as follows:

1. [ ] Session > New Session
1. [ ] Session Name: `x2go terminal test`
1. [ ] Host: `your_instance_ip_address`
1. [ ] Login: `ubuntu`
1. [ ] Try auto login: `enabled`
1. [ ] Session type: Single Application .. Terminal
1. [ ] Connect to the instance via this session

A terminal window should appear.

1. [ ] Type `xeyes`

Did you get some googly eyes appearing?

1. [ ] Type `firefox`
1. [ ] Google "what is my ip"