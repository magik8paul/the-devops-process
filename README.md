## the-devops-process

### Summary
The purpose of this repository is to provide an app and instructions for practicing DevSecOps principles using OpenShift.  The app isn't important.  It is a simple static web site.  All we really need is something we can change (Dev) that will then kick off a pipeline (Sec) that will then re-deploy the app automatically (Ops).  This repo is meant to document the steps needed to practice this DevSecOps methodology.

#### Step 1 - Fire up CodeReady Containers
We'll be using a pared-down version of OCP called CodeReady Containers for this exercise.  Refer to [the official documentation](https://access.redhat.com/documentation/en-us/red_hat_codeready_containers/) to get CRC running on your laptop or lab.

#### Step 2 - Deploy and test the web app
Once CRC is running and you're logged in via `oc`, run the following commands on your CRC instance to run and validate the web app.
```
$ oc new-project devsecops
$ oc new-app nginx~https://github.com/magik8paul/the-devops-process.git --name webapp
$ oc expose svc/webapp
$ curl http://webapp-devsecops.apps-crc.testing
```
You should see a simple HTML doc on vegetable gardening.  Again, this is very simple on purpose.

#### Step 3 - Install the OpenShift Pipelines operator
Launch the OpenShift web console and install the OpenShift Pipelines operator.
`$ CRC console`
Navigate to Operators > OperatorHub and install 'OpenShift Pipelines Operator' on the 'devsecops' project.
You should now see a 'Pipelines' section in the web console.
