
# Lesson I: An introduction to the dashboard (45 min)

-- *Slide* --

# Roll up to the Research Cloud mystery tour!

your tour guide is ...

-- *Slide End* --

(First: Do a personal introduction. Who am I, and why am qualified to teach this course?)

## Why do you care about this?

Two researchers at the University of Melbourne, who shall remain nameless, needed to do some fairly complex statistical 
analysis. So out of their grant money they bought two powerful computers, at a cost of $10 000 per machine to 
run[ MatLab](http://au.mathworks.com/products/matlab/?nocookie=true) on. 

But on the first run, they found that the machines couldn’t work with their data sets. The machines were underpowered! 
They were forced to iteratively upgrade those machines, until finally, one was able to perform the required analysis. 
It had taken them 12 months from the date of purchase to get to this point.

If, instead of purchasing hardware, they had turned to the cloud, they would have been able to have had their initial 
machine running within minutes. 

If it was underpowered, they would have been able to upgrade it to a larger machine, again within a matter of minutes. 
They probably wouldn’t even have had to re-install the software.  

The really good news for researchers is that everyone with an AAF login can experience this game changer for themselves, 
at no cost: through the national Research Cloud (NeCTAR) project.

If Research Cloud had been around with their current funding model in place when those two researchers were setting up 
their project that’s $20 000 of grant money that could have been used elsewhere!

-- *Slide* --

## Question 1

Currently, how much does it cost a researcher to use the Research Cloud?

1. Gazillions!
1. Squillions!
1. Billions!
1. Some unknown $$!
1. It’s currently free **at the point of service**

-- *Slide End* --

**Answer: E**

There's another powerful reason to use the Research Cloud: access to storage which is kept locally in Australia and 
available on the high speed [AARNET](https://www.aarnet.edu.au/about-us) backbone. Think of it as a USB stick on
steroids!

And all of this is backed by a research facing organization that is not driven by profit.

But before you go rushing to the Research Cloud, there are some important gotchas that you have to understand. 
The cloud environment is a not quite the same as dedicated computer on your desktop! 

What I hope to do is to give you enough information to get your own machines up and running on the Research Cloud, 
and to explain the gotcha’s around this small area.

How I’m going to do this is, is to start with an overview the Research Cloud parts through a very high level drive 
through of the Research Cloud dashboard. Hence the Research Cloud mystery tour title.

Then in the following session we’ll launch and access a machine.

By the end of the first two sessions you should be able start up and manage your own machines on cloud. You’ll also 
know where to go for support when things turn to custard! 

## Log in to the dashboard

**Q:** It's part of the prerequisites, but just to check: has everyone here logged into the Research Cloud dashboard 
before today? 

Please hold up a Red sticky note if you haven't

**A:** You are hoping to see nothing here, as this means that you are going to have to walk these people through the
process. If you do see nothing, skip through to the [follow my leader](#Follow my leader) section.

## For those who haven't performed the prerequisites, some special instructions on logging into the dashboard.

**Q:** Those of your who didn't log into the Research Cloud dashboard: Do you have AAF credentials?

Please hold up a Red sticky not if the answer is "No" and a Green one if the answer is "Yes".

**Answer:** You are hoping for Greens, as people without AAF credentials can’t log in to the dashboard. One way around
this is to get those who don't have AAF credentials to pair with someone who does…

The first time you log on to the Research Cloud dashboard, you get given a **free** project/tenant, with three-months 
worth of time if you run the largest computer you can on it all the time. 

If you only use your smallest computer for short periods of time, and terminate them religiously after each run, you 
will find that your project/tenant should last far longer. 

But even if your trial project has expired, you can still log in to the dashboard to view and request 
allocations. You can even fill in an allocation request to extend your existing project/tenant!

Regardless of your path,  your project/tenant should give you the time to learn the Research Cloud ropes!

## Follow my leader

-- *Slide* --

## Question 2

Can you log into: [https://dashboard.rc.nectar.org.au](https://dashboard.rc.nectar.org.au)? 

-- *Slide End* --

Please hold up a Green sticky note once you are done!

And a Red one if you need help.

Now that everyone has logged in, we are going to play a short game of "[follow my leader](http://www.thefreedictionary.com/follow-my-leader)".  
As I have the big screen, I’m going to be the leader. So there!

What I’d like you all to do is to follow along in your browsers, trying to do what I do. 

    Now stop, and ask the audience to introduce themselves to the person on either side of them (if they don't
    know that person). Then let them know that these are the people that they will turn to first for help if they
    have any problems with the lesson. Only put up red cards if neither person on either side can't help them.
    So if a read card goes up, you are expecting to see a row of red cards!

And I’m going to be asking questions as we go long, just to see how well I’m doing!

Having logged in, you should all be at the home page of the dashboard.

**Q:** Does anyone have anything very different from what’s up on the screen in front of them? 
Please hold up a Red sticky not if the answer is "Yes"  and a Green one if the answer is "No".

**A:** Hoping for a lot of Greens here, as anything else is a problem!

## Project drop down

At the top of the dashboard are two drop downs.

The one on the left shows the projects that you belong to.

In OpenStack parlance, a project is: 

"*A logical grouping of users; it defines quotas and access to computers*."

And every project has a project ID: A "[User-defined alphanumeric string; the name of a project.](http://docs.openstack.org/glossary/content/glossary.html#project-id )"

So a project is really just a way to set group people together and to set constraints on what operations they can do on 
the Research Cloud.

But here’s the interesting thing: you can belong to one or more projects. That’s why a drop down is used. By using it 
you can toggle between the different projects that you belong to, and work collaboratively within the constraints of 
the currently active project.

To the left of the dashboard is a tabbed menu system giving access to the operations and resources bound to the project. 
Dependent on your project, and your rights within the project, the menu system will expand and contract as you switch 
between the projects. The project panes to the left control your access to the resources of the cloud.

**Demonstrate:** If you belong to more than one project, toggle between them to show changes in the menu 
system to the left of the page.

As mentioned, everyone who logs into the Research Cloud via the AAF gets a small time limited project/tenant. This project 
is prefaced by the words "pt" ([project/tenant](http://support.rc.nectar.org.au/docs/allocations)) and followed by a 
number. So mine is, for example, pt-30.

**NB:** If you have multiple projects, get into the habit of always looking at the entry shown in this drop down 
before you do anything major, simply to confirm that you are in the correct project. You wouldn’t believe the trouble 
I’ve got into by launching VM’s in the wrong project!

**Q:** Can all those people who have multiple projects make sure they have their personal project selected?

Please hold up a Green sticky note if your project is prefaced with the character  "PT", and a Red one if it’s not.

**A:** We are hoping for Green to be shown: otherwise there’s a problem...

## Settings drop down

The drop down on the right is the settings drop down. It’s not exactly the most intuitive of drop downs IMHO.

If you select it, you’ll see that there are two options: "Settings" and “Help”.

### The Help Menu

**Activity:** Get everyone to select "help" on the settings drop down.

**Q:** Are you all looking at the dashboard - or at something else?

**A:** Hold up a Red sticky note if you are still looking at the dashboard!
       
A new tab has opened, taking you to the homepage of the Research Cloud support site. This page gives news on the 
latest updates to the cloud. 

**Activity:** Get everyone to click on the "Getting Started" link of the top bar of the support site.

A menu appears on the left! 

**Demonstrate:** This menu to the left of the support site matches the links in the top bar of the support site.

The support site has loads of useful documentation. It has how to get started guides, tutorials and knowledge bases.
It’s well worth exploring. But we are not going to do it now. You know where to go when you want to find some helpful 
documentation.

**Activity:** Get everyone to click on the "Get Help" link of the top bar of the support site.

**Activity:** Get everyone to click on the "Get Support" link in the resultant page.

This is the important page if you want to reach out and get help. Here NeCTAR document the process that they 
would like you to follow when you reach out to get help.

1. Check to see if the Research Cloud is OK
2. Check to see if anyone else has experienced your problem
3. Finally, try to get help.

This process is there to try and save everyone time and effort on the NeCTAR side. We are getting a lot of cloud for 
very little cost. If we can lessen the amount of work that Research Cloud’s staff do we can get more of the cloud to 
use. It seems fair to me.

If you do decide that you need help, next Research Cloud lay out an email template showing the format they would like any 
support request to follow.

The **first piece of information they request is the email shown in the dashboard settings drop down**. This is important:
it lets them know who you are on the cloud - remember, the email you are sending from might not be the same as the one
the Research Cloud knows you as.

Then they ask you to provide the information describing your problem.

The missing piece is of the puzzle is the address you are going to send that email support request to.

So can everyone click on the cunningly disguised link labelled "submit your support email here".

Please don’t click send! 

What should happen is that some form of email client opens up with you just having to provide the required details…

-- *Slide* --

## Question: 3

Which one is the support email address?

1. support@rc.nectar.org.au
1. help_me@rc.nectar.org.au
1. do_not_reply@rc.nectar.org.au 
1. the_big_boss@rc.nectar.org.au

-- *Slide End* --

**Answer: A**

**Activity:** Get people to close the tab and return to the dashboard.

**Q:** Does anyone have anything very different from what’s up on the big screen in front of them?

Please hold up a Red sticky not if the answer is "Yes" 
and a Green one if the answer is "they are about the same".

### The Settings Menu

**Activity:** Get everyone to select "settings" on the settings drop down.

**Q:** Notice how the "Project" tabbed pane on the left side of the dashboard has been collapsed and a new “Settings” 
tabbed pane has been added below it? 

With "User Settings" as the currently selected tab.

The settings on the "User Settings" tab affect your dashboard interface. You can set your preferred language and 
the timezone you are in. 

These changes affect only you, as a user, but they do cover all projects! 

**Activity** Go ahead, and change the language to, oh say Chinese! (to see the effect).

The so that we will all see the same interface today, change your language and time settings to match mine. 
"British English (en-au)" and “Australia/Melbourne (UTC + 11:00) 

**Q:** Does anyone have anything very different from what’s up on the screen in front of them?

Please hold up a Red sticky note if the answer is "Yes" 
and a Green one if the answer is "they are about the same".

**Activity:** Select the "Reset Password" tab

**NB:** Do not try to use this password to log into the dashboard. This password has nothing to do with the dashboard!
You log into the dashboard using your AAF credentials. However, the AAF doesn’t work too well with command line 
applications. So here you generate a password to use with command line applications.

So that’s the Settings tab and its children. Site wide changes that work across all projects.

So remember: if you want to change your personal details, the top right drop down with your name on it is the way to go!

And that the password is for **applications only**!

-- *Slide* --

## Question 4

Which one of these can’t you do with your settings dropdown?

1. Change your command line password
1. Change your dashboard language
1. Change your time zone
1. Change your currently selected project
1. Find the documentation site

-- *Slide End* --

**Answer: D**

-- *Slide* --

## Question 5

If you change your password under the settings drop down, which is correct?

1. You are free of the AAF requirement!
1. Your AAF password is changed
1. Your institutions password is changed!
1. Tools that interface with the cloud will be affected 
1. None of the above
  
-- *Slide End* --

**Answer: D**

## Overview tab

**Q:** Does anyone have anything very different from what’s up on the screen in front of them?

Please hold up a Red sticky not if the answer is "Yes" 
and a Green one if the answer is "they are about the same".

The overview tab simply gives an overview of your projects usage of its allocated resources. When a pie chart is full, 
your project has exceeded its quota for that resource type. And they are colour coded, so problems should stand out.

The project overview tab is your default home page when you log in. So these limits are put fairly and squarely in 
front of your face.

## Project Tab

Going back to the project tab:

You should be able to see that it’s essentially a menu system made out of nested tabs.

The top level tabs within on your personal project should be

* Compute
* Object Store
* Orchestration
* Allocations

**Activity:** Just click around on these tabs and their children seeing how they expand and contract, and how the 
screens change according which tab is selected. They only change when the leaf tabs are selected.

Please hold up a Green sticky note once you've clicked on all of these tabs and their child tabs.

The *Compute* tab is where you manage all of your computer resources.

The *Object Store* is an ideal replacement for the usb sticks that some people tend to carry 
around with them: any file that you give it is backed up in at least triplicate. You can upload and download 
files from any browser: and you can share the files with the world.

*Allocations* is an important tab: Once you’ve messed around in your personal project, and found that it’s not big 
enough for serious work, this is where you come. It’s basically an online form that allows you to apply for a proper 
project with enough resources to support your research.  You can also request to have your project/tenant extended.
You do this by selecting the "Convert project trial" option.

Remember, Compute and the Object Store are two separate items: one is where you manage your computers, the other is a 
data store. They are not linked in any way, and can be run without the other.

### Project -> Compute -> Images Tab

Ok. Back to the "Follow my leader game" 

**Activity:** If you could all join me on the Images sub-tab of the Project tab.

**Q:** Is everyone on the same tab as me?

Please hold up a Red sticky note if the answer is "No" 
and a Green one if the answer is "Yes".

**Concept alert:** What we have here is simply a listing of files, each being a copy of a hard drives contents. Each 
file is termed an "image".

How the Research Cloud works is that you select a file that is a copy of the contents of a hard drive when you 
launch your machine. That file is copied across to wherever your machine is going to be run and becomes the 
basis of your new machines hard drive.

**Demonstrate:** Create a whiteboard drawing of this.

Across the top of the list of images are four filters that are reasonably self explanatory.

1. Project - the images that are visible only to your project. 
2. NeCTAR official - the images that Research Cloud share with the world. These are simply images of operating 
   systems.  Whilst on this list NeCTAR is keeping them current. 
3. Shared with me - the images that other users have opted to share with you. 
   Sharing images with others requires the use of command line tools, so it's a more advanced topic that you will
   have to leave till you are more familiar with the research cloud.
4. Public - the list of images that others have shared with the world. This mostly already have applications installed  
   on them, ready to run.

As new users to the Research Cloud it is unlikely that you’ll have either project or shared images. Those come 
with time. 

So the image you’ll start your adventure on the Research Cloud with is most likely to be a NeCTAR one.

**Q:** So here’s a thought experiment: you fire up a machine that uses a NeCTAR image as it’s base. NeCTAR then 
release a new copy of the image with a security update applied. Remember, your machine is based on a copy of that older 
image. Is it likely to have that update applied to it as well?

**Demonstrate:** Create a whiteboard drawing of this.

Please hold up a Red sticky note if the answer is "No" 
and a Green one if the answer is "Yes".

**A:** No. the only way to benefit from that update is to start up a new machine based on that new copy that NeCTAR 
have provided. So you have to either do a lot of maintenance on your running machine, or start from scratch on a regular 
basis.

One common way of working is to start up a machine based on a NeCTAR image, then to install your own software onto it, 
and then to make a copy of its hard drive as it runs. This process is called "snapshotting". 

This saves you from having to reinstall the software next time you launch a machine. 

**Demonstrate:** Create a whiteboard drawing of this.

**Q:** Again, if you build your own image like this will it benefit from NeCTAR’s updates to the original file you copied?

Please hold up a Red sticky note if the answer is "No" 
and a Green one if the answer is "Yes".

**A:** No, the files are not linked in any way. 

(NOTE:  Once you make snapshot, you need to update it regularly and re-save it. Otherwise it just won’t get all the 
security upgrades that are released for the software on it. Also, its a good habit to immediately update all the 
software on a newly created machine. You can never be too paranoid!)

**Q:** And lets be paranoid: if you launch a machine based on a public image about which you know nothing, and the 
software on it asks for your credit card info, do you type it in?

Please hold up a Red sticky note if the answer is "No" 
and a Green one if the answer is "Yes".

**A:** I wouldn’t. At least, without a lot of digging. You can’t trust the software on an image unless you know and 
trust the people behind the image. 

## Walk through of a launch

Let's stop the game of "follow my leader".

I'm going to demonstrate the steps required to turn one of those images into a running machine. As I do so, I'm going
to describe what's going on. So just watch what I do.

### Project -> Access & Security Tab

First, I need to set the environment that will control access to the the machine. To do this I go to the 
"Access & Security"

This page has a further three tabs across the top.

### Project -> Access & Security Tab -> Security Groups

The first one of these child tabs I'm going to visit is the security group tab. 

By default a machine brought up on the Research Cloud can reach out to the world via the network, but the world 
can’t reach in. 

Security Groups simply allow you to specify what network traffic is allowed to reach your machine in the cloud..

So I create a security group that specifies what network traffic is going to reach it. In this case, I want to create 
one that allows both ssh and http. 

HTTP is required to allow web browsers to access the running instance.

SSH is required to allow us to access the instance to manage it. You can see it giving us access to the administrator
interface.

###Project -> Access & Security Tab -> Key Pairs

The next tab I'm going to visit on this page is the key pair tab.

"What's a key pair?" I hear you not ask.

Ok way back when, in the olden days, say when Greece ruled the known universe, and say you were a wealthy merchant 
named Pem, lets agree that I borrowed a lot of money from you and then relocated to a remote city.

How would I know that the man in front of me claiming to be your emissary, now here to collect your cash for you, was 
the correct person?

And the answer used by some was ingenious. We’d take a clay seal and break it in half. I’d take half, you’d keep half. 
Your emissary would hand me the half of the seal that you’d given me and if it matched mine I’d hand the cash over. 
Obviously there is quite a lot of trust in the system. And you’d want to keep your half of the seal private: 
under lock and key. Me? Meh, not so much.

Keys are a very similar concept. They have two halves. Anything you encrypt with one half can be decrypted by anyone 
with the other half.

On this tab you create key pairs. NeCTAR will keep one, the public key, and you will download the private key, the 
other half, to your local machine.

When NeCTAR fire up a machine for you, they inject the public key into your machine. Anyone with the private key will 
be able to communicate with and control that machine. Like the clay seals of yesteryear, you want to keep your private
key in a secure location. 

Now I'm going to generate the keypair that I'm going to use to access the instance to manage it.

**Q:** You fire up your machine. Days later, you realise that you’ve lost your private key. Will you ever be able to 
access and control your machine from that point onward?

Please hold up a Red sticky note if the answer is "No" 
and a Green one if the answer is "Yes".

**A:** No, the chances are extremely high that you've lost your machine for good.

### Project -> Instances Tab

Having set up the environment that controls access to the the machine I'm now going to launch it.

I do this by going back to the instances tab.

This is simply the place where you get to see the information about all your running machines. 
Note that I say "machines", as you can run more than one computer should you so choose. The only
limit is the one defined by your allocation.

It is also one of the places that you can use to launch your free computer.

Which I now do by clicking on the "Launch Instance" button.

**Action** Do a walk through of the dialogue, remembering to add your keypair and security groups! Then launch it.

Ok, while that starts up, lets walk through what’s happening behind the scenes.

The image file that I’ve chosen to be the basis of my hard drive is copied from where it is being stored to the 
physical machine on which it is going to be used. This physical machine is called the host. 

We say "host" because the free machine you are launching is ordinarily going to be a “virtual machine”. 

A virtual machine is one that is simply software and hardware working in concert to emulate a real machine. You can 
think of it as being a program pretending to be a computer. Much like your desktop computer can run many applications 
at the same time, such as ms-word, and excel, etc, a Research Cloud server can run many virtual machines at the same 
time.

So here’s a question. You have a virtual machine running. It makes all kinds of changes to its hard drives. Which are 
simply files on the host server. What happens to those changes when you terminate your virtual computer?

-- *Slide* --

## Question 6

What happens to your hard drive when you terminate your Virtual Machine (VM)?

1. It gets copied back to the image store
1. It gets ‘snapshotted’ for you to use again
1. It’s left on the host server, for you to use when you next launch a machine
1. It gets destroyed. Wiped. Cleaned. Gone!

-- *Slide End* --

**Demonstrate:** Refer to earlier whiteboard drawing of this.

**Answer D:** The image is simply wiped.

So your virtual machine has what is termed "ephemeral" drives. Anything written to these drives will be lost if it’s 
associated virtual machine is terminated.

Rebooting or restarting its associated virtual machine does not cause your data to vanish. But if you 
terminate it, then, whatever you wrote to this drive will be lost the minute your virtual machine exits. 
All upgrades, security patches, whatever data you wrote, everything is lost.

This is one of the reasons why people like snapshot images so much. You work with your machine a little, you make a 
snapshot. The next time you start up from the snapshot, work with it, snapshot it when you are done.

This only works for small machines. It’s not the worlds greatest way of doing things, but it works for small machines.

I've seen this ephemeral storage take grown developers by surprise when they first start using the Research Cloud. 
It has just about reduced them to tears. Don’t be like them - trust nothing on the cloud!

Now, I've been saying "terminating", but if you look at the running instance you can see that you have many different
options for halting it. Which begs the question:

-- *Slide* --

## Question 7

When does my free PC on the Research Cloud get destroyed (along with all its data)?

1. When I do a soft reboot on my VM
1. When I terminate my VM
1. When I pause my VM
1. When I stop my VM
1. When I do a hard reboot on my VM

-- *Slide End* --

Pick out the wrong answers first to provide explanations of what they are!

A paused VM is simply halted in memory, ready to be started again.
A stopped VM has its state written to the host machines disk, ready to be resumed from there.
A soft reboot tries to do a graceful reboot.
A hard reboot just reboots the machine!

**Answer: B** 

(Once the machine is finally launched, point out the IP address in the dashboard)

Every machine that is launched on the Research Cloud is given an IP address. This is it’s location on the 
internet.

NeCTAR unfortunately only have a small pool of IP address to use.

So when you terminate your instance, the IP address is returned to the pool and allocated to the next machine that 
starts up. But like the transient file system, it is not lost during reboots.

-- *Slide* --

## Question 8

When do I lose my IP number?
 
1. When I do a soft reboot on my VM
1. When I terminate my VM
1. When I pause my VM
1. When I stop my VM
1. When I do a hard reboot on my VM
 
-- *Slide End* --

**Answer: B** 

Also know that if you **don't terminate your computer** then it will still be running down your allocation clock!
Stopped and paused computers are still consuming resources on the host computer!

    "An instance in shutdown state is still consuming resources on the
    compute node (disk space, ip address). The vcpus and ram to run this
    instance are also reserved (as the instance could start at any time).
    This is why an instance in shutdown state would count against an
    allocation."

Now knowing what's going on under the hood, you can understand why once you hit the "Launch" button there might be a 
delay before the machine runs - there's quite a lot going on.

So we've explored the dashboard, learnt how to file a support request, and done a dive into the architecture of the
cloud, and watched me launch a VM.

-- *Slide* --

You can think of the Dashboard we've just explored as the cockpit/drivers seat for an entire Data Centre - <br /> 
BUT it is a car/plane you can crash!!! <br />
And we *want* you to crash it and restart it regularly...<br />
\#failfast!

-- *Slide End* --

