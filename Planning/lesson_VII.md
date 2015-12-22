# Lesson VII: Transient storage (don’t rely on it!) and sharing

##Learning objectives 

By the end of this lesson participants will know that transient storage is not saved when a snapshot is made.

They also learn how to share their snapshots with the greater world.

##Motivation 

Transient storage can take even experienced developers by surprise. Researchers should know that whilst it's
a great resource, it's not one that should be taken for granted: there is the risk that if you use transient
storage you could lose your data. Not something you would desire!

##Story

Disaster strikes: Anna had some notes on the transient file store. When her server dies, she finds that they are no
longer on the replacement instance. Oh woes!

Then a colleague wants to user her site has a foundation for his own kitten extravaganza. Anna gladly shares her backup
with him.

##Tasks

They will write a file to transient storage, then snapshot their instance. After that they will kill the instance
and then start up a new one based on the snapshot. The file on transient storage will be gone.

##Covers

Transient storage and sharing snapshots.

##Concepts

Transient storage is not captured as part of the snapshot process.

Snapshots can also be shared.

##Notes 

Snapshots can take a fair amount of time depending on the system load. So the lesson might drag out because of this :(

The effort required to create the file on the transient storage is large. Can it be simplified in any way?

##To discuss 



##Links for students 

http://wiki.libvirt.org/page/Snapshots
http://docs.openstack.org/openstack-ops/content/snapshots.html
http://physics.stackexchange.com/questions/32663/what-are-the-effects-of-cosmic-rays-on-consumer-electronics

##Supporting material 



##Preconditions 







##Preconditions 



