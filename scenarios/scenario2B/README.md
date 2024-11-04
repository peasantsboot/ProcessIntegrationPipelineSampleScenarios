# Scenario 2B

Scenario 2B is similar like scenario 2 except that we only have one single receiver and so the receiver determination pipeline step is bypassed.
- The scenario-specific integration flows of scenario 2 can be reused.
- However, we stick to one receiver only, so the receiver can be maintained as string parameter in the Partner Directory which allows to bypass the receiver determination pipeline step.
- For the receiver, interface determination XSLT is still defined.

<br>![](/images/Scenario_2B.png)

**Note**: Scenario 2B reuses the same integration package like scenario 2. So, ensure that you have deployed the scenario 2 integration flows
whereas for the Partner Directory dedicated objects for scenario 2B have to be setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 2B - Bypass Receiver Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request with country **DE** should run successfully from sender **Sender_2B** to the receiver **Receiver_21**:
  - You should see 8 new logs.
  - You should not see any log for pipeline step 4, this step has been bypassed, pipeline step 2 directly writes into the interface determination queue.
  - The message is split into three messages of interface **PurchaseOrderItem.Create** each containing an item.
- The second request with country **US** should run successfully from sender **Sender_2B** to **Receiver_21**:
  - You should see 6 new logs.
  - You should not see any log for pipeline step 4.
  - Here, the message is not split, the receiver interface should be **PurchaseOrder.Create**.

Go back to [Main page](../../README.md)
