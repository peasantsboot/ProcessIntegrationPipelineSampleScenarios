# Scenario 10

Scenario 10 leverages a new feature which has been supported as of integration package version 1.0.10 on, namely sender service interface with multiple operations.
- The scenario receives order messages with either create or change operation.
- The scenario runs on the integrated messaging runtime.
- The scenario supports different tenant stages like DEV, QA, PRD.

<br>![](/images/Scenario_10.png)

**Note**: Scenario 10 comes with a new integration package **PIP Samples - Scenario 10**. So, ensure that you have deployed the scenario 10 integration flows
and have setup the corresponding objects on the Partner Directory.

**Note**: We assume that you run the scenario on your quality assurance landscape with stage key **QA**. During runtime the sender names are mapped to their alias and vice versa.
The alias name is actually used across all tenant stages to identify the integration scenario stored in the Partner Directory.
Ensure, that the landscape has been setup in the Partner Directory mapping the stages like **DEV**, **QA**, and **PRD** to the tenant names.

## Support for service operation

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 10 - Sender Operations --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

**Note**: We have prepared different messages using the sender names of the landscape stage **QA**. Depending on your landscape settings, you may have to change the sender name in the header of the message requests.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request of service interface **PurchaseOrder** and operation **Create** should run successfully from sender **BS_101_Q** to receiver **BS_ERP10_Q**:
  - You should see 5 new logs.
  - The outbound processing log should show **OrderCreate** as Application Message Type of the receiving system.
  - In the custom header, the operation **Create** should be displayed.

<br>![](/images/22_04_Scenario10_message_moni_create.png)

- The second request of service interface **PurchaseOrder** and operation **Change** should run successfully from sender **BS_101_Q** to receiver **BS_ERP10_Q**:
  - You should see 5 new logs.
  - The outbound processing log should show **OrderChange** as Application Message Type of the receiving system.
  - In the custom header, the operation **Change** should be displayed.

<br>![](/images/22_06_Scenario10_message_moni_change.png)

Go back to [Main page](../../README.md)
