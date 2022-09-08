# LevelUpAzureDevOpsPipelines

Demo pipelines from the talk "Level up your AzureDevOps Pipelines"

## Usage

Download all files in folder you want to try.
Make sure you have an agent pool set up (if you want to try the parallel pipelines you need more 1 one agent).
If present replace the following values:

- Replace \<YOUR AGENT POOL> for the name of your agent pool.

### Extra actions for the Approval pipeline

Set up a Test and Prod environment in AzureDevOps and set a approval check on the Prod environment.
extra replacements:

- Replace \<EMAIL> with the email adres you want to send notification to.

### Extra actions for the Parallel pipeline

Create a resourcegroup in azure and create a storage account in there.
extra replacements:

- Replace \<YOUR STORAGE ACCOUNT NAME> with the name of the storage account created
- Replace \<YOUR RESOURCEGROUP NAME> with the name of the resourcegroup the storage account is located in.
- Replace \<YOUR SERIVICE CONNECTION> with the name of the service connection to the azure subscription the resourcegroup is located in.

### Extra actions for the Rollback pipeline

Create a resourcegroup in azure and create a keyvault.
Create the following secrets in the keyvault:

- LastKnownGoodConfiguration : leave this empty
- Password : fill this with the password you want to set for the azure VM

Create a library in AzureDevOps called "Deployment Variables" link this library to the keyvault (make sure the permissions are correct).
To trigger the rollback in the pipeline change for example the sku size of the VM to something nonexistent.
extra replacements:

- Replace \<YOUR KEYVAULT NAME> with the name of the keyvault you created.
- Replace \<YOUR SERIVICE CONNECTION> with the name of the service connection to the azure subscription the resourcegroup is located in.
- Replace \<YOUR SUBSCRIPTIONID> with the ID of your subscription.
- Replace \<YOUR PIPELINEID> with the id of your pipeline.
