# Scenario 8

Scenario 8 is a synchronous Point-to-Point scenario with XI inbound.
- The synchronous request is routed to an external service to convert a number to its written form.
- The scenario leverages an enhancement of the generic XI inbound flow providing a single entry point for synchronous and asynchronous XI inbound scenarios. This feature is supported as of integration package **version 1.0.9** only. 
- The scenario supports different tenant stages like DEV, QA, PRD.

<br>![](/images/Scenario_8.png)

**Note**: We assume that you run the scenario on your quality assurance landscape with stage key **QA**. During runtime, the sender names are mapped to their alias and vice versa.
The alias name is actually used across all tenant stages to identify the integration scenario stored in the Partner Directory.
Ensure, that the landscape has been setup in the Partner Directory mapping the stages like **DEV**, **QA**, and **PRD** to the tenant names.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 8 - Synchronous P2P with XI Inbound --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

Run the GET request below the **Trigger sample messages** folder:
- You should see a proper response in the test client with the number provided in the payload in written form.
- In the monitoring, you should see 2 new logs.
- The request should run successfully from sender **BS_ABC_Q** to receiver **BS_ERP8_Q**

<br>![](/images/20_01_Scenario8_MPL.png)

Go back to [Main page](../../README.md)
