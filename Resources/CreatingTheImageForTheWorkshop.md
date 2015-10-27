# Creating the workshop image

## Choose your base Ubuntu image

The course is currently built around an Ubuntu base image.

On several other presentations we've done there have been issues with the NeCTAR provided images when
doing updates from AARNET. Hence you may prefer to base your image on one provided by Ubuntu, as it
isolates you from this possible point of failure.

Either way, choose an [Ubuntu LTS](https://wiki.ubuntu.com/LTS) image as your base. This means that you
won't have to rebuild the image every six months or so: something that has bitten the origanal developers
of this course!

For the purpose of these notes we are using the 14.04 LTS release.

If wanting to use an Ubuntu provided image, go to the images tab of the dashboard: 

https://dashboard.rc.nectar.org.au/project/images/

Click on the "Create Image" button.

Fill in the requested Name and Description details.

When you get to the image location box, you need to enter the url of the image on the Ubuntu site. To find
this, go to the Ubuntu cloud image repository at http://cloud-images.ubuntu.com/, open the folder of the
image you are interested in, then open the "current" folder (current is the most recent). Then scroll all
the way to the bottom, and copy the url for the amd64 server cloud image. In our case that is:

https://cloud-images.ubuntu.com/trusty/current/trusty-server-cloudimg-amd64-disk1.img

Paste this url location into the image location box.

The format is "Raw".

The architecture is "x86_64".

Leave all the other fields blank and select the "Create Image" button.

Then wait awhile for the image to be imported.

If wanting to use the NeCTAR provided image, simply select the desired Ubuntu LTS image from the list of
NeCTAR provided images when launching the instance.

## Launch your instance

Don't forget to choose security groups that allow `ssh` and http access (ports 22 and 80). Also don't forget to
select the appropriate keypair to allow `ssh` access.

Once you have launched your chosen image, `ssh` into it.

## On your instance

### Set up `loop.sh`

Set up the required files in the ubuntu users home directory. First, `loop.sh`:

```bash
cat > loop.sh <<- EndOfMessage
#!/bin/bash
COUNTER=0
while [ \$COUNTER -lt 10000000 ]; do
	echo The counter is \$COUNTER
	let COUNTER=COUNTER+1
	sleep .5
done
EndOfMessage
```

Then make it executable:

```bash
chmod +x loop.sh 
```
### Set up `today.txt`

Then [`today.txt`](http://johnhenrymuller.com/today):

```bash
cat > today.txt <<- EndOfMessage
If nothing else, today I am going to ___________.

I am going to do this by ______ then _____ then ______.

If I do this and only this, today will be a good day.
EndOfMessage
```

### Install apache2

```bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install apache2
# check to see if installed by going to http://<your instance IP address>
# note that check this you need to have port 80 open in your security groups
```

### Install and prepare mysql

```bash
# install mysql and the php files to access it
sudo apt-get install mysql-server php5-mysql
# make a note of the password you selected for the root mysql user
# then tell mysql to make its tables
sudo mysql_install_db
# finally, secure the installation (provide the root password, 
# then just accept all the default suggestions by hitting 'enter'
sudo mysql_secure_installation
# now install php 5
sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt
# then set up the drupal database
mysql -u root -p
```

In the resultant mysql environment, set up the drupal database and drupal user, taking care to use a good
password that you again make a note of:

```sql
CREATE DATABASE drupal;
CREATE USER drupaluser@localhost IDENTIFIED BY 'your_good_password';
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,INDEX,ALTER,CREATE TEMPORARY TABLES,LOCK TABLES ON drupal.* TO drupaluser@localhost;
FLUSH PRIVILEGES;
exit
```

### Install php5

```bash
sudo apt-get install php5-gd php5-curl libssh2-php
sudo nano /etc/php5/apache2/php.ini
```

Search for the `expose_php` and the `allow_url_fopen` directives and set both of them to "Off":

Save and close.

```bash
sudo a2enmod rewrite
sudo nano /etc/apache2/sites-enabled/000-default.conf
```

Below the `DocumentRoot /var/www/html` add:

    <Directory /var/www/html>
        AllowOverride All
    </Directory>

and save and close.

Restart apache:

```bash
sudo service apache2 restart
```

### Install Drupal

Get the url for the Drupal release you want by going to the Drupal download page:

https://www.drupal.org/project/drupal

And finding the url for the latest 7.x series recommended release.

Back on your instance `wget` that release:

```bash
wget http://ftp.drupal.org/files/projects/drupal-7.41.tar.gz
tar xzvf drupal*
cd drupal*
sudo rsync -avz . /var/www/html
cd /var/www/html
cp /var/www/html/sites/default/default.settings.php /var/www/html/sites/default/settings.php
chmod 664 /var/www/html/sites/default/settings.php
sudo chown -R :www-data /var/www/html/*
```

In your browser navigate to your new Drupal site:

http://<your instance ip>/

and start the configuration process.

Select the 'standard' option and continue.

When you get to the database section, use the `drupal` database, and use the `drupaluser` and password
you set up earlier.

On the "Configure site" rememember to make a note of the drupal administrator name (say `drupaladmin`)
and make a note of it (again).

Once configured, 

Navigate to the home page, and select "add content"

Select "Basic Page"

Then give the resultant page the title "The research cat"
Select "Full Html" for the text format and paste in:

```html
<a title="By No machine-readable author provided. 
  Bertilvidet~commonswiki assumed (based on copyright claims). 
  [GFDL (http://www.gnu.org/copyleft/fdl.html), CC-BY-SA-3.0 
  (http://creativecommons.org/licenses/by-sa/3.0/) or CC BY 2.5 
  (http://creativecommons.org/licenses/by/2.5)], via Wikimedia Commons" 
  href="https://commons.wikimedia.org/wiki/File%3ATurkish_Van_Cat.jpg">
  <img width="512" alt="Turkish Van Cat" src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/22/Turkish_Van_Cat.jpg/512px-Turkish_Van_Cat.jpg"/>
  </a>
```

Under publishing options, select "Promoted to front page" and save.

Now when you visit the home page, you should see the cat image on it...

Then set up the site information to whatever you want it to be at Configuration -> Site Information.

Finally, back in your `ssh` shell:

```bash
chmod 644 /var/www/html/sites/default/settings.php
```

### Write down the passwords for future use...

Change back to your home directory, and save the passwords that you used above in the file named `info.txt`:

```bash
cd ~
nano info.txt
```

with the contents along the lines of:

    msqlroot: a_big_complex_password
    # drupal in the mysql database
    drupaluser: a_big_complex_password
    # the drupal admin user
    drupaladmin: a_big_complex_password

Then **shut the instance off** (do not terminate it) and make a snapshot of it named `mpaulo_drupal7`.

Go to the snapshot and edit it:

* change its description to "The ResBaz cloud workshop image"
* make it public

Once that is done, start it and test that all works as expected.

Only then terminate the source instance that you built above.





