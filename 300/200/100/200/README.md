# 200 - Create the EKS Cluster

**IMPORTANT**: To run a 3-node pxc cluster, you will need at least a 3-node cluster with 2vCPUs available. The database will not be created if you attempt to create a database cluster in a Kubernetes cluster without sufficient resources.

To create the EKS cluster, do the following steps:

1. Settled the required cluster details:

  - name of your EKS cluster
  - AWS region in which you wish to deploy your cluster
  - the number of nodes you would like to have
  - the desired ratio between [on-demand](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-on-demand-instances.html) and [spot](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html) instances in the total number of nodes.

**Note**: [spot](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances.html) instances are not recommended for production environment but may be useful for testing purposes.

2. Create your EKS cluster [following the official cluster creation instructions](https://docs.aws.amazon.com/eks/latest/userguide/create-cluster.html).

3. [Install the Amazon EBS CSI driver](https://docs.aws.amazon.com/eks/latest/userguide/ebs-csi.html) on your cluster. See the [official documentation](https://docs.aws.amazon.com/eks/latest/userguide/managing-ebs-csi.html) on adding it as an Amazon EKS add-on.
