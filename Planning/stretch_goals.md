#Day 2

Day 2 day to was to be a stretch goal if development time permitted. These are the topics we thought we might cover
on the day.

> 9am - Start

# Lesson X: A recap (45min)

Yesterday’s lessons, rerun.

A walk through of the steps taken yesterday, with the audience playing along.

# Lesson XI: The command line clients (45min)

## Objective: 
 
By the end of this lesson participants will be able to find, install and know the usage pattern of any of the command 
line clients for the OpenStack components, and be able to update them as well.

# Motivation: 

Largely driven by the fact that that the command line clients are more fully featured, hence giving better control 
and more feedback.

## Discuss: 

Command line client advantages, patterns in use, and updating them.

## Task:

To install a command line client for Nova, and to start an instance.

> 10h30am - 11h00am: Morning Tea

# Lesson XII: Cinder (45min) (This is a problem in that private tenancy's don't have cinder access)

## Objective: 

By the end of this lesson participants will be able to create, format and mount a cinder volume.

## Motivation: 

In order to use cinder you need to know the basics.

## Discuss

Cinder, partitioning, formatting etc.

## Task

To create a cinder volume, attach it to the volume, and relocate a set of files to the volume. 

# Lesson XIII: The Prototype Instance (45min) A pattern for scaling with throwaway instances

## Objective: 

By the end of this lesson the participants should realize that Cinder is durable, and that by putting persistent
data onto cinder and using an image you can achieve both durability and sharing of data. 

## Motivation: 

If you have exceeded the storage limits of a 10 gig instance disk, block storage offers persistence between
runs of your instance, and allows data to be shared.

## Discuss: 

Scalability, and the partitioning of applications. The fact that the files on cinder will make your instance 
a singleton. That Cinder is not a replacement for proper backups.

## Task

Flush and unmount the previous cinder volume, then start up a new instance and reconnect the old volume to it: a
nd tweak it so that it all runs again.

> 12h30am - 1h30pm: Lunch

# Lesson XIV: The Singleton Instance (45min) A pattern for persistent instances.

## Objective

By the end of this lesson participants will be able to create an instance that is persistent between runs...

## Motivation: 

Having a perstent image lightens the worry of loosing information.

## Discuss: 

The cheats way to get a persistent image that doesn’t scale: and the reason why you would, or wouldn’t use it...

## Task

The original Drupal image is going to be migrated by snapshotting it into cinder and then booted from cinder.


Question: Can the image be resized? This would be a neat way of build up above the 10 gig limit...
Answer: Yes, you can resize your images. However, nova won't launch anything larger than 10 gig. So no prizes here...

# Lesson XV: Trove (45min) (This is a problem in that private tenancy's don't have trove access)

## Objective: 

By the end of this lesson participants will be able to create and connect to trove databases, and know the basics of 
adding users...

## Motivation: 

The researcher wants to make database backups as painless as possible. 

## To discuss: 

DBaaS

A basic intro to trove, and perhaps a "you play along at the command prompt". Also the realization that Trove
now frees the drupal instance up from being a singleton instance.

## Task

Move the drupal database onto Trove.

> 3h00pm - 3h30: Afternoon Tea

# Lesson XVI: Putting it all together with Heat (1 hour)

## Objective: 

By the end of this lesson participants will be able to understand Heat, and its advantages, and know where to go when they want to build their own templates.

## Motivation: 

The researcher is tired of manually setting all this up and monitoring it. He’s now going to use Heat to tie it all together.

## To discuss: 

Heat, the advantages of Heat, how Heat works etc...

## Task

Find a template in the NeCTAR template repository that fires up an application that they are interested in, and fire it
up and confirm that it works. Then explain the template to their neighbours.

> 4h30pm - Day end.
