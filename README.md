jenkins-plugin-bluemix
=======================

Jenkins Cloud Plugin for Bluemix


The aim of the docker plugin is to be able to use a Bluemix Containers to
dynamically provision a slave, run a single build, then tear-down
that slave.

This repo is based on a fork of docker-plugin

It also uses as submodule a fork of docker-java


Because docker-java is a submodule, use --reqursive flag with git clone e.g.

git clone --recursive https://github.com/dunchych/jenkins-plugin-bluemix.git


Configuration
-------------
This plugin requires same configuration as Docker plugin for Jenkins

https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin

In addition, Bluemix login credentials need to be set up in Jenkins as per below. 
This allows plugin to automatically logs into Bluemix by itself. It will also re-login after every 72 hours upon use as will be seen in logs.  

The cf executable and cf ic plugin need to be installed and be on the $PATH for jenkins id as plugin executes these command via shell.

In Jenkins UI console - add credentials in global domain:
 
1.      Kind= Username with password
2.      Scope = Global
3.      Username = Bluemix id
4.      Password = Bluemix pwd
5.      ID must be = BLUEMIX   - a keyword , that’s how plugin finds these creds among other credentials in Jenkins
6.      Description is overloaded and is used to provide org:space  separated by colon e.g. as shown. Not ideal.. but saves messing with Jenkins UI to provide custom UI configs
