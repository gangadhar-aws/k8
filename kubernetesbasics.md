### Kubernetes - K8 - Tool

#### Installation On Ubuntu Linux
To install kubernetes in Linux follow below commands..
1. Official Documention website : kubernetes.io
2. Download the latest release with the command:
```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```
3. Validate the binary (optional)
```sh
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```
Validate the kubectl binary against the checksum file:
```sh
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```
    - If valid, the output is:kubectl: OK
4. Install kubectl
```sh
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```
5. Test to ensure the version you installed is up-to-date:
```sh
kubectl version --client
```
6. Giving The Full Permission to Run the kubectl
```sh
chmod +x ./kubectl
```
7. move the file to binary folder in linux
```sh
sudo mv ./kubectl /usr/local/bin/kubectl
```
8. To run anywere kubectl go to root folder 
```sh
kubectl version
```
9. How to check Virtualations Enable or Not ?
```sh
grep -E --color 'vmx|svm' /proc/cpuinfo
```
### Installing Minikube
https://minikube.sigs.k8s.io/docs/start/
```sh
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```
set the path for minikube
```sh
sudo install minikube-linux-amd64 /usr/local/bin/
```sh
Start the Driver
```
#### Kubectl Commands How to Run a Pod using minicube enviroment
1. Create a pod 
```sh
kubectl run nginx --image=nginx
```
2. checking the pod status 
```sh
kubectl get pods
```
3. if you want more information about our pods
```sh
kubectl describe pod nginx
```
4. check the status of pod another command
```sh
kubectl get pods -o wide
```

### How to Run Yaml File to 
1. creating containers using yaml
```sh
kubectl apply -f nginx.yml
```
checking the status
```sh
kubectl get pods
```
if you want more details about your container
```sh
kubectl describe nginx
```
deleting the pod containers
```sh
kubectl delete pod podname/webapp
```

#### Replication Controller Vs Replica Set Commands
1. Replication Controller Commands
To Run playbook
```sh
kubectl create -f rc-difination.yml
```
2. To view list of created controllers 
```sh
kubectl get replicationcontroller
```
3. to view the pods for replications how many running
```sh
kubectl get pods
```

#### Replica Set
1. To Run replicaset yaml file
```sh
kubectl create -f replicaset-definition.yml
```
2. to view the pods in replicaset 
```sh
kubectl get replicaset
```


#### Updating the replicas how 
1. update teh replicas in yaml files and save and run the yaml file using replace command
```sh
kubectl replace -f replicaset-difinition.yml
```
2. using scale command give paramater of replicas desired numbers
```sh
kubectl scale --replicas=6 -f replicaset-difinition.yml
```
Common Commands
1. Creating replicaset using yaml file
```sh
kubectl create -f replicaset-difinition.yml
```
2. To see list of replicaset 
```sh
kubectl get replicaset
```
3. to delete the replicaset
```sh
kubectl delete replicaset myapp-aplicationame
```
    - also deletes all underlying pods
4. Scaale command
```sh
kubectl scale --replicas=6 -f replicaset-definitio
```
or
```sh
kubectl replace -f replicaset-difinition.yml
```


