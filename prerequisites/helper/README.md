## Setup little helper flows

The following package is provided which contain integration flows to help you setting up and testing the scenarios:

- **PIP Samples - Little Helpers**

Import the **PIP Samples - Little Helpers** package to your workspace.

When opening the package, you will find the following integration flows:

- **PIP_EncodeAndUpload_XSLT**: Helps you to create or update an XSLT mapping to the Partner Directory
- **PIP_Mocked_Receiver**: Acts as mocked receiver system
- **PIP_Mocked_XI_Sender**: Acts as mocked sender system for XI inbound scenarios
- **PIP_ReadAndDecode_XSLT**: Reads and decodes XSLT mappings from the Partner Directory
- **PIP_Custom_ErrorHandling**: Optional custom error handling flow

As a prerequisite for deploying the **PIP_Mocked_XI_Sender** flow, you should have created the credential alias pointing to your own tenant runtime. Configure the Credential Name. The default value is **OWN**.

Then deploy all mandatory integration flows. If you like to test the custom error handling, deploy this integratin flow as well.

Go back to [Main page](../../README.md)
