# Web requests and Behat tests

* [Download ZIP](http://tutorials.pipeline-dev.services.acquia.io/pipelinestutorial501.zip)
* [Watch video](https://drive.google.com/a/acquia.com/file/d/0BwBnqz3kkaPuY2M3blNlc1pOTk0)

Minor edit

The purpose of the 501 tutorial is to demonstrate the Pipelines web env and show how you can run Behat as an example use of the web
environment. One of the Behat tests will publish the email variable you encypt to a private Pipelines validation hipchat room, 
confirming to the Pipelines product ownership team that you have completed this tutorial and are qualified on Pipelines.

Copy the files and directories from this directory into your Acquia Cloud repository. To get the files, clone this repository and checkout the pipelines501 branch, or you can [download the ZIP file here](http://tutorials.pipeline-dev.services.acquia.io/pipelinestutorial501.zip).

The steps are:

* Clear out a branch in your Acquia Cloud repo so that only the tutorial files are included.
* Commit the sample files to your Cloud repo.
* Add the encrypted variable containing your email address to the Pipelines YAML file. We recommend copying this line and editing the email:
```
   echo <<your email address>> | pipelines encrypt - --add variables.global.EMAIL
```
For example:
   echo "yourname@mail.com" | pipelines encrypt - --add variables.global.EMAIL

* Commit the changed YAML file and push to Cloud:
```
   git commit -a -m 'encrypted email address'
   git push origin master
```
* Run ```pipelines start```.
* When ```pipelines status``` shows the job is complete, run ```pipeline logs``` to see the results of the Behat tests.  Your email address will already have been posted to the Pipelines validation hipchat room.
