## This is a step by step guide for usecase of Clusterip and Nodeport mode in Kubernetes service.
### Prequisites: You should have Minikube, Docker already installed.
### Note :  code is inside " ". Remove "" after pasting into terminal.

### 1st step : Get docker image required for this tutorial
  "docker pull trainwithshubham/django-todo-app:latest"

### 2nd step : start minikube cluster
  "minikube start"

### 3rd step: Write and apply the deployment.yml file
  "nano deployment.yml"
Paste the content of this file in opened window or just download both files... Ur choice :)

### 4th step: Apply the deployment to create our pod.
  "kubectl apply -f service.yml"

### 5th step: check IP of created pod
  "kubectl get pods -o wide"

### 6th step: Access the pod in ClusterIp mode.
  "curl -L http://<IP-of-Pod>:8000/todos -v"


## Now, For NODEPORT mode:
### 7th step: write and apply the service.yml file.
  "nano service.yml"
  "kubectl apply -f service.yml"

### 8th step: Check Minikube ip and port of nodeport service.
  "minikube ip"
  "kubectl get svc"
In my case, minikube ip is : 192.168.49.2  and port of nodeport service is : 30007

### 9th step: Access the pod with nodeport service. Write in Terminal.
  "curl -L http://<minikube-ip>:<port-of-nodeport-service>/todos -v"
  "curl -L http://192.168.49.2:30007/todos -v"

## You can access the application in your browser also.
### 10th step: Paste this address into your laptop/PC browser.
  "http://192.168.49.2:30007/todos"
Change Ip and port according to above step. :)
