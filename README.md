# Process Integration Pipeline Sample Scenarios
Learn about the Process Integration Pipeline concept for Cloud Integration and how to setup sample scenarios leveraging the pipeline concept.

## Overview

The Process Integration Pipeline concept for Cloud Integration allows you to set up your asynchronous integration scenarios in Cloud Integration similarly to how messages are processed in SAP Process Integration and SAP Process Orchestration, namely in pipelines.

For a detailed description of the Pipeline concept, check out the [Pipeline Concept chapter](https://help.sap.com/docs/MIGRATION_GUIDE_PO/90c8ad90cb684ee5979856093efe7462/6e527fb074834af2be2546c6e7e2fa5f.html) in the SAP Process Orchestration migration guide.

Also check out the [Intro blog post](https://community.sap.com/t5/technology-blogs-by-sap/introducing-the-new-pipeline-concept-in-cloud-integration/ba-p/13639651) on the SAP community.

In this repository, we explain how to setup a couple of sample scenarios using the Pipeline concept for Cloud Integration. For each sample scenario, an integration package is provided. Furthermore, a Postman collection incl. Postman environment is provided that allows you to setup the Partner Directory entries and to trigger sample messages. One more package **PIP Samples - Little Helpers** comes with integration flows for mocking sender and receivers and to encode and decode the XSLT mappings required to run the receiver determination and interface determination, respectively.

## Prerequisites

Before you start, run through the following steps to get prepared:

- [Copy and deploy the standard package](prerequisites/standard)
- Download the provided files from [here](./download)
- [Setup the little helper flows](prerequisites/helper)
- [Setup Postman client](prerequisites/postman)
- [Setup credential alias on your tenant](prerequisites/credential)

## Setup of Sample Scenarios

For each sample scenario run through the following steps:

- Import and deploy the provided integration packages
- Setup the Partner Directory entries
- Finally, test the scenarios

## Sample Scenarios

The following sample scenarios are covered:

- Scenario 1: Recipient List & Interface Split
- Scenario 2: Interface Split with Multi Mapping & XI inbound
- Scenario 3: Interface Split with Maintain Order at Runtime
- Scenario 4: Use Extended Receiver Determination mapping instead of XSLT
- Scenario 5: Point-to-Point (Bypass option)
- Scenario 6: Point-to-Point with IDoc inbound
