# Scenario 2C

Scenario 2C is similar like scenario 2B except that for determining the interfaces we use a custom extension.
- The scenario-specific integration flows of scenario 2 can be reused.
- The messages are sent to one single receiver only, so the receiver can be maintained as string parameter in the Partner Directory which allows to bypass the receiver determination pipeline step.
- To determine the receiver interfaces, a custom extension is used instead of running an XSLT, i.e., we call the scenario-specific integration flow **PIPSamplesScenario2_Step05_CustomInterfaceDetermination** to determine the receiver interfaces.


<br>![](/images/Scenario_2C.png)

**Note**: Scenario 2C reuses the same integration package like scenario 2. In addition to scenario 2, we have added the integration flow **PIPSamplesScenario2_Step05_CustomInterfaceDetermination** to the package. So, ensure that you have deployed the scenario 2 integration flows
whereas for the Partner Directory dedicated objects for scenario 2C have to be setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 2C - Custom Extension for Interface Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request with country **DE** should run successfully from sender **Sender_2C** to the receiver **Receiver_21**:
  - You should see 9 new logs.
  - You should not see any log for pipeline step 4, this step has been bypassed, pipeline step 2 directly writes into the interface determination queue.
  - You should see a log for the integration flow **PIPSamplesScenario2_Step05_CustomInterfaceDetermination** where the interface determination is carried out.
  - The message is split into three messages of interface **PurchaseOrderItem.Create** each containing an item.
- The second request with country **US** should run successfully from sender **Sender_2C** to **Receiver_21**:
  - You should see 7 new logs.
  - You should not see any log for pipeline step 4.
  - You should see a log for the integration flow **PIPSamplesScenario2_Step05_CustomInterfaceDetermination**.
  - Here, the message is not split, the receiver interface should be **PurchaseOrder.Create**.

<br>![](/images/16_01_Scenario2C_MPL.png)

Go back to [Main page](../../README.md)
