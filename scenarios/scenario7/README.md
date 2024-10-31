# Scenario 7

Scenario 7 covers a Recipient List pattern with non-XML payload
- It combines the Recipient List pattern and the interface split.
- The payload of the messages exchanged are either in JSON or CSV format and remain so during message processing.
- Both the receiver determination and the interface determination are based on dynamic configuration headers passed to the generic integration flows.

**Note**: When running an XSLT mapping to determine the list of receivers or interfaces for non-XML messages, you usually run into an error even if the conditions are based on headers only because the XSLT expects an XML. To overcome the error, a dummy XML is created right before running the XSLT.

We assume that you have gone through the prerequisites and the scenario setup. So, all should be set to be able to test the scenario.

## Test the scenario
To test the scenario, open your Postman client, and navigate to the folder **Scenario 7 - RL with non-XML payload --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

You can run any of the POST requests below the **Trigger sample messages** folder. The first two requests will exchange JSON messages from end to end, the last will send a CSV file to Cloud Integration which is then converted to XML in the outbound processing flow.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged. In the Integration Suite launch page, navigate to **Monitor --> Integrations and APIs** and select the tile below **Monitor Message Processing**.

If you run through the provided requests, they should result into the following:
- The first request should run successfully and according to the routing condition one message should be sent to the mocked receiver flow **PIP_Mocked_Receiver** for receiver **Receiver_71** and receiver interface **PersonDEJson.Create**.
- The second request should run successfully and according to the routing condition one message should be sent to the mocked receiver flow **PIP_Mocked_Receiver** for receiver **Receiver_72** and receiver interface **PersonUKJson.Create**.
- - The third request should run successfully and according to the routing condition one message should be sent to the mocked receiver flow **PIP_Mocked_Receiver** for receiver **Receiver_72** and receiver interface **PersonUKXml.Create**.

Go back to [Main page](../../README.md)
