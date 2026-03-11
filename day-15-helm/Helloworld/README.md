# Helm Deployment Practical on Kubernetes (EKS)

## Step 1: Install Helm
First, Helm was installed on the cluster.

             https://github.com/helm/helm/releases

             wget https://get.helm.sh/helm-v3.14.0-linux-amd64.tar.gz

             tar -zxvf helm-v3.14.0-linux-amd64.tar.gz

             mv linux-amd64/helm /usr/local/bin/helm

             chmod 777 /usr/local/bin/helm  # give permissions 

             helm version 


This command verifies that Helm is installed successfully.

Step 2: Go to Helm Chart Directory

The Helm chart folder name was project-1.

First, I went inside the project directory to check the files.

cd project-1

Here I checked the chart structure and configuration files like:

Chart.yaml

values.yaml

templates/

Step 3: Update Docker Image

Inside values.yaml, I updated the Docker image name taken from Docker Hub.

Example:

image:
  repository: veeranarni/hotstar
Step 4: Configure NodePort

In the service configuration, I added a NodePort.

Example:

nodePort: 30000

NodePort allows the application to be accessed externally using:

http://<NodeIP>:30000
Step 5: Go Outside the Project Folder

Helm install command should not be executed inside the project folder.

So I moved one directory back:

cd ..
Step 6: Install the Helm Chart

Then I installed the Helm chart.

helm install release1 ./project-1
Step 7: Check Cluster Resources

Check Nodes:

kubectl get nodes

Check Pods:

kubectl get pods

Check Services:

kubectl get svc
Step 8: Create Another Release

I also created another release using the same chart.

helm install release2 ./project-1

This created another pod in the cluster.

Step 9: Upgrade Instead of Reinstall

If we make changes in the chart, we should use upgrade instead of install.

helm upgrade release2 ./project-1

After upgrade:

A new pod was created

The old pod was automatically deleted

This is called a rolling update in Kubernetes.

Step 10: Access Application

After deployment:

Security Group of the cluster was updated.

NodePort was opened.

Then the application was accessed in the browser using:

http://<NodePublicIP>:30000

If the Docker image is nginx, the Nginx default page will open in the browser.

Conclusion

In this practical:

Installed Helm

Modified values.yaml

Used Docker Hub image

Configured NodePort

Installed Helm chart

Created multiple releases

Performed Helm upgrade

Accessed application using Node IP and NodePort

Helm simplifies Kubernetes application deployment and management.
