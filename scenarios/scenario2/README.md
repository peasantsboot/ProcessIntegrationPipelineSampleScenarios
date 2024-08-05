# Scenario 2

With scenario 2, you can test the following features:
- Support for multi-mappings: Messages are sent to multiple receivers, and the messages are split to either the same message type (item) or multiple message types (header and item).
- Messages are sent to the pipeline via the XI inbound processing. In this case, we do not need a scenario-specific inbound flow, instead the generic XI inbound flow is used.
- Support for sender wildcards: Multiple senders are mapped to the same configuration.

We assume that you have gone through the prerequisites and the scenario setup.

## Test the scenario
To test the scenario, navigate to the folder **Scenario 2 - IF Split with Multi Mapping --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

You can run any of the POST requests below the **Trigger sample messages** folder.
In the message monitor of your Cloud Integration tenant, you can monitor the messages which were exchanged:
- The first request should run successfully from sender **Sender_21** to **Receiver_21** whereas the message is split into three messages of interface **PurchaseOrderItem.Create** each containing an item.
- The second request should run successfully from sender **Sender_22** to **Receiver_22** whereas the message is split into four messages, three messages of interface **PurchaseOrderItem.Create** and one of interface **PurchaseOrderHeader.Create**.
- The third request should run successfully from sender **Sender_23** to **Receiver_22** whereas the message is not split.

Go back to [Main page](../../README.md)
