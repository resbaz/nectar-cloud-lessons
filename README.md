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
* [Planning](Planning/Lessons.md) - The planning material that we used to develop the course
* [Resources](Resources/) - The resources that students will be using during the course
* [Diary](Dairy/) - Notes made from giving the course.

# Instructors notes

## Delivering the lessons

The lessons assume that participants have both red and green coloured sticky notes and cards lettered from "A" through
to "E" (in the style of Software Carpentry). These are used to answer questions and to show distress if the students
aren't keeping up or need help.

### When giving the lessons:

Try to engage the audience.  

* Ask them to provide explanations of what has just been done.
* Or ask questions of them. 

So for, example, 

* each time a bash command previously introduced is used point to people randomly and ask them what the command means...
* when you are typing bash commands ask for participants to tell you what to type at each space and slash in 
  the bash script...
  

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


### Prerequisites

* Each student will need a laptop with wifi access.
* The room must allow students to connect to the Internet via wifi. 
* Each student on the course must have an AAF logon.
* The Windows users will need to install [Babun](Resources/Babun.md) (5 minutes. Perhaps they can do this on the day?)
* Each person must have an allocation on the Research Cloud that they can use.

For those that have expired trial projects we can:

* get to pair up with others
* have a special tenancy for the lesson, and then them to it on the fly. 
  This is not a great solution as people in the tenancy will step on each others toes.
* have someone on hand to extend their trial tenancies on the spot?

If we could get participants AAF credentials before hand, we could:

* pre-create a special allocation for each person on the course that dies the day after the course.
* run a query to check if they are part of any project, and the status of their project.


## Git

If you check this repository out be aware that it uses Git submodules to manage the reveal.js dependency.
To also checkout reveal.js, you will have to either:

    # fetch it all in one hit
    git clone --recursive https://github.com/MartinPaulo/ResBazResOS.git

Or:

    # take it step by step
    git clone https://github.com/MartinPaulo/ResBazResOS.git
    git submodule init
    git submodule update

## To regenerate the slides

The SlideExtractor.jar in the root directory will re-create the slides if needed.

To run it ensure that the java version installed is java 8:

```bash
java -version
```

should return something along the lines of `java version "1.8.0_65"`.

If it doesn't then install java 8 from here: http://www.oracle.com/technetwork/java/javase/overview/java8-2100321.html

Then in a command prompt in the root directory simply issue:

```bash
java -jar SlideExtractor.jar
```

You should see something like the following fly by:

```bash
Working on:  ./Lessons/Lesson_I/Lesson_I.md
Writing to: ./Presentation/Lesson_1.html
    .
    .
    .
Working on: ./Lessons/Lesson_VIII/Lesson_VIII.md
Writing to: ./Presentation/Lesson_VIII.html
Writing to: ./Presentation/index.html
```

Remember to always walk through your slides when you regenerate them!


# Todo

1. [ ] Check that all red/green questions have the answer rephrase the question, if possible...

## Nice to have

1. [ ] Possibly add an FAQ of synonym's? Have things like drive, PC, server, IP, Web address, HTTP, link etc...
1. [ ] As a Chromebook user can I have an online SSH like resbaz.cloud.edu shell tool?
       [Crosh](http://www.howtogeek.com/170648/10-commands-included-in-chrome-oss-hidden-crosh-shell/)
       Or [Chrome Shell](https://chrome.google.com/webstore/detail/secure-shell/pnhechapfaindjhompbnflcldabbghjo)
1. [ ] Could we use three cup game, three card monty, etc. as example of moving data files around on your local and 
       remote server?
1. [ ] Should we create a booklet for attendees to take away with them - and to use during the session.

## For "Train the Trainer

1. [ ] As in Software Carpentry, should trainers who submit a GitHub correction get a certificate?
