# Setup Postman client

You should have downloaded the following Postman collection artifacts:
- Postman collection: **Pipeline Concept.postman_collection.json**
- Environment template: **your tenant.postman_environment.json**

Import the Postman collection as well as the Postman environment template to your Postman client.

## Maintain the Postman environment

Get your service keys from the BTP cockpit and maintain the Postman environment accordingly.

From the service key of service **Process Integration runtime** and plan **integration-flow**, maintain the following environment parameters:
- host = url
- username = clientid
- password = clientsecret

From the service key of service **Process Integration runtime** and plan **api**, maintain the following environment parameters:
- apihost = url
- apitokenhost = tokenurl (without path)
- apiusername = clientid
- apipassword = clientsecret

Go back to [Main page](../../README.md)
