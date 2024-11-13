# Scenario 1A

Scenario 1A uses exactly the same routing and interface split conditions like scenario 1
except that the receiver determination xpath conditions and the interface xpath conditions are combined in one single XSLT.
This way, we can completly bypass the interface determination pipeline step leading to a better runtime behavior in terms of performance.
- The scenario-specific integration flows of scenario 1 can be reused.
- However, the receiver determination XSLT has been enhanced to include the interface determination xpaths.

<br>![](/images/Scenario_1A.png)

**Note**: Scenario 1A reuses the same integration package like scenario 1.
So, ensure that you have deployed the scenario 1 integration flows whereas for the Partner Directory dedicated objects for scenario 1A have to be setup.

## Test the scenario
To test the scenario, open your Postman client, and navigate to the folder **Scenario 1A - Combined RL & IF Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

You can run any of the POST requests below the **Trigger sample messages** folder.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

If you run through the provided requests, they should result into the following:
- The first request should run successfully and according to the routing condition one message should be sent to the mocked receiver flow **PIP_Mocked_Receiver** for receiver **Receiver_12** and receiver interface **PurchaseOrder.Create**.
- The second request should run successfully and according to the routing condition five messages should be sent to the mocked receiver flow:
  - Two messages to **Receiver_11** both with receiver interface **PurchaseOrderItem.Create**.
  - One message to **Receiver_12** with receiver interface **PurchaseOrderItem.Create**.
  - Two messages to **Receiver_13** one with receiver interface **PurchaseOrderItem.Create** and one with **PurchaseOrder.Create**. 
- The other three requests will run into errors. The one where the test mode is set to true will not go into retry, it will be completed and the custom status is set to **ErrorInTestMode**.

**Note**: Because we use exactly the same xpath conditions like in scenario 1, the results should be the same except that you should not get any logs for step #5.

Go back to [Main page](../../README.md)
