
### ***Azure subscription and Azure Red Hat OpenShift environment***

Once the environment is provisioned, a screen with all the appropriate lab credentials will be presented. Additionally, you'll have your Azure Red Hat OpenShift cluster endpoint. The credentials will also be emailed to the email address entered at registration.

![Credentials](../media/environment.png)

You can now skip the **Create cluster** section and jump to [create project](#createproject).


### Tools

#### Azure Cloud Shell

You can use the Azure Cloud Shell accessible at <https://shell.azure.com> once you login with an Azure subscription.


Head over to <https://shell.azure.com> and sign in with your Azure Subscription details.

Select **Bash** as your shell.

![Select Bash](../media/cloudshell/0-bash.png)

Select **Show advanced settings**

![Select show advanced settings](../media/cloudshell/1-mountstorage-advanced.png)

Set the **Storage account** and **File share** names to your resource group name (all lowercase, without any special characters). Leave other settings unchanged, then hit **Create storage**

![Azure Cloud Shell](../media/cloudshell/2-storageaccount-fileshare.png)

You should now have access to the Azure Cloud Shell

![Set the storage account and fileshare names](../media/cloudshell/3-cloudshell.png)


#### OpenShift CLI (oc)

You'll need to [download the latest OpenShift CLI (oc)](https://github.com/openshift/origin/releases/tag/v3.11.0) client tools for OpenShift 3.11. You can follow the steps below on the Azure Cloud Shell.


> **Note** You'll need to change the link below to the latest link you get from the page.
> ![GitHub release links](../media/github-oc-release.png)

Please run following commands on Azure Cloud Shell to download and setup the OpenShift client.

```sh
cd ~
wget https://github.com/openshift/origin/releases/download/v3.11.0/openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz

mkdir openshift

tar -zxvf openshift-origin-client-tools-v3.11.0-0cbc58b-linux-64bit.tar.gz -C openshift --strip-components=1

echo 'export PATH=$PATH:~/openshift' >> ~/.bashrc && source ~/.bashrc

```

The OpenShift CLI (oc) is now installed.


#### GitHub Account
You'll need a personal GitHub account. You can sign up for free [here](https://github.com/join).
