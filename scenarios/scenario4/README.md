# Scenario 4

Scenario 4 is of pattern Recipient List, however in the current case we re-use a message mapping from SAP Process Orchestration to determine the list of receivers instead of running an XSLT.
For the interface determination however, the XSLTs are still needed.

In this case, we do not need to upload an XSLT to determine the receivers. Instead, we provide the information about the end point of the integration flow running the mapping as well as the receiver
not determined situations as string parameters uploaded to the Partner Directory.

We assume that you have gone through the prerequisites and the scenario setup.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 4 -  Reuse Extended Receiver Determination --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

You can run any of the POST requests below the **Trigger sample messages** folder:
- The first request should be routed to receiver **Receiver_41**.
- The second request should be routed to receiver **Receiver_43**.
- The third request should be routed to the receivers **Receiver_42** and **Receiver_43**.
- For the last request no xpath condition could be met and hence the message should be routed to the default receiver **Receiver_41**. In this case, the custom status of the **Pipeline Generic Step04 - Receiver Determination** flow should be **ReceiverNotFoundDefault**.

In any cases, you should see a message processing log for the integration flow **PIPSamplesScenario4_Step04_XRD** were the message mapping to determine the receivers is carried out.

<br>![](/images/10_01_Scenario4_MPL.png)

Go back to [Main page](../../README.md)
