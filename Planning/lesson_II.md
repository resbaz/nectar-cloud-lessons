#Lesson II A VM: up and running (45min)

**Objective:** 

By the end of this lesson, participants will be able to locate and launch an image on the NeCTAR cloud - and 
understand that the resultant machine is virtual.

**Motivation:** 

These are the basic steps required to successfully run a VM on the NeCTAR cloud. 

**Story**

A researcher, Anna Prentice wants to learn R at home: and use it at work. Not having a laptop, and looking at the 
RStudio website, she sees that there is a server version. She decides that if she can run it on the NeCTAR cloud it
would support her needs. 

Now knowing the parts of the NeCTAR cloud, Anna decides to see if she can find an image that has RStudio server
installed on it - and launch it.

**Task**

Create a security group, find the correct image, spin it up, connect to it with a web browser and then take it down

**Covers**

Glance, Nova, Security Groups

**Concepts**

Virtualization, moving an image from Glance to Nova, Security Groups, IP number allocation

**Notes:** 



**To discuss:** 

Nova and its message passing architecture, Glance and Horizon, how the disk is passed from glance to Nova, 
networking, security groups and IP number allocation. Note the state changes as the instance is spun up and 
how they show the message passing architecture of OpenStack

**Links for students:** 

* [An introduction to checklists](http://www.newyorker.com/magazine/2007/12/10/the-checklist)

**Supporting material:** 

* An image that will launch a server of some kind
* A security group that allows access

**Preconditions:** 

* A web browser

