#Snapshots: Backups, vertical scaling, sharing & transient storage (don’t rely on it!) (45 min)

##Learning objectives 

By the end of this lesson participants will understand what happens when you make a snapshot of a running instance.
They will understand why snapshotting is a somewhat imperfect backup medium.

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

What will the student do to learn this topic?

##Covers

What material is covered?

##Concepts

What concepts are covered?

##Notes 

Anything that the presenter should be aware of.

##To discuss 

The points of knowledge that the students should understand in order to master the topic

##Links for students 

Material for students to carry on reviewing in their own time.

##Supporting material 

What is needed to do the task

##Preconditions 

What the students need to bring to the table.

