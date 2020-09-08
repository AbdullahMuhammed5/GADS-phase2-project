#Google Cloud Fundamentals: Getting Started with GKE

####Task 1: Sign in to the Google Cloud Platform (GCP) Console
Use the provided credentials.

####Task 2: Confirm that needed APIs are enabled
Use this command 

`gcloud services list`

Confirm that both of these APIs are enabled:

- Kubernetes Engine API
- Container Registry API

If either API is missing, install it. First run this command:

`gcloud services list --available` 

To list all available services on GCP.

Pick the service name and run this command:

`gcloud services enable SERVICE_NAME`

Replace the SERVICE_NAME with the service name you've copied.

Now you have all services installed and ready.

####Task 3: Start a Kubernetes Engine cluster
1. Add defualt zone.

    `export MY_ZONE=us-central1-a`

2. Start a Kubernetes cluster managed by Kubernetes Engine. Name the cluster webfrontend and configure it to run 2 nodes:

    `gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2`

3. After the cluster is created, check your installed version of Kubernetes using the kubectl version command:

    `kubectl version`
    
4. Check that your VM instances are previsioned and running.

    `gcloud compute instances list`
    
####Task 4: Run and deploy a container

1. Launch a single instance of the nginx container. (Nginx is a popular web server.)

    `kubectl create deploy nginx --image=nginx:1.17.10`

2. View the pod running the nginx container:
    
    `kubectl get pods`
    
3. Expose the nginx container to the Internet:
    
    `kubectl expose deployment nginx --port 80 --type LoadBalancer`
    
4. View the new service:

    `kubectl get services`
    
    You can use the displayed external IP address to test and contact the nginx container remotely.

5. Scale up the number of pods running on your service:

    `kubectl scale deployment nginx --replicas 3`
    
6. Confirm that Kubernetes has updated the number of pods:

    `kubectl get pods`
   













    