# Docker-sugoi

Docker image for sugoi projects

http://sugoi.bubar.info

If you want to use it for development :

 - Set DEBUG=1 in config.xml
 - Install the template compiler temploc2 
   - SSH into the neko container ( `docker exec -it theContainerId /bin/bash` ) 
   - run `haxelib install templo`
   - create the temploc2 executable `cd /usr/bin;haxelib run templo`
