# NeCTAR cloud lesson plan

This course aims to teach the basics of the NeCTAR cloud to researchers over a one day workshop.

> "We are ... looking to find (and train) what we are calling a "power (researcher) users".  
>
> From our work with the [Research Bazaar](http://melbourne.resbaz.edu.au/) here in Melbourne we've discovered that 
> there is an increasing number of researchers who are turning to the Cloud as their "Operating System"
>  of choice, we call this "ResOS".
>
> Our investigation into these types of users produce the following kind of persona traits (which is whom we are aiming 
> this "ResOS Train the Trainer curriculum").  "Power (Researcher) Users" are the types of researchers who see 
> themselves as:
>
>* technically savvy (the person in the lab who everyone goes to for help);
>* they feel they are researcher first and foremost, e.g. they usually introduce themselves as "researchers" but are 
>  very happy for their research colleagues to identify them as "technical".
>* sometimes these users are hired for their technical skills and identified as the research groups developer, but they 
>  do have discipline expertise.
>* often they are a postgraduate or early career researcher; far too often they are male.
>* types of people who immediately un-installed the operating systems which the University provided them on their 
>  laptop and replaced it with an OS which allowed them to have access to the "Utilities", "Settings" and 
>  "Advanced Settings" of their Operating System. 
>* they've even played around with installing Linux Ubuntu and other "command line" tasks.
>* while they understand the basics of installing an OS, it is only a means to an end so they can access more of the 
>  research tools which get them and their colleagues results.
>* for them the cloud is just someone else's computer and they are only just willing to trust a computer the University 
>  runs so long as no restrictions are made on them about how they use it (they are glad to go back to doing it 
>  themselves if there are any barriers or bureaucracy put up by the University).
>
> The purpose of the above persona is to provide a training to all the nodes (via creative commons) so we can train up 
> these PowerUsers in how to use the Cloud Operating System (NeCTAR OpenStack) so that they can customise it with the 
> apps that will make it their own discipline specific "ResOS".
> ...
> Once we test the training we hope to take it out on the road to each of the nodes so we can train up at least 
> 6-12 people in each city."
> -- <cite>David Flanders</cite>

## Motivator

It’s been hyped: but the Cloud does offer serious value in terms of cost and instant availability to researchers.
However, it’s a complex tool and if you don’t know and understand its constraints trying to make use of it can end
in painful tears. This course introduces you to the the tools and the underlying concepts of the NeCTAR cloud -
thus reducing your risk and saving you time and trouble in your journey to the cloud. And given the scale and low price 
of the research cloud you will, most likely, be making that journey.

## Folders

The directories that make up this project are as follows:

* [Promotion](Promotion/README.md) - Promotional material to use in advance of the course
* [Prerequisites](Prerequisites/) - What we would like students and trainers to do before they step through the door
* [Lessons](Lessons/) - The lessons themselves
* [Planning](Planning/lesson_plans.md) - The materials that were used to create the course
* [Resources](Resources/) - The resources that students will be using during the course
* [Diary](Dairy/) - Notes made from giving the course.

## Delivering the lessons

The lessons assume that participants have both red and green coloured sticky notes and cards lettered from "A" through
to "E" (in the style of Software Carpentry). These are used to answer questions and to show distress if the students
aren't keeping up or need help.

## Instructors notes

### In general

Each person being taught needs to be given 

* a red sticky note 
* a green sticky note.
* A set of answer cards, lettered 'A', 'B', 'C', 'D' and 'E' respectively.

The image used for the lessons is named `res_os_drupal7`. Check that it is still around and works
as expected before the lesson. If you need to rebuild it, there are instructions in the file
named [CreatingTheImageForTheWorkshop.md](Resources/CreatingTheImageForTheWorkshop.md) in the Resources
folder.

Distribute the [prerequisites](../Prerequisites/README.md) to participants: with an offer to help
if they have problems in following them.

Contact the allocation approver for the node where the course will be delivered in advance of the course to
let them know that there might be some people requesting an allocation in order to be able to take part.

### Preparation for lesson III

You will need a few copies of the [play](https://github.com/resbaz/nectar-cloud-lessons/blob/master/Resources/Play.md) for lesson 3.
People will have to crowd round and share. The goal here is to get people moving and interacting, as they become 
familiar with some concepts.

You will need to write the following words onto cards in big print, one word per card:

* PWD
* LS
* MKDIR
* CD
* CHMOD
* OTHER
* USER
* GROUP

### When giving the lessons:

Try to engage the audience. You can do this by asking questions of them. So for, example, 

* each time a previous bash command is used in lesson 4 point to people randomly to ask them what the command means...
* when you are typing bash commands ask for participants to tell you what to type at each space and slash in 
  the bash script...

### Todo

#### Must do

1. [ ] Bring the Kanban stuff into this "todo" list
1. [ ] Change guide to help to Freshdesk once Freshdesk is launched
1. [ ] Update for the new support email (support@nectar.org.au) once Freshdesk is launched
       (confirm email address and process)


#### Nice to have

1. [ ] Possibly add an FAQ of synonym's? Have things like drive, PC, server, IP, Web address, HTTP, link etc...
1. [ ] As a Chromebook user can I have an online SSH like resbaz.cloud.edu shell tool?
1. [ ] Could you use three cup game, three card monty, etc. as example of moving data files around on your local and 
       remote server?

### For "Train the Trainer

1. [ ] Update this document to reflect the two in one
1. [ ] Complete the "Train-the-trainers" additions
1. [ ] As in Software Carpentry, should trainers who submit a GitHub correction get a certificate?


## Feedback

### On lesson I:

    Tim: I haven't done anything yet, so why am I learning about allocations?

This is tough: logically it should go to the end of the lessons, but then people might leave early, and miss the
bits about their allocation expiring after 3 months, and how to extend them. Which is important.

    Fiona: Can the help stuff come later? It has been 15 mins and I haven't done anything yet
    
We should rejig somehow?

    Bernard: How do I calculate how many core hours? What about location?

Is this important - or will it confuse some people?

    Fiona: Can there be some more rationale - what is this going to let me do? 
    Refer back to the applications/ benefits more often

This should be salted through the lesson a bit more?

    Fiona: Can all this content on images (maintaining them etc) come later once we've created something? 
    Like the questions & structure but it's a bit abstract

Part of the rejig?

    Bernard: No rules appeared when I created a new security group
    
This seems to be rather random, and depends on the user. We need to dig further and find out what NeCTAR are doing here.

    Fiona: Should be getting the group to do the activities creating key pairs & security groups along with you

As part of the rejig, we should perhaps bin the demonstration, and head straight into the checklists? I'm a bit
nervous about this, as I think less technically able people might like to see it done first. Perhaps it's a line
call that should be done based on the prowess of the students? I'm thinking that we should try both approaches on 
this demographic and see which is better.

    Tim: I wasn't able to use my pt account to create a new instance because it had already exceeded its quota.

We are just going to have to get people like this to pair up with others: the only other way to handle this is
to create a special tenancy for the lesson, and then to add people like this to it...

### Overall

Should we add some scenarios for what you'll need to know when colleagues have found out about your new 
cloud manager skills, and want you to do different things with their images: e.g.: one colleague wants things 
backed up and archived for long term, one one a clean install, one wants... etc?


