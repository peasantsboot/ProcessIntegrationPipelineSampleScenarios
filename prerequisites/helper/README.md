# Setup little helper flows

Once you have downloaded the package **PIP Samples - Little Helpers**, navigate to **Design --> Integrations and APIs** and import the same into your Cloud Integration workspace. The package contains integration flows to help you setting up and testing the scenarios.

<br>![](/images/04_01_ImportLittleHelpers.png)

When opening the package, you will find the following integration flows:

- **PIP_EncodeAndUpload_XSLT**: Helps you to create or update an XSLT mapping to the Partner Directory
- **PIP_Mocked_Receiver**: Acts as mocked receiver system
- **PIP_Mocked_XI_Sender**: Acts as mocked sender system for XI inbound scenarios
- **PIP_ReadAndDecode_XSLT**: Reads and decodes XSLT mappings from the Partner Directory
- **PIP_Custom_ErrorHandling**: Optional custom error handling flow
- **PIP_FetchTenantDetails**: Reads tenant details such as tenant name which is needed for the landscape stage support (supported from package **version 1.0.9** on)

As a prerequisite for deploying the **PIP_Mocked_XI_Sender** flow, you should have created the credential alias pointing to your own tenant runtime. Configure the Credential Name. The default value is **OWN**.

Then deploy all mandatory integration flows. If you like to test the custom error handling, deploy this integration flow as well.

<br>![](/images/04_02_DeployLittleHelpers.png)

Go back to [Main page](../../README.md)
