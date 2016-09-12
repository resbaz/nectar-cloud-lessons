# Windows SSH with MobaXTerm

This is *an alternative* to installing "Putty", and we now recommend use of **MobaXTerm**. 

If MobaXTerm is not installed, follow the installation instructions.

## Install MobaXTerm

http://mobaxterm.mobatek.net/download-home-edition.html

Download either:

* the Portable edition, and just unzip it
* the Installer edition (may require Adminstrative priviliges)

## Run MobaXterm

Find the shortcut, or just run the .exe

## Connect directly from the command line

Use ssh from the command line just like those Linux or Apple folk: 

```bash
ssh -i <path/to/mykey.pem> <username>@<ip.address.the.cloud>
```

You will now be logged in to your new server. 

## Or set up a connection shortcut in MobaXterm

* create a new SSH session 
* input your ip address "Remote Host", and username **ubuntu**
* check that it's using port 22 
* configure it to use your keypair.pem file 
* (configure any other settings relevant to your situation)
* Double-click your saved shortcut

You will now be logged in to your new server