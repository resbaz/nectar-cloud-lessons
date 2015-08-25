# Lesson VIII: The object store (30 min)

[Ideas](https://developer.rackspace.com/blog/openstack-swift-use-cases-in-rackspace-private-cloud/)
[Test](https://developer.rackspace.com/blog/backing-up-cinder-volumes-to-swift/)
[Borrow?](https://developer.rackspace.com/blog/mysql-backup-to-rackspace-cloud-files/)

Remember in Lesson 1 that we said the  *Object Store* is an ideal replacement for the usb sticks that some 
people tend to carry around?
 
On top of that, any file that you give it is backed up in triplicate, and each of the the copies is monitored for 
degradation.

Any bit rot, and the faulty file is replaced with a good one. 

You can upload and download files via your browser: and you can share them with the world. 
Some people have published whole websites from the object store!

There is some terminology that you need to know.

Files are called objects. And objects go into containers.

And this tab is where you create containers, and then put files (or objects) into the containers.

It is a very, very simple interface. So simple it's clunky. 

Ok: just watch what I do.

>  (demonstrate creating a container, uploading a file into it)

And the way that you share with the public, is to mark the container as being "public". If you click on the resultant 
“public” link you get some well formed xml. Just take the name of the object and append it to the url in the title bar 
to make a public handle that you can share with the world.

>  (demonstrate making the container public, and viewing the image in a browser)

Now for a challenge.

## Activity 1:

Please hold up a Red sticky note if you need help
and a Green one once you are done.