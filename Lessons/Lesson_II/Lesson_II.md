# Lesson II: Your free computer: up and running (35 min)

> A researcher, Anna Prentice wants fire up a website to share some some information about her project with the world. 
> Looking at the NeCTAR image list, she sees that there is a public image with Drupal, a content management system that
> may allow her to share her data.

> Having sat through the first part of this course, and know knowing the parts of the Research Cloud, Anna 
> decides to see if she can launch the instance to see if meets with her needs.

_This is one of the great things about the Research Cloud: you can just spin up machines, play with them, and then
**THROW THEM AWAY**!_

## The power of Checklists

In 2001 a critical-care specialist at Johns Hopkins Hospital designed a checklist to prevent line infections. 

**Slide 1:** The checklist

These steps have been known and taught for years. 

They then asked the nurses to observe the doctors for a month as they put lines into patients, and record how often 
they completed each step. In more than a third of patients, they skipped at least one of the steps.

They then asked the nurses stop the doctors whenever a step was skipped.

The ten-day line-infection rate went from eleven per cent to zero. 

This story inspired a company that I worked at to introduce a checklist for deploying software into production.

We would do it a pairs, one person playing the role of the nurse, the other the surgeon, performing the actual steps.

We had to sign in the date and our names, and each checklist was filed after a deployment.

Our rate of problems encountered during deployment fell to zero.

<table>
  <tr>
  <td>Further reading: http://www.newyorker.com/magazine/2007/12/10/the-checklist</td>
  </tr>
</table>

Knowing this, I’ve created a set of checklists for launching a virtual machine that runs the Drupal server Anna is 
interested in.

## Key Pairs

We'll start by creating our key pair.

**NB:** you can only download your keypair once! Don’t lose it!!

Walk the students through the key pair checklist, describing each entry

**Activity 1:** Get students to generate key pairs on their own.

Please hold up a Red sticky note if you need help
and a Green one once you are done.

## Security Groups

Now we’ll move onto security groups.

Let's see if I can explain them in a bit more detail.

Network messages destined for a computer are broken up into packets. Once a packet reaches a computer how does the
computer know which application the packet is destined for? 

What if each network packet also had an associated number indicating the destination application? Then the computer 
could sort them into different "trays", for the applications to pick up and work with. 

So the "tray" numbers associated with a packet are named the port numbers. And well known applications get well 
known port numbers. So web servers use port 80, for example.

A security group allows you to define the ports that packets from the outside world can have if they are going to
be allowed to reach your VM. 

Any packets with a different port number don’t even make it to your machine. They are just thrown away.

Ok, lets look at the security group checklist.

Walk the students through the security group checklist, describing each entry as you go. 

*If anyone asks, CIDR = Classless Internet Domain Routing, a flexible way of specifying internet address ranges*

**Activity 2:** Now get the students to create a security group 

Please hold up a Red sticky note if you need help
and a Green one once you are done.

**NB:** You can edit a security group at any time.  And the changes will immediately apply to all running virtual 
machines using that security group.

**NB:** This also means that if you share security groups amongst VM’s, you have to be careful: if you change rules for 
one server, you might inadvertently break another.

**Question 1**

**Answer: E.** Yes, it’s true. NeCTAR can experience network issues from time to time. 

**NB:** Under some circumstances, you might find that you already have security groups defined for your project: or that
the default security group has ports/applications set up for it. So it is wise to review your projects security groups
and to understand what is provided.

## Launch your own instance

**Activity 3** Get students to walk through the creation of an instance, following in Anna's footsteps.

Please hold up a Red sticky note if you need help
and a Green one once you are done.

**Activity 4** Once they've done this challenge them to terminate it.

Please hold up a Red sticky note if you need help
and a Green one once you are done.

So in this lesson we've launched a computer on the cloud, based on an image that has been shared with us. On top of that
we've created a security group to control access to our running machine. And we've launched it with a keypair which will
allow us to communicate with the machine in the next lesson.