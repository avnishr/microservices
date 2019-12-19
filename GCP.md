

# Examining Kubeflow cluster

If you want to examine your cluster while waiting for the Kubeflow dashboard to be available, you can use kubectl to connect to your cluster:

Connect your Cloud Shell session to the cluster:

```
gcloud container clusters get-credentials \

  ${DEPLOYMENT_NAME} --zone ${ZONE} --project ${PROJECT}
```


Switch to the kubeflow namespace to see the resources on the Kubeflow cluster:

```
kubectl config set-context $(kubectl config current-context) --namespace=kubeflow
````

Check the resources deployed in the kubeflow namespace:

```
kubectl get all
```


# Cleaning up GCP resources

Run the following command to delete your deployment and related resources:

gcloud deployment-manager --project=${PROJECT} deployments delete ${DEPLOYMENT_NAME}

Delete your Cloud Storage bucket when you’ve finished with it:

gsutil rm -r gs://${BUCKET_NAME}
As an alternative to the command line, you can delete the various resources using the GCP Console.
