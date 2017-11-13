# Docker-sugoi

Docker image for sugoi projects development

http://sugoi.bubar.info


## Troubleshooting

 - I get an error like `Error : Temploc compilation of error.mtt failed : Called from templo/Main.nml line 183`
 
 Temploc (the template engine) should be allowed to write in the **/lang/$lang/tmp** templates folders, where $lang can be "master", "fr" or "en". Doing a **chmod 777 /lang/master/tmp** should fix this.

