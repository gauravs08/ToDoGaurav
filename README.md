# ToDo Service

For this task you'll write a To-Do server and command-line client. You'll also
deploy it to a provided Kubernetes cluster :)

Send the Google account you will use with Google Cloud to **ops@delivered.im**. Your account will be given the necessary access to complete the assignment and you will not be charged for any usage.

Feel free to change these minimal requirements if you think something would be
better in a different way, but keeping the features of adding, deleting, and
listing ToDo items.

Create a branch named after you (your first name) in this repository and commit all your work products there.

## Coding tasks

### CLI

The command line app should support the following flags:

- `todo -l`
  - Would list my current ToDo items.
- `todo -i {JSON ToDo here}`
  - Would insert a new ToDo item with arbitrary JSON content. Server assigns the
    ID.
- `todo -d ID`
  - Would delete the ToDo with a given ID.

### Server

The server should expose a REST API to support the 3 basic CLI operations.

For storage, you won't be able to write to disk in the cluster.

## Deployment tasks

### Connect to the cluster

Install the [Google Cloud SDK](https://cloud.google.com/sdk/) for your platform.
Once that's done, configure it for `external-assignment-1018` and zone `europe-north1-a`.
You can find SDK quickstart guide [here](https://cloud.google.com/sdk/docs/quickstarts).

Get credentials for cluster:
```
gcloud container clusters get-credentials <your-first-name-here> --zone=europe-north1-a
```
To interact with the cluster you need [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/).
Make sure you can connect to it:
```
kubectl cluster-info
```
Send an e-mail to **ops@delivered.im** if something doesn't work as expected in this stage.


### Dockerfile preparation and upload to registry

Prepare a `Dockerfile` for your server, and upload it to Google Cloud Container Registry of the project.
To be able to work with the registry you need to setup credentials for it:
```
gcloud auth configure-docker
```
For more information about working with Google Cloud Container Registry see [the documentation](https://cloud.google.com/container-registry/docs/pushing-and-pulling).

Tag the docker image as `eu.gcr.io/external-assignment-1018/todo`.


### Kubernetes manifests

You should write a service and deployment manifest for your server, making sure
that it gets a public IP assigned so that the CLI can access to it.

### Applying manifests and testing

Apply those manifests to the cluster! Let us know what you would do to know if
everything went well 😈
