<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# P3 - Create Kubernetes Manifests

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eks3)

**Author:** Gilbert Emodi  
**Email:** zemodi99@gmail.com

---

## Create Kubernetes Manifests

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks3_b01876555)

---

## Introducing Today's Project!

In this project, I will set up manifest files because they are a key part of the Kubernetes deployment process. Manifest files give Kubernetes the instructions on HOW it should deploy the containerized application.

### Tools and concepts

I used Amazon EKS, eksctl, Git, Docker, ECR to create a Kubernetes cluster and build the container image of the backend of an app to deploy. Key concepts include using Manifest files, Deployments and Services to get ready for a Kubernetes deployment.

### Project reflection

need a job

This project took me approximately 2 hours including documentation. The most challenging part was understanding the deployment manifest. My favourite part was also being able to set up manifests files and understand how they work together.

---

## Project Set Up

### Kubernetes cluster

To set up today's project, I launched a Kubernetes cluster. Steps I took to do this included granting the EC2 instance permissions with IAM, and installing the eksctl command line tool. I created the cluster using the "eksctl" create command.

### Backend code

I retrieved the backend that I plan to deploy by cloning it from my team member's GitHub repository. Backend is the "brain" or logic of an application. For example, how an app stores, retrieves, and processes data.

### Container image

Once I cloned the backend code, I built a container image because Kubernetes requires apps to be in container images to deploy them. I used Docker to build a container image of the backend.

I also pushed the container image to a container registry, because this helps establish a single source of truth for the latest version of the container. To push the image to ECR, I ran the push commands that built and tagged the image.

---

## Manifest files

Kubernetes manifests are instructions for Kubernetes on how it should deploy the app. Manifests are helpful because they reduce manual work when we're wanting to deploy and manage applications across multiple containers (clusters).

A Kubernetes deployment manages multiple copies of the same containerized backened. The container image URL in my Deployment manifest tells Kubernetes the attributes of the container that I'd like Kuernetes to deploy.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks3_b01876554)

---

## Service Manifest

A Kubernetes Service exposes the application to network traffic. You need a Service manifest because the deployment manifest takes care of creating/managing the application except how users/apps will get access to them. No service manifest=no traffic

My Service manifest sets up a NodePort and targetPort, which means it maps traffic that get to port 8080 of the service to port 8080 of a container running the application.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks3_b01876555)

---

## Deployment Manifest

Annotating YAML files helped me understand the ins and outs of each command in the deployment manifest because I broke down and explained each line & their relationship to other commands too.

A notable line in the Deployment manifest is the number of replicas, which means the number of copies of the app I'd like to deploy across the cluster. Pods are relevant to this because 3 replicas = 3 pods (1:1 relationship).

One part of the Deployment manifest I still want to know more about is the namespace of a deployment because I am not too clear what it means and how it impacts Deployment/how it's used as metadata.

![Image](http://learn.nextwork.org/ecstatic_beige_calm_tarapirohe/uploads/aws-compute-eks3_6aae73e71)

---

---
