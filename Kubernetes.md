# Microservices


# Dockers

[A good youtube video series](https://www.youtube.com/watch?v=_3NUI5vasPk&list=PLMPZQTftRCS8Pp4wiiUruly5ODScvAwcQ)


## Create a deployment 


## Replica Set 

1. Ensure a min number of instances of a deployment are always running 

## Pods

1. Get the pod status 

kubectl get pod

kubectl get pod <name of pod> -o wide|json|yaml

kubectl describe pod <name of pod>

2. Running commands inside the shell on that pod

kubectl exec -it <name of pod> -- /bin/sh
  
3. Delete the pod that we created

kubectl delete pod <name of the pod>



## Creating a Spark Cluster 

There are two ways to create a Spark Operator. 

1. Using GCP 
2. Command line using Helm

### Using Helm

1. Set up a kubernetes cluster of 3 nodes, 2 cores each with 7.5 GB RAM each
2. Once the cluster is up, check the information 
kubectl cluster-info
3. Create a cluster role binding 
kubectl create clusterrolebinding spark-cluster-admin-binding --clusterrole=cluster-admin --user=kumarrastogia@hcl.com

4. helm install incubator/sparkoperator --namespace spark-operator
5. 
