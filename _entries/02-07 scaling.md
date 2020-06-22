## **2.7 Scaling ARO Cluster** ##
### Scale the Azure Red Hat OpenShift cluster

You can scale the number of application nodes in the cluster using the Command Prompt.

Run the below on the ***Command Prompt*** to scale your cluster to 5 application nodes. Replace `<cluster name>` and `<resource group name>` with your applicable values. After a few minutes, `az openshift scale` will complete successfully and return a JSON document containing the scaled cluster details.

```sh
az openshift scale  --name <cluster name> --resource-group <resource group name> --compute-count 5
```

After the cluster has scaled successfully. You can run following command to verify the number of application nodes.

```sh
az openshift show --name <cluster name> --resource-group <resource group name> --query "agentPoolProfiles"[0]
```

Following is a sample output. You can notice that the value of `count` for `agentPoolProfiles` has been scaled to 5.

```sh
{
  "count": 5,
  "name": "compute",
  "osType": "Linux",
  "role": "compute",
  "subnetCidr": "10.0.0.0/24",
  "vmSize": "Standard_D4s_v3"
}
```

> **Resources**
> * [ARO Documentation - Scaling the cluster](https://docs.microsoft.com/en-us/azure/openshift/tutorial-scale-cluster)
