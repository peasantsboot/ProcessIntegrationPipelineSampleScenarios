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

## Initial setup of the Partner Directory entries

For each scenario that you like to setup and test, open the respective folder **Setup Partner Directory entries**, and then **Run** all POST APIs in the given order.
This will create the following entries:
- Alternative partners which map sender component and sender interface to the partner ID.
- String parameters to determine the runtime behavior and flow end points.
- XSLTs to determine receivers and interfaces, respectively.

For the alternative partner and string parameters, we directly call the Partner Directory API.

For the XSLTs, we pass the request to the helper integration flow **PIP_EncodeAndUpload_XSLT** which encodes the XSLT before uploading it to the Partner Directory.
This way, you are able to see the xpath conditions of the XSLT mappings in the body of the requests.

## Checking the Partner Directory entries

If you like to double check if the Partner Directory entries have been successfully created, you can run through the GET requests below the folder **Check Partner Directory entries**.

**Note**: If you get an unauthorized, first run the **Fetch PD Access Token** GET request to fetch the Bearer token.

For the alternative partner and string parameters, we directly call the Partner Directory API.

For the XSLTs, we pass the request to the helper integration flow **PIP_ReadAndDecode_XSLT** which decodes the XSLT after having fetched it from the Partner Directory.
This way, you are able to see the xpath conditions of the XSLT mappings in the response of the request.

## Optionally: Updating the Partner Directory entries

If you like to change existing Partner Directory entries, you can run the PUT requests below the folder **Update Partner Directory entries**.

**Note**: If you get an unauthorized, first run the **Fetch PD Access Token** GET request to fetch the Bearer token.

## Clean up Partner Directory entries

If you are done with your tests, you may delete the Partner Directory entries by running the DELETE requests below folder **Clean up Partner Directory**.

You can delete all entries of a scenario by opening the folder **Clean up Partner Directory**, and then selecting **Run**.

**Note**: If you have changed the scenario or the pid Postman variables, the deletion of the alternative partner may not work because the hexadecimal IDs may not fit any more.
In this case, read the exact URL via the GET requests and update the DELETE request URL accordingly.


Go back to [Main page](../../README.md)
