# Lesson VI: Snapshots, backups and vertical scaling (30 min)

##Learning objectives 

By the end of this lesson participants will understand what happens when you make a snapshot of a running instance.
They will know why snapshots are a somewhat imperfect backup medium.

They will also see how to scale their machine to a larger one, and of course, shrink it down again. 

##Motivation 

The ability to make a copy of a running instance confers a whole lot of benefits: the ability to switch to a larger
machine if needed, the ability to share copies with others, and to make somewhat imperfect backups. 

##Story

Anna is aware that she needs to make backups of her site: so she chooses to do this using snapshots, even though its
not an ideal way of doing this.

Her kitten picture is taking the internet by storm, and she needs to move to a bigger server to cope with the load.
She does this by scaling her instance up.

##Tasks

They will make a snapshot of a running VM.

##Covers

Snapshots, vertical scaling.

##Concepts

That a snapshot is simply a copy of the images file system: but that making them does have an impact on the instance.
Not only that, if there are writes to the drive in progress, they can leave the copy in a faulty state. So to get a
high quality snapshot, disk activity has to be stopped and any buffers flushed. 

Snapshots can be used to move to a larger or smaller machine (vertical scaling).

##Notes 

Snapshots can take a fair amount of time depending on the system load. So the lesson might drag out because of this :(

##To discuss 



##Links for students 

http://wiki.libvirt.org/page/Snapshots
http://docs.openstack.org/openstack-ops/content/snapshots.html
http://physics.stackexchange.com/questions/32663/what-are-the-effects-of-cosmic-rays-on-consumer-electronics

##Supporting material 



##Preconditions 



