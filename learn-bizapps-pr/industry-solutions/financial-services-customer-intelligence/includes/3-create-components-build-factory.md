In this exercise, you'll build a data pipeline in Azure Data Factory. In it, you'll ingest sample data from Dataverse into an Azure Data Lake, which is a set of capabilities dedicated to big data analytics. To complete this exercise, you must have an Azure subscription with administrator privileges. To learn more about Azure Data Lakes, see [Introduction to Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction/?azure-portal=true).

## Task 1: Create a resource group in Azure

In this task, you'll create a Resource group to house your other Azure components. To learn more about Azure Resource groups, see [Manage Azure Resource Manager resource groups by using the Azure portal](/azure/azure-resource-manager/management/manage-resource-groups-portal/?azure-portal=true).

1. Using an In-private or Incognito window, go to [Azure portal](https://portal.azure.com/?azure-portal=true).

1. In the search box, search for and select **Resource groups**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Microsoft Azure search box with Resource groups selected.](../media/groups.png)](../media/groups.png#lightbox)

1. Select **Create** to create a new Resource group.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Resource groups showing the Create button.](../media/create-group.png)](../media/create-group.png#lightbox)

1. Name the new Resource group **fsiResourceGroup**, choose the appropriate Region, select **Review + Create**, and then select **Create**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create a resource group Basics tab filled in and the Review + create button showing.](../media/review-create.png)](../media/review-create.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create a resource group Review + create tab with Validation passed message and Create button showing.](../media/validated.png)](../media/validated.png#lightbox)

1. Once the Resource group is created, go to **Access control (IAM)** and select **Add role assignment**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of f s i resource group on the Access control (I A M) page on the Check access tab showing the Add role assignment button.](../media/role.png)](../media/role.png#lightbox)

1. Select **Owner** and select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment with Owner selected and the Next button showing.](../media/owner.png)](../media/owner.png#lightbox)

1. Select **Select Members**, search for and select your user and then select **Select**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the Members tab with Select members showing.](../media/members.png)](../media/members.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Selected members showing Allen Contoso and the Select button.](../media/selected.png)](../media/selected.png#lightbox)

1. Select **Review + assign** to assign the role.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the members tab with the Review + Assign button showing.](../media/review-assign.png)](../media/review-assign.png#lightbox)

**Congratulations!** You've created a Resource group in Azure.

## Task 2: Create an Azure storage account

In this task, you'll create a storage account within the resource group that you created in the previous task. An Azure storage account contains all your Azure storage data objects and provides a unique namespace for your Azure storage data. To learn more about Azure storage accounts, see [Azure Storage documentation](/azure/storage/blobs/data-lake-storage-introduction/?azure-portal=true).

1. Navigate to the **Resource group** that you created in the previous task.

1. Select **Create**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the resource group showing the Create button.](../media/create-storage.png)](../media/create-storage.png#lightbox)

1. Scroll down the page to **Storage account** and select **Create**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create a resource scrolled down to show Storage account.](../media/create-resource.png)](../media/create-resource.png#lightbox)

1. Select the **Resource group** that you created in the previous task.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Project details with Subscription field empty and Resource group filled in.](../media/details.png)](../media/details.png#lightbox)

1. Scroll down to **Instance details** and enter the following information, select **Review + create**, and then select **Create**:

    - **Storage account name**: fsistorageacct

    - **Region**: The same region you selected for your Resource group

    - **Performance**: Default

    - **Redundancy**: Default

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Instance details filled in and the Review + create button.](../media/instance-details.png)](../media/instance-details.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create a storage account showing Validation passed and the Create button.](../media/storage-validation.png)](../media/storage-validation.png#lightbox)

1. Once the Storage account is created, go to **Access Control (IAM),** and select **Add role assignments**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Access Control (I A M) showing the Add role assignment button.](../media/access-control.png)](../media/access-control.png#lightbox)

1. **Search** for and select **Storage Blob Data Contributor**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment with search results for storage blob data contributor.](../media/blob.png)](../media/blob.png#lightbox)

1. Select **Members** and then select **Select Members**. Find your user and select **Select**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the Members tab with the Select members button showing.](../media/members-tab.png)](../media/members-tab.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Selected members with one member.](../media/selected.png)](../media/selected.png#lightbox)

1. Select **Review + assign** to assign the role.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the Members tab with the Review + assign button.](../media/role-assign.png)](../media/role-assign.png#lightbox)

1. Go back to **Access Control (IAM)** and select **Add role assignment** again.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Access Control showing Add role assignment button.](../media/access-control.png)](../media/access-control.png#lightbox)

1. Select **Owner** and then select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the Role tab with Owner selected.](../media/owner-role.png)](../media/owner-role.png#lightbox)

1. Select **+ Select Members**. Find your user and select **Select**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment on the Members tab again.](../media/select-members.png)](../media/select-members.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Selected members again.](../media/selected.png)](../media/selected.png#lightbox)

1. Select **Review + assign** to assign the role.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Members tab of Add role assignment with Review + assign button.](../media/assign.png)](../media/assign.png#lightbox)

1. Go back to **Access Control (IAM)** and select **Add role assignment** one more time.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Access Control again.](../media/access-control.png)](../media/access-control.png#lightbox)

1. **Search** for and select **Storage Blob Data Contributor**. Select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Storage blob data contributor search results again.](../media/blob.png)](../media/blob.png#lightbox)

1. Select **Members** and then select **+ Select Members**. Search for and **Select Dynamics 365 AI for Customer Insights**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment members tab yet again.](../media/members-tab.png)](../media/members-tab.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Selected members showing Dynamics 365 A.](../media/dynamics.png)](../media/dynamics.png#lightbox)

1. Select **Review + assign** to assign the role.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Add role assignment yet again showing the Review PLUS assign button.](../media/assign-role.png)](../media/assign-role.png#lightbox)

**Congratulations!** You've created a Storage account in your Azure Resource group.

## Task 3: Create a staging Azure container for Customer Insights

In this task, you'll create an Azure container from the storage account that you created in the previous task. This Azure container will be used as a staging area for data that will be ingested by Customer Insights. To learn more about Azure containers, see [Azure Container Instances documentation](/azure/container-instances/?azure-portal=true).

1. In the Storage account you created in the previous task, select **Containers**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Storage account with Containers appearing under Data Storage.](../media/containers.png)](../media/containers.png#lightbox)

1. Select **+ Container**, fill out the following information and select **Create**.

    - **Name**: fsicistagingcontainer

    - **Public access level**: Container

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New container dialog filled in.](../media/container.png)](../media/container.png#lightbox)

1. Open the newly created Container and select **Manage ACL**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Settings with Manage A C L selected.](../media/manage.png)

1. Under **Access permissions**, select **Add Principal**. Search for **Dynamics 365 AI for Customer Insights** and select **Select**. Provide Read, Write, and Execute permissions and select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Manage A C L on the Access permissions tab showing Dynamics 365 A I for Customer Insights with all three checkboxes selected.](../media/add-principal.png)](../media/add-principal.png#lightbox)

1. Follow the exact same steps for **Dynamics 365 AI for Customer Insights** under **Default permissions**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Manage A C L on the Default permissions tab showing Dynamics 365 A I for Customer Insights with all three checkboxes selected.](../media/default.png)](../media/default.png#lightbox)

1. Go to **Overview** and select **Add Directory**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Container Overview showing the Add Directory button.](../media/add-directory.png)](../media/add-directory.png#lightbox)

1. Type **Corpus** and select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add Directory dialog with Name set to Corpus.](../media/add.png)](../media/add.png#lightbox)

1. Open the new **Corpus** directory and select **Add Directory**. Type **resolved**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add Directory with Name set to resolved.](../media/resolved.png)](../media/resolved.png#lightbox)

1. Open the new **resolved** folder and select **Upload** to upload the .JSON files that have been provided as part of this lab. These .JSON files will be used to transform the data for Customer Insights.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Container Overview showing the list of JSON files.](../media/json.png)](../media/json.png#lightbox)

**Congratulations!** You've created a staging Azure Container for Customer Insights.

## Task 4: Create a new Azure Synapse link

In this task, you'll create a new Azure Synapse link to connect your Dataverse environment to your Azure Storage account.

1. Using an In-Private or Incognito window, navigate to [Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Select the correct environment from the upper right **Environment** drop down.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the upper right Environment drop down.](../media/environment.png)

1. Expand **Dataverse** and select **Azure Synapse Link**. Select **New link**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Azure Synapse Link for Dataverse showing the New link button.](../media/link.png)](../media/link.png#lightbox)

1. Select your Azure **Subscription**, **Resource Group**, and **Storage account**, and select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New link wizard on the Select Storage Account page with the fields filled in.](../media/new-link.png)](../media/new-link.png#lightbox)

1. Filtering by keyword, search for and add the following 18 tables. Select **Save**.

    - Bank

    - Branch

    - Contact

    - Customer financial holding

    - FH account

    - FH investment

    - FH line of credit

    - FH loan

    - FH saving

    - FI card

    - FI direct debit

    - FI overdraft

    - FI standing order

    - Financial holding

    - Financial holding instrument

    - Group

    - Group financial holding

    - Group member

    - Life event

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New link wizard on the Add Tables page showing Life event added.](../media/add-tables.png)](../media/add-tables.png#lightbox)

1. Once you finish adding the tables, you should begin to see the tables populate with data. This action will also create a new Azure Container in your storage account that we can use to run our Data Pipeline in Azure Data factory.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Tables tab showing all 18 of the added tables.](../media/tables.png)](../media/tables.png#lightbox)

**Congratulations!** You've linked Dataverse to Azure Data Lake using Azure Synapse.

## Task 5: Create an Azure data factory

In this task, you'll create an Azure data factory within your Azure Resource group. Azure Data Factory is Azure's cloud ETL service for scale-out serverless data integration and data transformation. To learn more about Azure Data Factory, see [Azure Data Factory documentation](/azure/data-factory/?azure-portal=true).

1. In Azure, search for and select **Data factories**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Microsoft Azure showing Data factories in the search box.](../media/data-factories.png)](../media/data-factories.png#lightbox)

1. Select **Create** to create a new data factory.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Data factories showing the Create button.](../media/create-data.png)

1. Fill out the following information:

    - **Subscription**: Your Azure subscription

    - **Resource group**: Your previously created Resource group

    - **Region**: Same region as your Resource group

    - **Name**: myfsidatafactory

    - **Version**: V2

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create Data Factory Basics tab filled in.](../media/create-data-factory.png)](../media/create-data-factory.png#lightbox)

1. Select the **Git configuration** tab and select **Configure Git later**. Select **Review + create**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create Data Factory Git configuration tab with Configure Git later selected.](../media/git.png)](../media/git.png#lightbox)

1. Finally, select **Create** to create the Azure Data factory.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Create Data Factory Review + create tab showing the Validation passed message.](../media/validate.png)](../media/validate.png#lightbox)

**Congratulations!** You've created an Azure data factory.

## Task 6: Run a data pipeline in Azure data factory

In this task, you'll run a Data Pipeline in your Azure Data Factory using an ARM (Azure Resource Manager) template. This data pipeline will ingest the sample data from the Storage Container linked to your Microsoft Cloud for Financial Services Dataverse environment. Then it will move it to the staging Container to be ingested by Dynamics 365 Customer Insights. For more information on Data Pipelines, see [Pipelines and activities in Azure Data Factory and Azure Synapse Analytics](/azure/data-factory/concepts-pipelines-activities/?azure-portal=true).

1. In your Azure Data Factory, go to **Overview** and then select **Open Azure Data Factory Studio**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Data Factory Overview page showing the Open Azure Data Factory Studio tile under Getting started.](../media/open-studio.png)](../media/open-studio.png#lightbox)

1. Select your Azure Data factory from the **Data Factory name** dropdown menu and select **Continue**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Select Data Factory filled in showing the Continue button.](../media/select-factory.png)](../media/select-factory.png#lightbox)

1. In the left navigation, select the **Manage** icon (toolbox), then select **ARM template**, and select the **Import ARM template** tile.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of A R M template showing the Import A R M template tile.](../media/template.png)](../media/template.png#lightbox)

1. Select **Build your own template in the editor**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Custom deployment on the Select a template tab showing the Build your own template in the editor option.](../media/custom.png)](../media/custom.png#lightbox)

1. Select **Load file** to upload the ARM Template file provided in the Lab Resources.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Edit template showing JSON code.](../media/edit.png)](../media/edit.png#lightbox)

1. Go back to your Storage Account. Go to **Access Keys** and select **Show keys**. Copy the **key1** key.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Storage account Access keys with Show keys selected.](../media/keys.png)](../media/keys.png#lightbox)

1. Edit the following parameters and select **Save**:

    - **factoryName: defaultValue:** Your Data factory name

    - **lnkFSICDM_accountKey: metadata:** The Storage Account Key you copied in the previous step

    - **lnkCICDM_accountKey: metadata:** The Storage Account Key you copied in the previous step

    - **lnkFSICDM_properties_typeProperties_url: metadata:** `https://STORAGEACCOUNTNAAME.dfs.core.windows.net`

    - **lnkCICDM_properties_typeProperties_url: metadata:** `https://STORAGEACCOUNTNAAME.dfs.core.windows.net`

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Edit template showing JSON code with parameters added.](../media/parameters.png)](../media/parameters.png#lightbox)

1. Select your **Resource group** from the dropdown menu. Fill in the remaining two parameters with the **Storage Account Key** that you copied in the previous step. Select **Review + create**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Custom deployment filled in.](../media/custom-deployment.png)](../media/custom-deployment.png#lightbox)

1. Select **Create** to create the Data Pipeline.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Custom deployment showing a validation passed message.](../media/custom-validated.png)](../media/custom-validated.png#lightbox)

1. Go back to your **Data factory** and **refresh** the page. Select **Linked services** and you should now see two connections.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Data Factory Linked services page showing two connections.](../media/linked.png)](../media/linked.png#lightbox)

1. Select the **Author** (pencil) icon. Expand and select the **Pipeline**. Input the following parameters:

    - **pipFSICDM**: The full name of your Storage Container linked to Azure Synapse. For example: `dataverse-AZURESYNAPSE-unqab48050868e14fef9572fa91f02ff`

    - **pipCICDM**: The name of your Customer Insights staging Storage Container. For example: `cistagingcontainer`

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Factory Resources with the Pipeline selected and parameters added.](../media/pipeline.png)](../media/pipeline.png#lightbox)

1. To publish your changes, select **Publishing** and then select **Publish**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Publish all dialog showing pending changes and the Publish button.](../media/publish.png)](../media/publish.png#lightbox)

1. To turn on data flow debug, check the **Data flow debug** field and select **OK**. This will provide you with a detailed error message should the pipeline fail to run. It will take a couple minutes for this process to complete.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Turn on data flow debug dialog.](../media/debug.png)](../media/debug.png#lightbox)

1. Once Data flow debug is turned on, select **Debug** and then select **OK** to trigger the pipeline.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the editor showing the Data flow debug toggled on.](../media/data-flow-debug.png)](../media/data-flow-debug.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Pipeline run dialog showing parameters and an O K button.](../media/pipeline-run.png)](../media/pipeline-run.png#lightbox)

1. If the run is successful, you'll receive a status of Succeeded for the Data flow.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Factory Resources on the Pipeline showing the output tab listing pipeline runs with status showing succeeded.](../media/succeeded.png)](../media/succeeded.png#lightbox)

1. Go back to your Customer Insights staging Storage Container to see data begin to populate in a newly created Data folder.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of data folder populating with folders.](../media/folder.png)](../media/folder.png#lightbox)

**Congratulations!** You've successfully built and run a Data Pipeline in Azure Data Factory.
