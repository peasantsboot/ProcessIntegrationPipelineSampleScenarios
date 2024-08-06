# Import and deploy sample scenarios

We have prepared 6 scenarios in total. For each scenario, a zip file is provided which you need to upload to your tenant workspace.

<br>![](/images/05_01_ImportScenarios.png)

The following scenarios are supported:
- **PIP Samples - Scenario 1**: Scenario with multiple receivers and multiple interfaces
- **PIP Samples - Scenario 2**: Scenario with interface split (1:n message mappings)
- **PIP Samples - Scenario 3**: Scenario with interface split and Maintain Order at Runtime option
- **PIP Samples - Scenario 4**: Scenario with multiple receivers and reuse of extended receiver 
- **PIP Samples - Scenario 5**: Point-to-Point Scenario
- **PIP Samples - Scenario 6**: Point-to-Point Scenario with IDoc inbound

Each scenario package contains the scenario-specific integration flows which handle the inbound processing, the inbound conversion if any as well as the outbound processing.

Depending on which scenario you like to run, deploy all the integration flows of the respective packages. If re-usable message mappings are used like for scenario 4, also deploy those mapping artifacts.

<br>![](/images/05_02_DeployScenarios.png)

For **PIP Samples - Scenario 6**, also configure and deploy the mocked IDoc sender integration flow.
As a prerequisite for deploying the flow, you should have created the credential alias pointing to your own tenant runtime.
Configure the Credential Name. The default value is **OWN**.

Go back to [Main page](../../README.md)
