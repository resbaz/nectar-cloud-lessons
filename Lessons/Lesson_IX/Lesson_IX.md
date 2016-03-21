-- *Slide* --

# Lesson IX: Securing and maintaining your instance (45 min)

-- *Slide End* --

> Anna Prentice finds that there is yet another security scare: realizing that she is out of her depth, she turns to her 
> local security expert to help her tighten up the security on her machine.
>
> That security expert is you!

-- *Slide* --

## Shared Responsibility Model

NeCTAR look after the cloud

**You** look after the stuff you put in that cloud

-- *Slide End* --

When it comes to security, NeCTAR follow the shared responsibility model.

That is:

* NeCTAR will make a best effort attempt to look after the security of the cloud
* You will look after the security of the instances, images, applications and content that you put onto the Research 
  Cloud.

Or put another way: NeCTAR manages the security **of** their cloud, you manage the security of the stuff you choose 
to put **in** that cloud. Hence the term "shared responsibility model"

What this really boils down to is that NeCTAR will look after the infrastructure, and you will look after the stuff
that you put up into their cloud.

This means that you have a fair amount of responsibility.
 
But that's true of all the computers and software that you use. 

-- *Slide* --

## Be paranoid!

>  "Just because you're paranoid, don't mean they're not after you" ― Nirvana, [Territorial Pissings](http://www.azlyrics.com/lyrics/nirvana/territorialpissings.html)  

-- *Slide End* --

And it is a scary world out there: the minute you put a server onto the internet, automated scanners start probing it 
for weaknesses.

-- *Slide* --

## Exercise

Reinstall and run firefox on your server.

Then in the browser go to:

Shields up: https://www.grc.com/shieldsup

Click on the 'Proceed' button, then select 'All Service Ports' and stand back.

-- *Slide End* --
 
What you are witnessing is a real time
scan of the first 1053 ports of your computer. Hopefully in our case it will only find 2 ports open.

The scan doesn't take long, does it?

The take away here is that the minute you put a server up on the internet, you are going to be probed for weaknesses.

In the current interconnected environment you can really never be too paranoid.

**Q:** Just to repeat, if you launch a machine based on a public image, and the software on it asks for your 
credit card info, do you type it in?

Please hold up a Red sticky note if you say "No, no way am I going to provide my credit card details!" 
and a Green one if the answer is "Yes, I'll happily hand my credit card info over. After all, what could go wrong?"

**A:** No! Be paranoid. You can’t trust the software on an image unless you know and trust the people behind the image.
And even then, they can still have made a mistake that will get you burned. 

One of the amazing things about the modern world is just how much trust we put into other people's software. 
We happily run applications provided by random strangers from the furthest points of the globe. That there 
seems to be so little actual hacking going on shows that either we aren't aware of what's going on, or that most
people are remarkably honest.

And the question that always plays at the back of my paranoid mind is:

**Q:** Would a good hacker want you to know that you've ben hacked?

Please hold up a Red sticky note if you feel that good hackers would prefer to remain unknown. 
and a Green one if you think that they want to be found out.

**A** I don't actually know the answer, as I'm not sure what motives hackers, but I think that most don't want to be 
found. And so what worries me is just how much successful hacking is actually going on...

-- *Slide* --

## Be prepared!

A good scout always:

* Knows what's the worst that can happen
* Takes steps to contain the fallout
* Knows what do in an emergency
* Makes sure they have a first aid kit!
 
-- *Slide End* --

So always have a plan that prepares for the worst. Ask yourself the following:

1. What's the worst that can happen if this machine or site gets hacked?
2. What I can do to minimize or contain the fallout when the machine does get hacked?
3. What steps do I have to take when the machine does get hacked?
4. Will I have the resources to take those steps?


### The worst thing can happen

By example of the worst thing that can happen, take the idea of using the same password and username everywhere.
 
**Q:** As an aside, who thinks this is a good idea?

Please hold up a Red sticky note if think that using the same password everywhere is a great idea. 
and a Green one if you think that this is a horrible idea.

**A** Greens have it. 
 
If someone compromises the server or site, just how many other sites or servers can they try those credentials on? 

Just how much pain can they inflict on you? Never mind your bank account, what are your friends and family going to
think if your twitter stream turns into a porn stream?

Remember that hackers do this in a highly automated way. Once they've got those credentials they can try them against
most of the popular sites around the world within minutes.

### Minimize the fallout

So when you run up a server, or register on a site, try to make sure that the ripple effect of it getting hacked are
contained. For example, as yourself "Is it OK to use the same password here that I use for my banking?".

### Know what to do when you are hacked

Also know what you need to do when you find that you have been hacked. Again, going back to the same password example,
know that you will have to go to all the sites that you have used that password on, and that you will have to change
your password on them. 

If your instance is hacked, you'll have to stop it running and bring up a replacement.

### Make sure you are able to take those steps

For example, if you have to go to many sites to change your password, do you have a list of them to work through? Or 
are you simply going to rely on your memory? If you have a lot of people using your machine, do you have their email 
address stored off of the machine so that you are able to contact them?

## Next steps

If you start with a NeCTAR prepared image, NeCTAR have already taken a few steps to help you be secure.

Luckily Anna's Drupal instance was based on a Nectar prepared image. We are going to tighten up the security a little.

## SSH

The first point of call we are going to look at is ssh, as this is the service that gives you access to the system, 
and is the most desirable one from the point of view of an attacker.

### Don't delete the known_hosts file!

First off, remember that every communication with a server, the first thing the server sends is its own public key to 
you. 

And that after the very first communication, where you accept the veracity of the public key, a check is done against an
entry in the known hosts file to see if that public key has changed.

**Q** Rather than editing the known_hosts file to remove entries that have knowingly changed, some people simply delete
the whole file. Do you think that this good practice?

Hold up a Red sticky note if you approve,
and a Green sticky note if you don't.

**A** You are hoping for a see of Greens here!

Ask random members of the audience for their opinions as to why they chose their answer. Try to encourage some debate
on the topic here.

The truth is that deleting the file is certainly very convenient, but that if there is any server with sensitive data
on it, then you really, really want to know if there is a man in the middle style attack in progress!

If there is a wide variance if answers, try to get the audience to debate it and then re-ask the question. Hopefully you
wil be able to move them to the green side of the answer spectrum. You might want to mention that foreign countries are
dead hot keen on research data (or movie companies on proof of piracy).

### Hide the ssh port 

-- *Slide* --

##Exercise

* Remove ssh from the security group on your VM
* Try to ssh in – and fail!
* Create a special ssh only security group
* Add it to your running VM
* Try to ssh in: success?

-- *Slide End* --

Remove ssh from the security group currently in force on your instance.

Try to ssh into your machine. All being well, you should find that you get an `Operation timed out` error..

Create a new security group with ssh as the only rule. Name it something useful, such as 'ssh'.
Add it to your instance.

Ssh into the VM again. All being well, you should find that you again have ssh access. (There might be a slight delay
as the change is propagated to the VM)

Remove the ssh security from the VM and try to ssh into the machine again. (You might have to wait a short while
as the change is propagated to the VM)

Hold up a Red sticky note if you need help.
A Green one if you've managed to leap through all these hoops.

-- *Slide* --

# A recommendation
 
Have a dedicated security group for ssh. 

Only enable it for a VM if you want to ssh into the machine. 

**AND THEN REMOVE IT ONCE YOU ARE DONE**

-- *Slide End* --

That way scanners automated scanners won't ordinarily see the port, and also won't have a window to attack it.

-- *Slide* --

## NeCTAR's security guidelines

NeCTAR has a set of security guidelines that can be found at:
 
* https://support.nectar.org.au/support/solutions/articles/6000070469-introduction

Ok: that's too long for normal people. Try

* http://tinyurl.com/nectar-security-guidelines

-- *Slide End* --

Note that it's a set of pages: not just one page. And they are worth taking the time to read! 

Lets work through some of the "Getting Started" tips.

### Mail Servers

If you can avoid running a mail server, then don't run it. It will make your life a lot easier. If you can, rather
use services such as [Mandrill](http://mandrill.com/) 

-- *Slide* --

# Avoid mail servers

* Use a service such as Mandrill
  http://mandrill.com/

-- *Slide End* --

### Enable automatic updates

Its funny: in the old days, when I was just getting started as a software developer, updating software was strongly
resisted because of the fear of something breaking. "If it's working, why change it" was the mantra.

But now, if you don't update your software with security updates, the chances are you will be hacked. 

So the lessor of the two evils is to perform security updates as soon as is possible. 

**I believe that this is the most important step that you need to take in terms of security.**

But there was wisdom in that old timer mantra of not rocking the boat. Every time you make a change to your system you
run the risk of breaking it. So remember to make sure you have a regular backup to hand.

Automatically install security upgrades on our Drupal site by ssh'ing in and doing the following:

-- *Slide* --

## Exercise

Enable automatic updates:

``` bash
sudo dpkg-reconfigure unattended-upgrades
```

And answer yes.

-- *Slide End* --

Hold up a Red sticky note if you need help,
And a green one when you are done.

*NB:*  Remember that we are running on an instance of Ubuntu. The instructions for other operating systems will be 
different. So if using a different operating system, find out what they are, and use them!

### Upgrade your kernel

By default, the unattended upgrades software will not reboot your system. 

So you will need to do this.

-- *Slide* --

## Exercise

Using the dashboard, reboot the running VM.

-- *Slide End* --

Hold up a Red sticky note if you need help,
And a green one when you are done.

### Subscribe to security announcements for your server

So how do you know if you need to reboot your VM?

Most popular software issue security advisories.

-- *Slide* --

## Exercise

Can you find the security advisories for the Ubuntu operating system?

-- *Slide End* --

Hold up a Red sticky note if you are stumped,
And a green one if you think you've found the page.

We should all be on the [Ubuntu security notices](http://www.ubuntu.com/usn/) web page. As you can see, it gives a
list of all Ubuntu security advisories. You can filter down to a particular release of Ubuntu, and you can opt to
get the advisories sent to you via email.

-- *Slide* --

## Exercise

On http://www.ubuntu.com/usn/ can you find a kernel advisory, and click through to it?

-- *Slide End* --

Hold up a Red sticky note if you are lost,
And a green one if you've found one.

There you will see that if a reboot is needed it is stated in the advisory. There's also a handy link telling you how
to apply the advisory. So: Lets apply the advisory!

-- *Slide* --

## Exercise

Follow the link to the instructions and apply the advisory.

At the end, reboot your instance from inside the ssh shell by issuing the command:

```bash
sudo reboot
```

-- *Slide End* --

BTW, Anna used `apt-get upgrade` to update her machine. As her local security expert you doubtless know that 
`upgrade` simply updates installed software, whereas `dist-upgrade` will try to intelligently handle any clashes
that might result from the new software being installed. If you perform an `upgrade` and see a message that packages
have been held back, that's your cue to run the `dist-upgrade`. Basically `dist-upgrade` makes deeper and riskier
changes. Double down on your policy of having a backup before you run this command!

-- *Slide* --

## upgrade vs dist-upgrade

```bash
apt-get upgrade
apt-get dist-upgrade
```

-- *Slide End* --

## Summary

To recap:

NeCTAR has a shared responsibility model when it comes to security. That means that they look after the security 
of the cloud. You look after anything you put up on that cloud.

But if you are a good scout/girl guide, and have a plan, you should be able to cope when you are hacked.

And when you put an instance up into the Research Cloud, there are some basic steps you can take to protect yourself.


-- *Slide* --

# Homework...

http://tinyurl.com/ResBaz-Links

-- *Slide End* --

We've just introduced the Research Cloud. In order to make use of it effectively do work through the NeCTAR training.

The page referenced here gives links to the NeCTAR training material that covers what we've done today.

-- *Slide* --

#Remember:

You can think of the Dashboard we've just explored as the drivers seat for an entire Data Centre: <br />
The Research Cloud. <br />
BUT it is a car you can crash! <br />
And we *want* you to crash it and restart it regularly...<br />
Don't be afraid: **\#failfast**!

## Thank you

-- *Slide End* --








