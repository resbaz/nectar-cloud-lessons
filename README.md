# NeCTAR cloud lesson plan [V1.0.0](#versioning)

This course aims to teach the basics of the NeCTAR cloud to researchers over a one day workshop.

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
    git clone --recursive https://github.com/resbaz/nectar-cloud-lessons.git

Or:

    # take it step by step
    git clone https://github.com/resbaz/nectar-cloud-lessons.git
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


# Todo's

1. [ ] Update the prerequisites on this page.

## Nice to have's

1. [ ] Check that all red/green questions have the answer rephrase the question, if possible...
1. [ ] Possibly add an FAQ of synonym's? Have things like drive, PC, server, IP, Web address, HTTP, link etc...
1. [ ] As a Chromebook user can I have an online SSH like resbaz.cloud.edu shell tool?
       [Crosh](http://www.howtogeek.com/170648/10-commands-included-in-chrome-oss-hidden-crosh-shell/)
       Or [Chrome Shell](https://chrome.google.com/webstore/detail/secure-shell/pnhechapfaindjhompbnflcldabbghjo)
1. [ ] Could we use three cup game, three card monty, etc. as example of moving data files around on your local and 
       remote server?
1. [ ] Should we create a booklet for attendees to take away with them - and to use during the session?
1. [ ] Remove or improve the play!

## For "Train the Trainer

1. [ ] As in Software Carpentry, should trainers who submit a GitHub correction get a certificate?

# Versioning

Each version below will have an associated tag: hence enabling people to switch to a particular
point in time, if need be. But development will continue unabated on the master branch...

We have a whimsical 3 digit version number: but the truth is that there is no real schema in play.
The version number simply indicates a point in time. This is done so that if you want to teach
to a particular version of the material, you can.

| Version | Description | Date |
| ------- | ----------- | ---- |
| 1.0.0   | First release | 30<sup>th</sup> March 2016 |