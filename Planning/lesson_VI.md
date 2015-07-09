#Snapshots: Backups, vertical scaling, sharing & transient storage (don’t rely on it!) (45 min)

##Learning objectives 

By the end of this lesson participants will understand what happens when you make a snapshot of a running instance.
They will know why snapshots are a somewhat imperfect backup medium.

They will also see how to scale their machine to a larger one, and of course, shrink it down again. 
They will be able to share their images with others. 

Finally, they will understand that transient storage is not to be relied upon.

##Motivation 

The ability to make a copy of a running instance confers a whole lot of benefits: the ability to switch to a larger
machine if needed, the ability to share copies with others, and to make somewhat imperfect backups. But there is the
risk that if you use transient storage you could lose your data or worse. Not something you would desire!

##Story

Anna is aware that she needs to make backups of her site: so she chooses to do this using snapshots, even though its
not an ideal way of doing this.

Her kitten picture is taking the internet by storm, and she needs to move to a bigger server to cope with the load.
She does this by scaling her instance up.

Then a colleague wants to user her site has a foundation for his own kitten extravaganza. Anna gladly shares her backup
with him.

Disaster strikes: Anna had some notes on the transient file store. When her server dies, she finds that they are no
longer on the replacement instance. Oh woes!

##Tasks

They will make a snapshot of a running VM.

##Covers

Snapshots, vertical scaling, transient storage and sharing snapshots.

##Concepts

That a snapshot is simply a copy of the images file system: but that making them does have an impact on the instance.
Not only that, if there are writes to the drive in progress, they can leave the copy in a faulty state. So to get a
high quality snapshot, disk activity has to be stopped and any buffers flushed. 

Snapshots can also be shared and used to move to a larger machine (vertical scaling).

Transient storage is not captured as part of the snapshot process.

##Notes 

Snapshots can take a fair amount of time depending on the system load. So the lesson might drag out because of this :(

##To discuss 



##Links for students 

http://wiki.libvirt.org/page/Snapshots
http://docs.openstack.org/openstack-ops/content/snapshots.html
http://physics.stackexchange.com/questions/32663/what-are-the-effects-of-cosmic-rays-on-consumer-electronics

##Supporting material 



##Preconditions 



