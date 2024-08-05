## Setup standard package

Copy the latest version of the following package from the SAP Business Accelerator Hub to your workspace in your Cloud Integration tenant:

- **Process Integration Pipeline - Generic Integration Flows & Templates**

**Note**: if the package already exists in your workspace, eventually update your package. The sample scenarios require at least version 1.0.6 of the package.
From version 1.0.6 on we had to do an incompatible change of the partner ID for fetching the interface determination XSLT which was necessary due to the partner ID length restrictions of 60 characters.
Furthermore, we introduced the option of using alternative partner which maps sender component and sender interface to a scenario name. We recommend to apply the alternative partner and hence have used this feature for all of our sample scenarios.

Configure (optionally) and deploy the following generic artifacts of the standard package:

- **Pipeline Generic - Script Collection**
- **Pipeline Generic Step01 - Inbound Processing for Idoc**
- **Pipeline Generic Step01 - Inbound Processing for XI**
- **Pipeline Generic Step02 - Inbound Processing**
- **Pipeline Generic Step04 - Receiver Determination**
- **Pipeline Generic Step05 - Interface Determination**
- **Pipeline Generic Step06 - Outbound Processing**

Go back to [Main page](../../README.md)
