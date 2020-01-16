

# Examining Kubeflow cluster

Once the kubeflow cluster comes up, we can find out the external ip address (URL) 

```
kubectl -n istio-system get ingress
```

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


# How to run a docker model with tensor flow
docker run -p 8501:8501 --mount type=bind,source=/tmp/model,target=/models/mnist2 -e MODEL_NAME=mnist2 --name mnist2 -t tensorflow/serving

# How to query the model using HTTP
The following code snippet can be used 

import sys
import json
import requests
from keras.datasets import fashion_mnist


def get_prediction(server_host='127.0.0.1', server_port=9000):
    (trainX, trainy), (testX, testy) = fashion_mnist.load_data()
    testX = testX / 255
    testX = testX.reshape(testX.shape[0], 28, 28, 1)
    data = json.dumps({"signature_name": "serving_default", "instances": testX[0:3].tolist()})
    headers = {"content-type": "application/json"}
    json_response = requests.post('http://localhost:8501/v1/models/mnist2:predict', data=data, headers=headers)
    print(json_response)
    
    
```
gcloud deployment-manager --project=${PROJECT} deployments delete ${DEPLOYMENT_NAME}
```

Delete your Cloud Storage bucket when you’ve finished with it:
```
gsutil rm -r gs://${BUCKET_NAME}
```

As an alternative to the command line, you can delete the various resources using the GCP Console.


# Setting up a sample MNIST program 

https://www.kubeflow.org/docs/gke/pipelines-tutorial/

# Kubeflow sample github code
https://github.com/kubeflow/examples


docker run -p 8501:8501 --mount type=bind,source=/tmp/model,target=/models/mnist2 -e MODEL_NAME=mnist2 --name mnist2 -t tensorflow/serving


