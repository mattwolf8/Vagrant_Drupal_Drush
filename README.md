# vagrant_drupal7_drush

Vagrant Box with Drupal and Drush    |     
Mac OS X El Capitan Version: 10.11.4


SET UP VAGRANT
* 0. Create folder
* ***$ mkdir drupal_7_vagrant***
* 1. Open folder in terminal
* ***$ cd drupal_7_vagrant***
* 2. Download scotch box
* ***$ git clone https://github.com/scotch-io/scotch-box.git drupal***
* 3. Load vagrant
* ***$ cd drupal***
* ***$ vagrant up***
* 4. Visit the site [192.168.33.10/](http://192.168.33.10/)
* 5. ssh into the newly created box
* ***$ vagrant ssh***
  
ADDING A DATABASE
* 1. log into mysql
* ***$ mysql -uroot -proot***
* 2. create the database
* ***$ create database drupal7;***
* ***$ exit;***
  
INSTALLING DRUSH
* 1. Navigate to your vagrant (default) directory
* ***$ cd***
* 2. get the latest version of drush
* ***$ wget https://github.com/drush-ops/drush/archive/master.zip***
* 3. unzip master.zip
* ***$ unzip master.zip***
* 4. remove the master.zip file 
* ***$ rm master.zip***
* 5. rename drush-master
* ***$ cp -R drush-master/ drush/ && rm -R drush-master/***
* 6. Correct the permissions on the file:
* ***$ chmod u+x drush/drush***
* 7. Create the drush alias by editing your .bashrc file in your home directory:
* ***$ nano ~/.bashrc***
* 8. Add the following line to the bottom of your .bashrc file.
* ***$ alias drush='~/drush/drush'***
* 9. Exit nano, save on exit (Y)
* ***$ ^X***
* 10. Save on exit
* ***$ (Y)***
* 11. Reload the profile
* ***$ source ~/.bashrc***
  
INSTALL COMPOSER
* 1. Navigate to your home directory
* ***$ cd***
* 2. Create a bin directory
* ***$ mkdir bin***
* 3. Prepare Composer install
* ***$ curl -sS https://getcomposer.org/installer | php -- --install-dir=bin***
* 4. Navigate into drush folder
* ***$ cd drush***
* 5. Install Composer
* ***$ php ~/bin/composer.phar install***
  
INSTALL DRUPAL 7
* 1. navigate to cd /var/www
* 2. Download Drupal 7 
* ***$ drush dl drupal-7.x --drupal-project-rename=public***
* 3. navigate to public folder
* ***$ cd public***
* 4. Install drupal 7
* ***$ drush si standard --db-url=mysql://root:root@localhost/drupal7***
* 5. Copy the username and password given to you
* ***$ User name: admin***
* ***$ Password: PE3S6yVKqQ***
* ***$ (Your Password will be different)***
* Visit the site and login with your new credentials [192.168.33.10/]
* [192.168.33.10/](http://192.168.33.10/)
* If Errors:
* ***$ sudo service apache2 restart***
  
USING DRUSH
* 1. navigate to ***cd /var/www/public***
* 2. Install and activate a module
* ***$ drush en commerce -y***
* 3. Clear the cache
* ***$ drush cc***
  
REQUIREMENTS
* [Git](https://git-scm.com/downloads)
* [Virtual Box](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)

SOURCES
* [Drupal Environment in 10 Minutes](https://www.carnaghan.com/2015/05/drupal-development-environment-in-less-than-10-minutes)
* [How do I install Drush](https://www.greengeeks.com/kb/2874/how-do-i-install-drush/)
  
OPERATING SYSTEM 
* Mac OS X El Capitan
* Version: 10.11.4

 
   
   
   
 