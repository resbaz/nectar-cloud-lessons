# Snapshots: Backups, vertical scaling, sharing & transient storage (don’t rely on it!) (45 min)

## Snapshots

> Having updated her site, and made an off site backup of the data, Anna realises that if anything happened to the 
> machine that her site was on, she would have to go to a lot of effort to restore the site. She mentions this to
> a more technically literate friend, Sandy, saying "If only I could make a copy of it! Something like a photograph
> - quick and easy to do!".  Sandy laughs, and says: "Odd you should say 'photograph', as NeCTAR give you a facility to
> make a copy of a running machine. The term they use is 'snapshot'. The button to take it is right up there on the
> list of running instances in the dashboard. Give it a try next time you are logged in!"

**Exercise 1**

Find the snapshot button next to your running instance of drupal, and make a snapshot of it. Give it a useful name
that will allow you to know what it is when you come back to it weeks later.

Hold up a Green card once your instance has had its snapshot created.
And a Red card if you need help.

Whilst your snapshots are being taken, lets talk about what has just gone on under the hood.

The running virtual machine is suspended on its host machine for a short while. Whilst it is suspended a copy is made
of the underlying disk. Then the virtual machine is restarted. Finally the copy of the disk is 
transferred to the NeCTAR image store.

When this process is completed your snapshot will appear on the images tab of the project, with a type of "Snapshot". 
If all has gone well, the dashboard will take you to this tab automatically.

**Exercise 2**

To get a feel for the duration of the suspension, ssh into your running VM. In your home directory there
is a script by the name of `loop.sh`. Launch it by typing `./loop.sh`. It will start to count up, at the rate of one
count every half second or so. Readjust the windows on your desktop so that you can see the output in the terminal 
window as you snapshot your running instance. Then make a snapshot, and watch what happens to the output of the 
loop script.

All going well, you should see the output pause for a few seconds, then resume. On the other hand, the dashboard will 
continue well after the count has resumed, as it writes the copy of the disk to the image store.

To stop `loop.sh` from running, simply press the 'Ctrl' and the 'c' key together.

Hold up a Green card once you have seen the output pause.
And a Red card if you need help.

So snapshots look like they might be the answer to Anna's problem, but they will have a short impact on anyone
who is using her site at the time they taken.

# Backups

> Anna is delighted to have a way of making a convenient backup of the site. But when she tells another friend, Ben,
> of her discovery he is very dismissive: "Oh, that's just broken" he says.

**Question 1** 

Why does Ben think snapshots are broken?

**Choices**

    A. They are just too easy to do: suspicious enough!
    B. The magic nostrums aren't up to the task!
    C. Ben likes a life more complicated
    D. The state of the machine is not captured
    E. Cosmic rays can flip their bits.

**Answer 1**

    Whilst E is a topic for a good debate, the answer is:
    D. The state of the machine is not captured 

Lets take a look at this for a moment. The machine is paused, and then a copy of the hard drive is made. So any data
transfers that are happening between the machines drive and processor will be stopped mid flow. And then resumed
afterwards. So if its a file being read, all well and good. But what about files that are being written? Well, they 
might be caught mid write: which means that they won't be correctly captured.

**Q**  

Hold up a Red sticky note if you agree with Ben, 
and a Green one if you think that, snapshots are good to go.

**A** Sadly, Ben is right. Snapshots, although seductively easy to do, are prone to occasional failure due to writes
not being captured. The interesting thing about this is that you might never notice that your data has been corrupted
in this way.

**Exercise 3**

Delete your older, possibly unreliable, snapshot.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

> Alarmed by what Ben has told her, Anna does her research. And finds that in order to take good snapshots, she has
> to make sure that running programs have all written their contents to disk before the snapshot is made. There are
> a raft of fairly complicated steps that she has to take on the virtual machine to make sure that this is the case.
> Ann is depressed. But then she has an epiphany. If she shuts of her instance, then takes a snapshot of the shut
> off instance, all should be well.

**Exercise 4**

Power down your instance by shutting it off, then make a snapshot of it. Remember to wait till your instance is in the
shut off state before you try to make your snapshot.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

**Question 2** 

What's a big problem with Anna's new approach?

**Choices**

    A. You may forget to start your instance up again
    B. The powered off machine might not have saved its state properly
    C. The saved disk image is powerless
    D. The process overhead is too high
    E. How can you make a copy of a powered off disk?

**Answer 2**

    A. You may forget to start your instance up again

Yes: not only are you taking your site offline for a longer period than the momentary pause of a regular snapshot,
you are opening yourself to the possibility of forgetting to start it up again when you are done.

Remember the checklists of lesson II? This is where the power of checklists can help you. If you have an important site
that you don't want to be down for extended periods create a checklist for this process.

Also, if you have a lot of users, notify them of the outage. It's only polite. Also consider doing it as a regularly
scheduled event.

## Restore

> Shortly after making her snapshot backup, Anna realizes that her instance is no longer responding to the outside
> world. After confirming that she didn't leave it in the shut down state, and with some trepidation, she shuts it down 
> and launches the snapshot backup.

**Exercise 5**

This is where the rubber meets the road. Terminate your running instance, then go to the images tab of your project
and launch a new instance using the snapshot that you have just created. 
Modify the checklist from Lesson II and use it appropriately.

Once you are done make sure that your site is back up, and that you can ssh into the instance again.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

## Vertical Scaling

> Anna's site is becoming increasingly popular, and some of her visitors are complaining that it's getting slow under
> the load.

**Question 3** 

Anna's raft of kitten photographs has made it to the front page of the internet. Her server is struggling under the 
load. What can Anna do to solve this problem?

**Choices**

    A. Nothing
    B. Upgrade to a more powerful machine
    C. Buy a physical machine and port her site to it
    D. Make a support call to NeCTAR
    E. Pay NeCTAR for more network

**Answer 3**

    B. Upgrade to a more powerful machine

Remember the two nameless researchers whom I told you about at the start of these lessons, the two who spent over 
$20000 of their grant money on buying and upgrading their machines to complete their research? Well, if NeCTAR had
been around when they were doing their research, this is how simply they would have been able to resolve their prolbem.

**Exercise 6**

Terminate your running instance, then again go to the images tab of your project
and launch a new instance using the snapshot that you have just created. But this time round, use the largest flavour
that your project will allow you.

Modify the checklist from Lesson II and use it appropriately.

Once you are done make sure that your site is back up, and that you can ssh into the instance again.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

**Question 4** 

You'll notice that in your personal tenancy you can't run the largest machine image that you might want to.
What can you do to remedy this situation?

**Choices**

    A. Nothing
    B. Offer NeCTAR a load of money 
    C. Reach for your credit card and call Amazon
    D. Make a support call to NeCTAR
    E. Go to the allocation tab and complete an allocation request

**Answer 4**

    E. Go to the allocation tab and complete an allocation request

## Transient Storage

> Anna needs some extra disk space over and above the 10 Gig image size. While she's ssh'd into the image she
> types `df -h` (**d**isplay **f**ile usage). And sees that she has 30 Gig of free space on `/mnt`
> She decided to put her new files there.

*Q* Has Anna made a mistake?

Hold up a Red sticky note if you think she has.
Otherwise a green one if you think all is well.

*A*

We are going to do an experiment to see who's correct.

**Exercise 7**

Ssh into your running instance.

Do as Anna did and issue a `df -h`. You should see the same result as her.
Now create two files by:

```bash
sudo chmod a+rw /mnt/  # what does this do, and why is it needed?
echo "This is file one" > /mnt/file1.txt
echo "This is file two" > file2.txt
```

Confirm their contents:

```bash
more /mnt/file1.txt
more file2.txt
```

Exit the ssh shell, and make a snapshot of your running instance following our new best practices.
When it is complete then delete the original instance.

Launch a new instance from your new snapshot.

`ssh` into the new instance and run the following commands:

```bash
sudo chmod a+rw /mnt/  # what does this do, and why is it needed?
more file2.txt
more /mnt/file1.txt
```

All being well, you should get a "No such file" error when you try to look at file1.txt.

Hold up a Red sticky note if you need help,
Otherwise a green one when you are done.

So where's the missing `file1.txt`?

When you launch an instance, the instance is given a second hard drive with a fair amount of of space on it.
That is the extra space that Anna found and used.

*NB* When you make a snapshot, the snapshot is only of the primary drive. Anything on the secondary drive is not
saved. 

You can get and run some fairly grunty machines on the NeCTAR cloud. But snapshots will only save your small primary
drive. If you use the extra drive space you will not be able to back it up by means of snapshots!

*Q* So to repeat: has Anna made a mistake?

Hold up a Red sticky note if you think she has.
Otherwise a green one if you think all is well.

*A*

I'm hoping to see a sea of Red...

## Sharing

> Anna has now got quite a cat collection on the go: and would like to share it with a colleague. How would she do this?
 
Beware the size ratchet!

> Anna made a snapshot of a 10Gig machine: and is now trying to launch it as a 5Gig flavor. What happens?

> She gets two errors: "Error: Flavor's disk is too small for requested image... Error: Unable to launch instance named..."

We have seen that snapshots are convenient. But that they do impact the performance of the VM for a short while. 
And that without extra steps, snapshots of running instances can be inexact. 
However, if we power the machine off first, then we can get a good snapshot. But run the big risk that we forget to 
start the machine again.
We have also seen that snapshots allow you to move between different sized machines easily.
And we have learnt that snapshots only save the primary drive of an instance. If you use the secondary drive, for 
example to put large datasets on, you will not backup that data with a snapshot.