# Scenario 1

Scenario 1 covers the most generic use case:
- It combines the Recipient List pattern and the interface split.
- Inbound conversion is needed to convert from JSON to XML.
- For receiver **Receiver_11**, a receiver specific outbound queue is used.

We assume that you have gone through the prerequisites and the scenario setup. So, all should be set to be able to test the scenario.

## Test the scenario
To test the scenario, open your Postman client, and navigate to the folder **Scenario 1 - RL with IF Split --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request should run successfully and according to the routing condition one message should be sent to the mocked receiver flow **PIP_Mocked_Receiver** for receiver **Receiver_12** and receiver interface **PurchaseOrder.Create**.
- The second request should run successfully and according to the routing condition five messages should be sent to the mocked receiver flow:
  - Two messages to **Receiver_11** both with receiver interface **PurchaseOrderItem.Create**.
  - One message to **Receiver_12** with receiver interface **PurchaseOrder.Create**.
  - Two messages to **Receiver_13** one with receiver interface **PurchaseOrderItem.Create** and one with **PurchaseOrder.Create**. 
- The other three requests will run into errors. The one where the test mode is set to true will not go into retry, it will be completed and the custom status is set to **ErrorInTestMode**.

Go back to [Main page](../../README.md)
