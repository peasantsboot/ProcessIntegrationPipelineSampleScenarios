# Scenario 5

Scenario 5 is a pure Point-to-Point scenario, i.e., the messages are sent to one single receiver and one single interface. So, neither receiver determination nor interface determination are needed.

Instead of maintaining the receiver and interface determination as XSLTs, we now maintain the name of the receiver and the end point of the outbound processing flow as string parameter in the Partner Directory.

Furthermore, sender wildcard is supported. i.e., two alternative partners are mapped to the same partner ID.

We assume that you have gone through the prerequisites and the scenario setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 5 - Point-to-Point --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request should run successfully from sender **Sender_51** to **Receiver_51**.
- The second request should run successfully from sender **Sender_52** to **Receiver_51**.

In any case, because receiver determination as well as interface determination were bypassed you should not see any log for **Pipeline Generic Step04 - Receiver Determination** nor for **Pipeline Generic Step05 - Interface Determination**.

Go back to [Main page](../../README.md)
