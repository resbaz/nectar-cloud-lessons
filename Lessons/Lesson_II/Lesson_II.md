-- *Slide* --

# Lesson II: Your free computer: up and running (25 - 35 min)

-- *Slide End* --

**Note:** Introduce Anna, our persona who will be guiding the rest of the course.

> A researcher, Anna Prentice wants fire up a website to share some some information about her kitten project with the 
> world. 

> Looking at the NeCTAR image list, she sees that there is a public image with Drupal, a content management system that
> may allow her to share her data.

> Having sat through the first part of this course, and know knowing the parts of the Research Cloud, Anna 
> decides to see if she can launch the instance to see if meets with her needs.

_This is one of the great things about the Research Cloud: you can just spin up machines, play with them, and then
**THROW THEM AWAY**!_

> Remember, if you have any problems during this session, turn to your neighbors before you lift up your red sticky
notes!

## The power of Checklists

In 2001 a critical-care specialist at John Hopkins Hospital designed a checklist to prevent line infections. 

-- *Slide* --

## A line infection checklist

<div align="left">
▢ wash hands with soap, <br/>
▢ clean the patient’s skin with chlorhexidine antiseptic, <br/>
▢ put sterile drapes over the entire patient, <br/>
▢ put on a sterile mask, hat, gown, and gloves, <br/>
▢ put a sterile dressing over the catheter site once the line is in
</div>

-- *Slide End* --

These steps have been known and taught for years. 

They then asked the nurses to observe the doctors for a month as they put lines into patients, and record how often 
they completed each step. In more than a third of patients, they skipped at least one of the steps.

They then asked the nurses stop the doctors whenever a step was skipped.

The ten-day line-infection rate went from eleven per cent to zero. 

This story inspired a company that I worked at to introduce a checklist for deploying software into production.

We would do it a pairs, one person playing the role of the nurse, the other the surgeon, performing the actual steps.

We had to sign in the date and our names, and each checklist was filed after a deployment.

Our rate of problems encountered during deployment fell to zero.

| Further reading | Url |
|-----------------|-----|
| "The Checklist" | http://www.newyorker.com/magazine/2007/12/10/the-checklist |

Knowing this, I’ve created a set of checklists for launching a virtual machine that runs the Drupal server Anna is 
interested in.

## Key Pairs

We'll start by creating our key pair.

Walk the students through the key pair checklist, describing each entry

**NB:** you can only download this file once! Don’t lose it!!

**Note:** The checklists are online: so do as we did in our software deployments. One person will use the checklist
to instruct the other, remembering to fill in the checklists as you go through it. Then swap!

-- *Slide* --

## Key Pairs

Create a Keypair with the help of the key pair checklist

http://tinyurl.com/creating-a-keypair

*Tip:* Preface the security group name with an "kp_" so that you know that
its part of a keypair when you see the name...

-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

## Security Groups

Now we’ll move onto security groups.

Let's see if I can explain them in a bit more detail.

Network messages destined for a computer are broken up into packets. Once a packet reaches a computer how does the
computer know which application the packet is intended for? 

Well, the operating system allocates a different number to each running application. Then all network packets that
carry that number are sent to that application. This number is called a port number.

A security group is a firewall that allows all outgoing network packets to pass, but blocks all incoming network 
packets by default. But you can open "ports" in the security group, hence allowing inbound network packets with a 
matching port number through to the application on the instance.

    If you get lots of blank looks, the following twisted metaphor might help:
    
    Imagine that Australia was a computer: and that containers on ships heading to Australia were the network packets.
    And stretching the metaphor even more, that cities were applications. 
    
    If you can get your head around that tortured metaphor, then its easy. Each container has a port number painted on it.
    Then when the ship docks, customs will only allow those containers with the correct port number off of it.
    
    So what if each network packet also had an associated number indicating the destination application? Then the security
    group, acting as a customs officer, could reject all the packets that were not acceptable for a given application!
    
    Well, strange to say, each packet on the network gets given a port number, indicating the application it is intended
    to go to. And well known applications get well known port numbers. So web servers use port 80, for example.
    
    So simply put a security group allows you to define the port numbers that packets from the outside world must have if 
    they are going to be allowed to reach your VM. 
    
    Any packets with a different port number don’t even make it to your machine. They are just thrown overboard!

Ok, lets look at the security group checklist.

Walk the students through the security group checklist, describing each entry as you go. 

*If anyone asks, CIDR = Classless Internet Domain Routing, a flexible way of specifying internet address ranges*

-- *Slide* --

## Security Groups

Create a Security Group with the help of the security group checklist

http://tinyurl.com/creating-a-security-group

*Tip:* Preface the security group name with an "sg_" so that you know that
its a security group when you see the name...

-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

**NB:** You can edit a security group at any time.  And the changes will immediately apply to all running virtual 
machines using that security group.

**NB:** This also means that if you share security groups amongst VM’s, you have to be careful: if you change rules for 
one server, you might inadvertently break another.

-- *Slide* --

## Question

I change the rules in a security group by removing port 80 (http). Mysteriously a web server on another VM in the 
project stops "working". Could it be because:

1. The security group was shared with the other machine?
1. The web server inexplicably broke?
1. The other machine itself failed?
1. NeCTAR are experiencing a network problem?
1. All of the above... ☹

-- *Slide End* --

Walk through each option, describing how it could affect the instance you are trying to reach.

**Answer: E.** Yes, it’s true. The research cloud can experience network issues from time to time. 

**NB:** Under some circumstances, you might find that you already have security groups defined for your project: or that
the default security group has ports/applications set up for it. So it is wise to review your projects security groups
and to understand what is provided.

## Launch your own instance

Remember that an image is simply a file on the cloud somewhere. When we launch our computer in the cloud, we
select the image that we are going to be using, and then a copy of that file becomes the hard drive of the computer 
we are launching. And that that computer is called an 'instance'. The instance will in turn run our applications!

So you can think of instances as someone else's computers, and cloud applications simply as applications that run
on someone else's computers.

-- *Slide* --

## Launch an instance

Use the launch an instance checklist to launch an instance.

http://tinyurl.com/starting-an-instance
 
-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

-- *Slide* --

## Terminate an instance

Terminate the instance you launched!

-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

-- *Slide* --

## Count of less than 30 security groups

Did anyone find out why this is in the checklist?

-- *Slide End* --

It's in the list because NeCTAR limit you to a maximum of 30. Which means that you have to share them around if
you have lots of instances!

-- *Slide* --

## HTTP vs HTTPS

Can anyone tell us about these two?

-- *Slide End* --

HTTP is Hypertext Transfer Protocol. All you need to know is that it is the way in which web pages are requested
from the server and transferred back to your computer. HTTPS simply appends "Secure" to the end of HTTP. It gives you
the guarantee that the communications between you and the server are encrypted. So HTTP means anyone between you and
the server can see what pages you are looking at, and their contents. HTTPS means that they only will know what site
you are visiting.

-- *Slide* --

## What is SSH?

Anyone? Please?

-- *Slide End* --

Secure Shell. We'll cover it in the next lesson. Patience!

-- *Slide* --

## And CIDR?

(And no, it's not a drink!)

-- *Slide End* --

Classless Internet Domain Routing, a snazzy way of specifying internet address ranges.

So in this lesson we've launched a computer on the cloud, based on an image that has been shared with us. On top of that
we've created a security group to control access to our running machine. And we've launched it with a keypair which will
allow us to communicate with the machine in the next lesson.

These are the three essential skills for building any cloud application for you and all your research colleagues to 
use!!! When these three steps fail you, the fourth step is the HELP menu item.
 
Do you remember where it is?

And where do you find the user name that NeCTAR are going to request?