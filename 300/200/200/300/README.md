# 300 - Remove the GKE cluster

You can clean up the cluster with the ```gcloud``` command as follows:

```
$ gcloud container clusters delete <cluster name>
```

The return statement requests your confirmation of the deletion. Type ```y``` to confirm.

**NOTE**: Also you can delete your cluster via the Google Cloud console.

The cluster deletion may take time.

**WARNING**: After deleting the cluster, all data stored in it will be lost!