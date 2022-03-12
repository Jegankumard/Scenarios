## Create a storage account to host the static website.
- Click + Add to create a new resource.
- Search for and select Storage Account.
- For Resource Group, select the existing resource group if it is not already selected.
- Enter a Storage account name that begins with staticsite. You may need to add some characters at the end of the name to make it unique.
- Click Review + Create, then Create.

## Configure the storage account for static site hosting.
- Wait for your storage account to finish being created. When viewing the resource group, you can click Refresh. When your storage account appears in the list, it has been created.
- Click on your storage account, then click Static Website on the left side of the storage account pane.
- Click Enabled to enable static website hosting for the storage account.
- For Index document name, enter index.html.
- Click Save.

## Upload the static site files.
- Log in to Azure Cloud Shell at https://shell.azure.com.
- Select Bash, then advanced settings. Select use existing for all three fields, and enter cloudshell for the container.
- Get the key for the storage account. Note that you can find the resource group name in the Azure portal. 
The storage account name is the name of the storage account you created earlier.

```
export AZURE_STORAGE_ACCOUNT="&ltstorage account name>"
export RESOURCE_GROUP="&ltresource group name>"
az storage account keys list
--account-name $AZURE_STORAGE_ACCOUNT
--resource-group $RESOURCE_GROUP
--output table
```

- Set an environment variable containing the storage account key.
```
export AZURE_STORAGE_KEY="&ltkey>"
```
- Clone the lab resources repository from GitHub and switch to the static site directory.
```
git clone https://github.com/linuxacademy/content-azurestoragedd-lab-resources.git
cd content-azurestoragedd-lab-resources/satt-static-site/
```
- Upload the static site files as blobs within the $web container.
```
az storage blob upload-batch -d "$web" -s .
```
- In Azure portal, navigate back to the static site storage account and select Static Website again. 
This page contains a URL under Primary Endpoint. Copy this URL and access it in a new tab.
