# Setup standard package

As a prerequsite to run the sample scenarios using the Process Integration Pipeline for Cloud Integration, you need to deploy the generic integration flows of the provided standard package **Process Integration Pipeline - Generic Integration Flows & Templates**.

Each of the generic integration flows represents a pipeline where the messages are carried out. We distinguish between the following pipelines:
- Inbound Processing
- Receiver Determination
- Interface Determination
- Outbound Processing

## Copy or update package

In your SAP Integration Suite launch page, navigate to **Discover --> Integrations**, and copy the latest version of the package **Process Integration Pipeline - Generic Integration Flows & Templates** from the SAP Business Accelerator Hub to your workspace.

<br>![](/images/02_01_StandardPackage.png)

**Note**: if the package already exists in your workspace, eventually update your package. The sample scenarios require at least **version 1.0.6** of the package.
From version 1.0.6 on we had to do an incompatible change of the partner ID for fetching the interface determination XSLT which was necessary due to the partner ID length restrictions of 60 characters.
Furthermore, we introduced the option of using alternative partner which maps sender component and sender interface to a scenario name. We recommend to apply the alternative partner and hence have used this feature for all of our sample scenarios.

## Deploy script collection

Switch to **Design --> Integrations and APIs** and select the beforehand copied package.

Within the package, switch to tab **Artifacts** and deploy the generic script collection **Pipeline Generic - Script Collection** which is used across the generic integration flows.

<br>![](/images/02_02_DeployScript.png)

## Configure and deploy integration flows

For mass deployment, select the following generic integration flows, then select entry **Configure** from the **Actions** menu.

- **Pipeline Generic Step01 - Inbound Processing for Idoc**
- **Pipeline Generic Step01 - Inbound Processing for XI**
- **Pipeline Generic Step02 - Inbound Processing**
- **Pipeline Generic Step04 - Receiver Determination**
- **Pipeline Generic Step05 - Interface Determination**
- **Pipeline Generic Step06 - Outbound Processing**

<br>![](/images/02_03_Configure.png)

In the upcoming dialog, select **Deploy All**. This will deploy all flows.

**Note**: Before deployment, you have the option to configure the integration flows like maintaining a different XI or IDoc inbound path, maintaining a different queue prefix, maintaining the JMS adapter settings, etc. However, keep in mind that if you change some settings here, you need to change the configuration of the provided sample scenarios accordingly. So, to be on the save side, keep the configuration as is.

<br>![](/images/02_04_DeployAll.png)

Go back to [Main page](../../README.md)
