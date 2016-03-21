-- *Slide* --

# Lesson VII: Transient storage (don’t rely on it!) and sharing

-- *Slide End* --

In the last lesson, we launched our image based on our snapshot with the largest size possible.

Did any of you notice the ephemeral disk in the flavor details?

**Demonstrate**

Bring up the launch dialogue and show the changing ephemeral disk as different flavors are selected. 

That's what we are going to be looking at in this lesson. 

-- *Slide* --

Anna needs some extra disk space over and above the 10G image size. While she's ssh'd into her larger instance she
types 

```bash
df -h
```

(**d**isplay **f**ile usage)

And sees that she has 30 Gig of free space on `/mnt`

She decided to put her new files there. Has Anna made a mistake?

-- *Slide End* --

---

Hold up a Red sticky note if you think she has.
Otherwise a green one if you think all is well.

**A**

We are going to do an experiment to see who's correct.

Ssh into your running instance.

Do as Anna did and issue a `df -h`. You should see the same result as her.

---

Hold up a Red sticky note if you don't.
Otherwise a green one if you do.

-- *Slide* --

## A command line torture test

```bash
df -h
# check file permissions and make usable
ls -al /mnt/
sudo chmod a+rw /mnt/  
# Create two files
echo "This is file one" > /mnt/temp.txt
echo "This is file two" > home.txt
# Confirm their contents:
more /mnt/temp.txt
more home.txt
```

When done, make a snapshot of this machine.

-- *Slide End* --

---

Anyone want to hazard a guess as to what chmod does, and why is it needed?

Remember to make the snapshot of your running instance following our new best practices!

When it is complete then delete the original instance.

---

-- *Slide* --

## A command line torture test, continued

Launch a new instance of the same flavor as the last from your new snapshot.

`ssh` into the new instance and run the following commands:

```bash
sudo chmod a+rw /mnt/ 
more home.txt
more /mnt/temp.txt
```

What's missing?

-- *Slide End* --

---

All being well, you should get a "No such file" error when you try to look at file1.txt.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

---

So where's the missing `temp.txt`?

When you launch an instance, the instance is given a second hard drive with a fair amount of of space on it.
That is the extra space that Anna found and used.

**NB** When you make a snapshot, the snapshot is only of the primary drive. Anything on the secondary 
ephemeral drive is not saved. 

You can get and run some fairly grunty machines on the Research Cloud cloud. But snapshots will only save your small 
primary drive. If you use the extra drive space you will not be able to back it up by means of snapshots!

**Q** So to repeat: has Anna made a mistake?

Hold up a Red sticky note if you think she has.
Otherwise a green one if you think all is well.

**A**

I'm hoping to see a sea of Red...

## Sharing

> Anna has now got quite a cat collection on the go: and would like to share it with a colleague. 
> How would she do this?


-- *Slide* --

## Exercise

On the images tab of the dashboard, click the drop down button next to the "Launch" button. Select the 'Edit' option.

In the resultant dialogue give the image a description and check the public flag. Then save it.

-- *Slide End* --

---

Once it's saved go to the list of public images and see if you can find it in there. Yes, that's the whole world who
can now start an instance based on your image!

Hold up a Red sticky note if you need help,
and a Green one once you are done.

---


-- *Slide* --

## Question

Anna's snapshot was made with her public still on the image.

Will she be able to ssh into her colleagues instance once he launches it?

1. No
1. Yes

-- *Slide End* --

**Answer B**

Yes, she can. Her key is on the image, so she can access it.

-- *Slide* --

## Exercise

Get someone else to launch your shared snapshot, then ssh into it. Do the same for them.

-- *Slide End* --

-- *Slide* --

## Question

Is having other peoples keys on your instance a potential problem?

1. Yes
1. Yes

-- *Slide End* --

**Answer: Yes**

**Activity** Ask the audience why: challenge them to think through some of the issues.

The takeaway is that you should be very leery about other peoples images and snapshot: at the very
least, you should get a technical friend to see who can log on to the snapshot - and possibly remove
other users for you.

-- *Slide* --

## PS: The keys live in the authorized_keys file

```bash
more ~/.ssh/authorized_keys
```
## *For each user!*

-- *Slide End* --

-- *Slide* --

## Question

Beware the size ratchet!

> Anna made a snapshot of a 10Gig machine: and is now trying to launch it as a 5Gig flavor. 

What happens?

-- *Slide End* --

---

Hold up a Red sticky note if you think it's going to end in tears.
And a Green one if you think that it will launch.

---

-- *Slide* --

**Answer**

Yep: the tears have it:

> Anna will get the error: "Error: Flavor's disk is too small for requested image..."

You can't cram a bigger snapshot down into a smaller instance.

-- *Slide End* --

We have seen that snapshots are convenient. But that they do impact the performance of the VM for a short while. 
And that without extra steps, snapshots of running instances can be inexact. 

However, if we power the machine off first, then we can get a good snapshot. But run the big risk that we forget to 
start the machine again.

We have also seen that snapshots allow you to move between different sized machines easily.

And we have learnt that snapshots only save the primary drive of an instance. If you use the secondary drive, for 
example to put large data sets on, you will not backup that data with a snapshot.

-- *Slide* --

## Exercise

Make your shared snapshot private again!

-- *Slide End* --

Hold up a Red sticky note if you run into problems.

And a Green one once you are done.

-- *Slide* --

## Terminate your free computer!

Check to see if you have any computers running (Compute-Instances).

If so, terminate them.

* <span style="color:red">&#9632;</span> = Help me!
* <span style="color:green">&#9632;</span> = I'm ready to move on...

-- *Slide End* --


-- *Slide* --

### Why did we terminate our computers?

1. To conserve our trial tenancy
1. To conserve our trial tenancy
1. To conserve our trial tenancy
1. To conserve our trial tenancy
1. All of the above

-- *Slide End* --

**Answer:** The E's have it!

-- *Slide* --