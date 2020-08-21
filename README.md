# From Docker to Kubernetes: A Workshop

## What This Is

This is a workshop which introduces basic Docker and Kubernetes concepts - how to use it, why it's important, and where to get more information afterwards. This workshop is designed to be self-running, and contains practical and conceptual information inside the repository.

This workshop aims to for the comprehension and application of Docker knowledge.

## Prerequisites (Docker)

Before beginning this workshop, you must:

 - Install Docker ( [Instructions for Windows](https://docs.docker.com/v17.09/docker-for-windows/install/) / [Instructions for Macs](https://docs.docker.com/docker-for-mac/install/) )

 - Signup for an account in [Docker Hub](https://hub.docker.com/)

 - After signing up for an account, make sure you can login by running the following in your command line:

```
docker login
```

## Prerequisites (Kubernetes)

#### The Really Easy Way (Using Google Kubernetes Engine)

We can run the workshop with GKE (Google Kubernetes Engine), as part of Google Cloud. Google Cloud is one of the big three platform providers (along with AWS and Azure) that serve a lot of the industry - and signup is simple. It's also *free*, as long as we clean up later.

Instructions are [in this link](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/Setup-with-Google-Cloud.md). This is the best way to go!

Use this option if you are less familiar with the command line and want to experiment with Google Cloud.


#### The Not-so-easy Way (Using Minikube)

If you want to install a single-node Kubernetes cluster on your machine to play with, you can install with [Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/). With this way, you'll be able to see your deployments with your browser. 

[If you are using a Windows computer, use the instructions here.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/Setup-with-Minikube-Windows.md)

[Otherwise, if you are using a Mac, use the instructions here.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/Setup-with-Minikube-Mac.md)

Use this option if you're more familiar with with the command line. Keep in mind minikube is used for testing from your local machine and could be useful for your kubernetes usecase.


## Prerequisites (Git)

After you've setup an environment with Docker and Kubernetes, you're going to need some files from this repository for parts of this workshop.

You'll need to [create a Personal Access Token and use that token on the command line](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token).

## The Workshop


#### Docker

The Docker workshop has three components:

 - [Part 0: Docker Concepts.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/0-Concepts.md) In this part, we'll review *what Docker is* and why it is important.

 - [Part 1: Docker Basics.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/1-Basics.md) In this part of the workshop, we'll go through basic commands to run containers and pull images. 

 - [Part 2: Creating Docker Images.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/2-Images.md) We'll break down how to create your own Docker images.

 - [Part 3: Docker Tagging.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/3-Tags-and-Push.md) We'll take a look at what Docker tags are, and how to publish your images.


#### Kubernetes

 - [Part 4: Kubernetes Concepts.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/4-K8S-Concepts.md) In this part, we'll review what Kubernetes is and why companies use it.

 - [Part 5: Kubernetes Basics, and the Command Line.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/5-Kubernetes-Basics.md) In this part, we'll go through the Kubernetes command line, and make our way into creating our first objects.

 - [Part 6: Deployments and Services.](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/6-Deployments-and-Services.md) In this section, we'll go through how to make our pods available to the world, and how we can update them at scale.

 - [Part 7: Labels](https://github.com/DevOps-Girls/from-docker-to-kubernetes/blob/master/7-Labels.md). In this section, we stitch everything together.
