# 200 - Create and configure the GKE cluster

**IMPORTANT**: To run a 3-node pxc cluster, you will need at least a 3-node cluster with 2vCPUs available. The database will not be created if you attempt to create a database cluster in a Kubernetes cluster without sufficient resources.

You can configure the settings using the ```gcloud``` tool. You can run it either in the [Cloud Shell](https://cloud.google.com/shell/docs/quickstart) or in your local shell (if you have installed Google Cloud SDK locally on the previous step). The following command will create a cluster named ```my-cluster-name```:

```
$ gcloud container clusters create my-cluster-name --project <project name> --zone us-central1-a --cluster-version 1.25 --machine-type n1-standard-4 --num-nodes=3
```

**NOTE**: You must edit the previous command and other command-line statements to replace the ```<project name>``` placeholder with your project name. You may also be required to edit the *zone location*, which is set to ```us-central1``` in the above example. Other parameters specify that we are creating a cluster with 3 nodes and with machine type of 4 vCPUs.

You may wait a few minutes for the cluster to be generated.

When the process is over, you can see it listed in the Google Cloud console.

![gke-quickstart-cluster-connect](https://github.com/vanHeemstraSystems/percona/assets/1499433/329adc6e-47ce-4668-93f1-ff32f19328ca)

Now you should configure the command-line access to your newly created cluster to make ```kubectl``` be able to use it.

In the Google Cloud Console, select your cluster and then click the *Connect* shown on the above image. You will see the connect statement which configures the command-line access. After you have edited the statement, you may run the command in your local shell:

```
$ gcloud container clusters get-credentials my-cluster-name --zone us-central1-a --project <project name>
```

Finally, use your [Cloud Identity and Access Management (Cloud IAM)](https://cloud.google.com/iam) to control access to the cluster. The following command will give you the ability to create Roles and RoleBindings:

```
$ kubectl create clusterrolebinding cluster-admin-binding --clusterrole cluster-admin --user $(gcloud config get-value core/account)
```

Expected output:

```
clusterrolebinding.rbac.authorization.k8s.io/cluster-admin-binding created
```