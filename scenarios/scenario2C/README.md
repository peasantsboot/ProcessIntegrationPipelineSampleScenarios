# Scenario 2C

Scenario 2C is similar like scenario 2B except that for one receiver the interface determination pipeline step is bypassed.
- The scenario-specific integration flows of scenario 2 can be reused.
- However for receiver 1, only one interface index is defined with no interface condition, so the interface can be maintained in the receiver determination XSLT which allows to bypass the interface determination pipeline step.
- For receiver 2, an interface determination XSLT is still defined.

**Note**: Scenario 2A reuses the same integration package like scenario 2. So, ensure that you have deployed the scenario 2 integration flows
whereas for the Partner Directory dedicated objects for scenario 2A have to be setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 2A - Bypass Interface Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request with supplier **ABCD** should run successfully from sender **Sender_2A** to **Receiver_21**:
  - You should see 8 new logs.
  - You should not see any log for pipeline step 5, this step has been bypassed, step 4 directly writes into the outbound processing queue.
  - The message is split into three messages of interface **PurchaseOrderItem.Create** each containing an item.
- The second request with supplier **XXXX** should run successfully from sender **Sender_2A** to the default receiver **Receiver_21**:
  - You should see 8 new logs.
  - You should not see any log for pipeline step 5, this step has been bypassed, pipeline step 4 directly writes into the outbound processing queue.
  - The custom status of pipeline step 4 should be **ReceiverNotFoundDefault**.
  - The message is split into three messages of interface **PurchaseOrderItem.Create** each containing an item.
- The third request with supplier **EFGH** and country **DE** should run successfully from sender **Sender_2A** to **Receiver_22**:
  - You should see 10 new logs.
  - This time, pipeline step 5 hasn't been bypassed.
  - The message is split into four messages, three messages of interface **PurchaseOrderItem.Create** and one of interface **PurchaseOrderHeader.Create**.
- The fourth request with supplier **EFGH** and country **US** should run successfully from sender **Sender_2A** to **Receiver_22**:
  - You should see 7 new logs.
  - This time, pipeline step 5 hasn't been bypassed.
  - Here, the message is not split.

Go back to [Main page](../../README.md)
