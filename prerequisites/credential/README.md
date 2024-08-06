# Maintain credential alias

As a prerequisite for deploying the mocked XI sender flow as well as the mocked IDoc sender flow, you need to create a credential alias pointing to your own tenant runtime.

Get your service key of service **Process Integration runtime** and plan **integration-flow** from the BTP cockpit and maintain the credential alias accordingly.

<br>![](/images/01_01_ServiceKeyIntegrationFlow.png)

In your SAP Integration Suite launch page, navigate to **Monitor --> Integrations and APIs**, and select the **Security Material** tile.

<br>![](/images/03_01_MonitorSecurityMaterial.png)

In the **Manage Security Material** page, create a new user credential.

<br>![](/images/03_02_CreateCredential.png)

Enter the parameters as follows, then **deploy** the credential:
- enter a **Name**, we used **OWN**.
- as **User**, enter the **clientid** of the service key.
- as **Password**, enter the **clientsecret** of the service key.

<br>![](/images/03_03_DeployCredential.png)

Go back to [Main page](../../README.md)
