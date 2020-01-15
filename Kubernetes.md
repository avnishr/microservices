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
