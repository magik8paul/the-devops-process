## the-devops-process

### Summary
The purpose of this repository is to provide an app and instructions for practicing DevSecOps principles using OpenShift.  The app isn't important.  It is a simple static web site.  All we really need is something we can change (Dev) that will then kick off a pipeline (Sec) that will then re-deploy the app automatically (Ops).  This repo is meant to document the steps needed to practice this DevSecOps methodology.

### Step 1 - Fire up CodeReady Containers
Run CRC to get a standalone OpenShift on your laptop or lab.  We'll be using this pared-down version of OCP for this exercise.
`$ crc start`

### Step 2 - Deploy and test the web app
Again, this is very simple on purpose.  Run the following command on your CRC instance to run the web app.
```
$ oc new-project devsecops
$ oc new-app nginx~https://github.com/magik8paul/the-devops-process.git --name webapp
$ oc expose svc/webapp
$ curl http://webapp-devsecops.apps-crc.testing
```
