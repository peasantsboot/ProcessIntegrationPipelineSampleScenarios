# Setup landscape stage mapping

As of integration package **version 1.0.9**, the pipeline concept supports different landscape stages such as DEV, QA, PRD.
This allows you to run your scenarios on the different landscape stages without changing the configuration in the Partner Directory such as the XSLT for determining the receivers.
During runtime, the actual sender business system name is mapped to a sender alias which is used within the pipeline processing,
at the end the receiver alias is then mapped back to the actual receiver business name.
To automatically identify the stage, the tenant names are mapped to the corresponding stage IDs.
This mapping is stored in the Partner Directory using partner ID **SAP_Integration_Suite_Landscape**.

The Partner Directory entries are created via the [Partner Directory API](https://help.sap.com/docs/integration-suite/sap-integration-suite/partner-directory)
using the provided Postman collection **Pipeline Concept - Sample Scenarios** which you should have downloaded from the [here](../../download).

In the Postman collection you should see the folder **SAP Integration Suite Landscape** which contains the following subfolders:
- Setup Partner Directory entries
- Check Partner Directory entries
- Clean up Partner Directory

## Initial setup of the Partner Directory entry

Open the folder **Setup Partner Directory entries**, and then select **Run**.

<br>![](/images/06a_01_SetupPD.png)

In the **Runner** tab, run the GET requests to fetch the tenant name and the token and the POST request in the given order.

<br>![](/images/06a_02_Runner.png)

This will first fetch the tenant name and then match the name to the stage **QA** assuming that you run the scenarios on your quality assurance landscape.
If you like, you can change the stage but then keep in mind to also change it accordingly when triggering the test messages.

## Checking the Partner Directory entry via API

If you like to double check if the Partner Directory entry have been successfully created, you can run through the GET request **Read Landscape Mapping** below the folder **Check Partner Directory entries**.

**Note**: If you get an unauthorized, first run the **Fetch PD Access Token** GET request to fetch the Bearer token.

<br>![](/images/06a_03_ReadString.png)

## Checking the Partner Directory entry via UI

Recently, we have shipped a Partner Directory user interface in SAP Integration Suite that allows you to maintain the Partner Directory entries. After you have run through the APIs to setup the Partner Directory entries, you can check in the UI if the entries have been successfully created.

In the SAP Integration Suite launch page, navigate to **Monitor --> Integrations and APIs**, and select the tile **Partner Directory** below the **Manage Stores** section.

<br>![](/images/08_01_Scenario2_PDTile.png)

If you have run through the setup, you should see the partner ID **SAP Integration Suite Landscape**.
On the tab **String Parameters**, you should see the entry mapping the tenant name to the stage.

<br>![](/images/06a_04_PDStringParameter.png)

## Clean up Partner Directory entries

If you are done with your tests, you may delete the Partner Directory entries by running the DELETE requests below folder **Clean up Partner Directory**.

Go back to [Main page](../../README.md)
