# Create Partner Directory entries

For each scenario, you need to setup the respective Partner Directory entries which are read during runtime by the generic integration flows of the pipeline concept.
With the Partner Directory, we can dynamically configure the behavior of the scenarios such as defining max number of retries in case of message processing errors.
Furthermore, we fetch XSLT mappings from the Partner Directory to determine the receivers the message should be passed to and to carry out interface splits if any.

The Partner Directory entries are created via the [Partner Directory API](https://help.sap.com/docs/integration-suite/sap-integration-suite/partner-directory)
using the provided Postman collection **Pipeline Concept - Sample Scenarios**.

For each scenario, the Postman collection contains the following sub folders:
- Setup Partner Directory entries
- Check Partner Directory entries
- Update Partner Directory entries
- Clean up Partner Directory
- Trigger sample messages

If you switch to the **Pre-request Script** tab of each scenario folder, you can see the variables that define the Partner Directory entries.
You may change the **scenario** name and the partner ID **pid** if you prefer different names, however better keep the rest of the values unchanged to avoid breaking the scenario.

<br>![](/images/06_01_PreRequestPD.png)

## Initial setup of the Partner Directory entries

For each scenario that you like to setup and test, open the respective folder **Setup Partner Directory entries**, and then select **Run**.

<br>![](/images/06_02_SetupPD.png)

In the **Runner** tab, run the GET request to fetch the token and all POST requests in the given order.

<br>![](/images/06_03_Runner.png)

This will create the following entries:
- Alternative partners which map sender component and sender interface to the partner ID.
- String parameters to determine the runtime behavior and flow end points.
- XSLTs to determine receivers and interfaces, respectively.

For the alternative partner and string parameters, we directly call the Partner Directory API.

For the XSLTs, we pass the request to the helper integration flow **PIP_EncodeAndUpload_XSLT** which encodes the XSLT before uploading it to the Partner Directory.
This way, you are able to see the xpath conditions of the XSLT mappings in the body of the requests.

## Checking the Partner Directory entries via API

If you like to double check if the Partner Directory entries have been successfully created, you can run through the GET requests below the folder **Check Partner Directory entries**.

**Note**: If you get an unauthorized, first run the **Fetch PD Access Token** GET request to fetch the Bearer token.

For the alternative partner and string parameters, we directly call the Partner Directory API.

<br>![](/images/06_05_ReadString.png)

For the XSLTs, we pass the request to the helper integration flow **PIP_ReadAndDecode_XSLT** which decodes the XSLT after having fetched it from the Partner Directory.
This way, you are able to see the xpath conditions of the XSLT mappings in the response of the request.

<br>![](/images/06_06_ReadXSLT.png)

## Checking the Partner Directory entries via UI

Recently, we have shipped a Partner Directory user interface in SAP Integration Suite that allows you to maintain the Partner Directory entries. After you have run through the APIs to setup the Partner Directory entries, you can check in the UI if the entries have been successfully created.

In the SAP Integration Suite launch page, navigate to **Monitor --> Integrations and APIs**, and select the tile **Partner Directory** below the **Manage Stores** section.

<br>![](/images/08_01_Scenario2_PDTile.png)

If you have run through the setup for all scenarios, you should see a list of partner IDs corresponding to the scenario names. Select any partner ID, in our case we select **PIP_Samples_Scenario_2**. On the tab **String Parameters**, you should see an entry defining the maximum number of retries.

<br>![](/images/08_03_Scenario2_PDStringParameter.png)

Switch to tab **Binary Parameters**. Here, the XSLT entries for the receiver and the interface determinations are displayed.

<br>![](/images/08_04_Scenario2_PDBinary.png)

Switch to tab **Alternative Partners**. You can see that three senders are mapped to the scenario.

<br>![](/images/08_02_Scenario2_PDAlternativePartner.png)

## Optionally: Updating the Partner Directory entries

If you like to change existing Partner Directory entries, you can run the PUT requests below the folder **Update Partner Directory entries**.

**Note**: If you get an unauthorized, first run the **Fetch PD Access Token** GET request to fetch the Bearer token.

## Clean up Partner Directory entries

If you are done with your tests, you may delete the Partner Directory entries by running the DELETE requests below folder **Clean up Partner Directory**.

You can delete all entries of a scenario by opening the folder **Clean up Partner Directory**, and then selecting **Run**.

**Note**: If you have changed the scenario or the pid Postman variables, the deletion of the alternative partner may not work because the hexadecimal IDs may not fit any more.
In this case, read the exact URL via the GET requests and update the DELETE request URL accordingly.


Go back to [Main page](../../README.md)
