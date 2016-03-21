-- *Slide* --

# Lesson VIII: The object store (15 min)

Your supercharged USB stick

-- *Slide End* --

[Ideas](https://developer.rackspace.com/blog/openstack-swift-use-cases-in-rackspace-private-cloud/)
[Borrow?](https://developer.rackspace.com/blog/mysql-backup-to-rackspace-cloud-files/)

There's another powerful reason to use the Research Cloud: access to storage which is kept locally in Australia and 
available on the high speed [AARNET](https://www.aarnet.edu.au/about-us) backbone. There are different forms of
storage available: but we are only going to look at the Object Store.

The *Object Store* is an ideal replacement for the usb sticks that some people tend to carry 
around with them: You can upload and download files to it from any browser: and you can keep those files private,
or share those files with the world if you want.

Some people even publish whole websites from the object store!
 
On top of that, any file that you give it is backed up in triplicate, and each of the the copies is monitored for 
degradation.

Any bit rot, and the faulty file is replaced with a good copy. 

There is some terminology that you need to know.

Files are called objects. Unsurprisingly, since it's called the object store.
 
And objects go into containers.

-- *Slide* --

### On the NeCTAR dashboard what's the Object Store's child tab called?

1. Directories
1. Loading
1. Containers
1. Boxes
1. Objects

-- *Slide End* --

Please hold up a Red sticky note if you need help finding it
Otherwise, hold up your answer...

**Answer:** C: Containers.

This tab is where you create containers, and then put files (or objects) into the containers.

It is a very, very simple interface. So simple it's actually clunky IMHO. 

Ok: just watch what I do.

>  (demonstrate creating a container, uploading a file into it)

And the way that you share with the public, is to mark the container as being "public". If you click on the resultant 
"public" link you get some well formed xml. Just take the name of the object and append it to the url in the title bar 
to make a public handle that you can share with the world.

>  (demonstrate making the container public, and viewing the image in a browser)

Now for a challenge. There is no checklist!

-- *Slide* --

## Activity 1:

Can you create a container named **resbaz**
in the Object Store and upload a picture to it? 

**NB:** preserve the file extension as you name it.

Once your done, can you delete it all?

-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

-- *Slide* --

## Share an image

<div align="left">
▢ Create a container (make it public)<br/>
▢ Upload a picture into it <br/>
▢ Click on the resultant public link <br/>
▢ Append '/' and the object name to the browser address <br/>
▢ Do you see the image in your browser? <br/>
</div>

-- *Slide End* --

Please hold up a Red sticky note if you need help
and a Green one once you are done.

You have just worked out how to build a url in your browser to access items in a container. 
If the container is public you can share these addresses and others will be able to access those 
files.

-- *Slide* --

### You mark a container as being public. Which of the following are affected:

1. Just the first file in the container
1. None of the files in the container
1. The mittens of celestial kittens
1. All of the files in the container
1. The last file in the container

?

-- *Slide End* --

**Answer:** D: all of the files in the container. So you need to use this feature with care!

- - - 
