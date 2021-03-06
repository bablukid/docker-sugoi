# Docker-sugoi

Docker image for Sugoi projects.

Sugoi is a web framework for Haxe : http://sugoi.bubar.info

## Getting started
 - Install Docker
 - Download the files of this repo and copy them in a local folder
 - Go to this folder and type `docker-compose up` to start 2 dockers containers : one for the database (MySQL 5.7) and one for Apache and the Neko VM
 - The web root of your app is in `app/www/`
 - The code of your app is in `app/src/`
 - The templates of your app are in `app/lang/`


## Troubleshooting

#### I get an error like `Error : Temploc compilation of error.mtt failed : Called from templo/Main.nml line 183`
 
 Temploc (the template engine) should be allowed to write in the **/lang/$lang/tmp** templates folders, where $lang can be "master", "fr" or "en". Doing a **chmod 777 /lang/master/tmp** should fix this.

#### The web root looks empty
 
 By default, apache2 will look for files in a folder named **html**. If your project uses a different web root ( say "www" ), log into the neko container ( `docker exec -it $nekoContainerId /bin/bash` ) and make a simlink ( `cd /var/www/ && ln -s ./html ./www` )
 
#### The database schema looks incomplete
 
 Sugoi init the database schema when you run the app for the first time. If you already ran another app in this container, you surely still have the bad database schema.  Log into the mysql container and drop all the tables :
 - `docker exec -it $mysqlContainerId /bin/bash`
 - `mysql -uroot -p`
 - `use db;`
 - `DROP TABLE Error,Session,File,User,Variable;`
