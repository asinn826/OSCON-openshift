# Getting started with OpenShift Origin on Azure

OpenShift is a container deployment and management tool developed by Red Hat. It is built on top of Docker containers and uses Kubernetes as its container orchestrator. OpenShift Origin is the open source upstream community OpenShift project; Red Hat also sells OpenShift Container Platform, which is an enterprise-grade container also developed and supported by Red Hat.

In this lab, you will get a taste for creating and deploying applications using OpenShift running on Azure infrastructure. You will create a Node.js application with a MongoDB database, push updates to the code base, and see updates deploy in real time with minimal work needed.

## Prerequisites:
For this lab, you will need the following:
1. A GitHub account (if you don't have one, this lab is still doable but becomes much simpler - you won't be able to use the fancy automated Git deployment)
    - You can sign up for a GitHub account [here](https://github.com/join). It takes less than a minute!
1. Visual Studio Code installed (already done for you in the lab machine)
1. An OpenShift Origin cluster (predeployed for you)

    For the purposes of this lab, we have deployed 6 OpenShift Origin clusters on Azure. The links are as follows:
    - aka.ms/openshift1
    - aka.ms/openshift2
    - aka.ms/openshift3
    - aka.ms/openshift4
    - aka.ms/openshift5
    - aka.ms/openshift6

    Please use the cluster corresponding to your lab machine. For example, if you are at machine #1, you would use the cluster located at aka.ms/openshift1.

## Part 1: Starting with OpenShift on Azure
Login to your OpenShift cluster with the following credentials:

        Username: clusteradmin
        Password: DoNotCheckMeIn!

Once you have logged in, you will see all the images available to you. Note that Open Service Broker has already been configured so that you can also deploy Azure services from within OpenShift!

Play around with the UI if you want or continue to part 2.

## Part 2: Starting with GitHub
//TODO: add some intro verbiage about forking

- Fork the project from https://github.com/asinn826/nodejs-ex //TODO: CHANGE THIS LINK to your GitHub account
- Clone the forked project onto your local machine

## Part 3: Starting with Visual Studio Code
Visual Studio Code is a cross-platform code editor developed by Microsoft that supports a wide selection of languages and features. One cool feature within VSCode is native Git integration. We will be using the Git integration during this lab. You may skip this section if you don't have a GitHub account.

- Open the cloned project in VSCode
- play with it if you want

## Part 4: Deploying an image to a container
Now we will deploy an image to a container within OpenShift Origin
- go back to OpenShift
- Deploy a NodeJS + MongoDB image
    - ephemeral image means that your application database will be lost of the host VM is rebooted
- when asked for a git repo, put in the link to your forked repo
- press next until it deploys, then click the link to go to the configurations
- go to build configurations and add git hooks
- go to the nip.io link

## Part 5: Play with the source to image workflow
- Go back to VSCode
- Make a change to the HTML
    * // TODO put example here
- Open the Source Control view
- note the changed files; add them to staging
- type your commit message then ctrl+enter to commit
- push via the 3 dots or terminal
    - 3 dots: // TODO: show screenshot
    - terminal: 
        - press ctrl + ` and select bash
        - navigate to your repo directory
        - git push
- go back to your project in OpenShift, and notice a new build has started
- go to the nip.io link and refresh - note that it has updated to show your changes without you needing to do anything!

## Part 6 (optional): Open Service Broker for Azure - OpenShift integration
- notice that in the home page you also see Azure services
- OSBA for Azure has now moved out of preview, and is now 1.0 - you can deploy various services directly from OpenShift
- //TODO: pick a service to deploy 
