# Import and deploy sample scenarios

We have prepared a couple of sample scenarios covering different use cases. Right now, we have 9 sample integration packages in total for which a zip file is provided and which you need to upload to your tenant workspace.

**Note**: Some of the integration packages are used by more than one scenario. Actually, scenario variants labeled with an additional letter share the same integration package but are differently configured in the Partner Directory.

<br>![](/images/05_01_ImportScenarios.png)

The following packages are supported:
- **PIP Samples - Scenario 1**: Scenario with multiple receivers and multiple interfaces
- **PIP Samples - Scenario 2**: Scenario with interface split (1:n message mappings)
- **PIP Samples - Scenario 3**: Scenario with interface split and Maintain Order at Runtime option
- **PIP Samples - Scenario 4**: Scenario with multiple receivers and reuse of extended receiver 
- **PIP Samples - Scenario 5**: Point-to-Point Scenario
- **PIP Samples - Scenario 6**: Point-to-Point Scenario with IDoc inbound
- **PIP Samples - Scenario 7**: Recipient List pattern with non-XML payload (supported from Pipeline **version 1.0.8** on)
- **PIP Samples - Scenario 8**: Synchronous Point-to-Point Scenario with XI inbound (supported from Pipeline **version 1.0.9** on)
- **PIP Samples - Scenario 9**: Synchronous Content-Based-Router Scenario (supported from Pipeline **version 1.0.9** on)

Each scenario package contains the scenario-specific integration flows which handle the inbound processing, the inbound conversion if any as well as the outbound processing.

Depending on which scenario you like to run, deploy all the integration flows of the respective packages. If re-usable message mappings are used like for scenario 4, also deploy those mapping artifacts.

<br>![](/images/05_02_DeployScenarios.png)

For **PIP Samples - Scenario 6**, also configure and deploy the mocked IDoc sender integration flow.
As a prerequisite for deploying the flow, you should have created the credential alias pointing to your own tenant runtime.
Configure the Credential Name. The default value is **OWN**.

Go back to [Main page](../../README.md)
