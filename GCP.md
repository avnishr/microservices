

# Cleaning up GCP resources

Run the following command to delete your deployment and related resources:

gcloud deployment-manager --project=${PROJECT} deployments delete ${DEPLOYMENT_NAME}

Delete your Cloud Storage bucket when you’ve finished with it:

gsutil rm -r gs://${BUCKET_NAME}
As an alternative to the command line, you can delete the various resources using the GCP Console.
