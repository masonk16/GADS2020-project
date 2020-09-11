## LAB : Google Cloud Fundamentals: Getting Started with GKE

## OBJECTIVES:

    - In this lab, you learn how to perform the following tasks:
        
        - Provision a Kubernetes cluster using Kubernetes Engine.

        - Deploy and manage Docker containers using kubectl.

## STEPS:

1. Confirm that needed APIs are enabled

    gcloud services list

2. Start a Kubernetes Engine cluster

    1. For convenience, place the zone that Qwiklabs assigned you to into an environment variable called MY_ZONE.

        export MY_ZONE=us-central1-a

    2. Start a Kubernetes cluster managed by Kubernetes Engine. Name the cluster webfrontend and configure it to run 2 nodes:

        gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2

    3. After the cluster is created, check your installed version of Kubernetes   

        kubectl version

3. Run and deploy a container

    1. Launch a single instance of the nginx container

        kubectl create deploy nginx --image=nginx:1.17.10

    2. View the pod running the nginx container

        kubectl get pods

    3. Expose the nginx container to the Internet

        kubectl expose deployment nginx --port 80 --type LoadBalancer

    4. View the new service 

        kubectl get services

    5. Scale up the number of pods running on your service

        kubectl scale deployment nginx --replicas 3

    6. Confirm that Kubernetes has updated the number of pods and your External IP address has not changed

        kubectl get pods
        kubectl get services