# Setup Postman client

You should have downloaded the following Postman collection artifacts:
- Postman collection: **Pipeline Concept - Sample Scenarios.postman_collection.json**
- Environment template: **your tenant.postman_environment.json**

## Import Postman client

Import the Postman collection **Pipeline Concept - Sample Scenarios** to your Postman client.
You should see six subfolders for the six sample scenarios. Each scenario contains the following subfolders:
- for setting up the Partner Directory
- for reading the Partner Directory
- for updating the Partner Directory
- for cleaning up the Partner Directory
- for triggering sample messages

<br>![](/images/01_04_PostmanCollection.png)

## Maintain the Postman environment

Import the Postman environment template **your tenant.postman_environment.json** to your Postman client.

Get your service keys from the BTP cockpit and maintain the Postman environment accordingly.

<br>![](/images/01_03_PostmanEnvironment.png)

From the service key of service **Process Integration runtime** and plan **integration-flow**, maintain the following environment parameters:
- host = url
- username = clientid
- password = clientsecret

<br>![](/images/01_01_ServiceKeyIntegrationFlow.png)

From the service key of service **Process Integration runtime** and plan **api**, maintain the following environment parameters:
- apihost = url
- apitokenhost = tokenurl (without path)
- apiusername = clientid
- apipassword = clientsecret

<br>![](/images/01_02_ServiceKeyApi.png)

Go back to [Main page](../../README.md)
