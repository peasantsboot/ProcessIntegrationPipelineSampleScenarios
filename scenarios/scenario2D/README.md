# Scenario 2D

Scenario 2D is similar like scenario 2 except that we run the scenario on the integrated messaging runtime which is supported as of integration package version 1.0.9.
The integrated messaging runtime combines inbound conversion as well as receiver and interface determination in one single pipeline step leading to an improvement in terms of runtime performance.
- The scenario-specific integration flows of scenario 2 can be reused.
- The scenario supports different tenant stages like DEV, QA, PRD.

<br>![](/images/Scenario_2D.png)

**Note**: Scenario 2D reuses the same integration package like scenario 2. So, ensure that you have deployed the scenario 2 integration flows
whereas for the Partner Directory, dedicated objects for scenario 2D have to be setup.

**Note**: We assume that you run the scenario on your quality assurance landscape with stage key **QA**. During runtime the sender names are mapped to their alias and vice versa.
The alias name is actually used across all tenant stages to identify the integration scenario stored in the Partner Directory.
Ensure, that the landscape has been setup in the Partner Directory mapping the stages like **DEV**, **QA**, and **PRD** to the tenant names.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 2D - Integrated Messaging Runtime --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

**Note**: We have prepared different messages using the sender names of the landscape stage **QA**. Depending on your landscape settings, you may have to change the sender name in the header of the message requests.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request with supplier **ABCD** and country **DE** should run successfully from sender **BS_DD1_Q** to receiver **BS_ERP21_Q**:
  - You should see 7 new logs.
  - You should see a log for the integrated messaging runtime pipeline step.
  - The message is split into two messages of interface **PurchaseOrderItem.Create** each containing an item.

<br>![](/images/18_01_Scenario2D_MPL.png)

- The second request with supplier **EFGH** and country **DE** should run successfully from sender **BS_DD2_Q** to **BS_ERP22_Q**:
  - You should see 8 new logs.
  - You should see a log for the integrated messaging runtime pipeline step.
  - The message is split into three messages, two messages of interface **PurchaseOrderItem.Create** and one of interface **PurchaseOrderHeader.Create**.
- The third request with supplier **XXXX** and country **US** should run successfully from sender **BS_DD2_Q** to the default receiver **BS_ERP21_Q**:
  - You should see 6 new logs.
  - You should see a log for the integrated messaging runtime pipeline step.
  - The custom status of the integrated messaging runtime pipeline should be **ReceiverNotFoundDefault**.

Go back to [Main page](../../README.md)
