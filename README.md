# Process Integration Pipeline Sample Scenarios
Learn about the Process Integration Pipeline concept for Cloud Integration and how to setup sample scenarios leveraging the pipeline concept.

## Overview

The Process Integration Pipeline concept for Cloud Integration allows you to set up your asynchronous integration scenarios in Cloud Integration similarly to how messages are processed in SAP Process Integration and SAP Process Orchestration, namely in pipelines.

For a detailed description of the Pipeline concept, check out the [Pipeline Concept chapter](https://help.sap.com/docs/MIGRATION_GUIDE_PO/90c8ad90cb684ee5979856093efe7462/6e527fb074834af2be2546c6e7e2fa5f.html) in the SAP Process Orchestration migration guide.

Also check out the [Intro blog post](https://community.sap.com/t5/technology-blogs-by-sap/introducing-the-new-pipeline-concept-in-cloud-integration/ba-p/13639651) on the SAP community.

In this repository, we explain how to setup a couple of sample scenarios using the Pipeline concept for Cloud Integration. For each sample scenario, an integration package is provided. Furthermore, a Postman collection incl. Postman environment is provided that allows you to setup the Partner Directory entries and to trigger sample messages. One more package **PIP Samples - Little Helpers** comes with integration flows for mocking sender and receivers and to encode and decode the XSLT mappings required to run the receiver determination and interface determination, respectively.

## Prerequisites

Before you start, run through the following steps to get prepared:

- Download the provided files from [here](./download)
- [Setup Postman client](prerequisites/postman)
- [Copy and deploy the standard package](prerequisites/standard)
- [Create credential alias on your tenant](prerequisites/credential)
- [Setup the little helper flows](prerequisites/helper)
- As of version 1.0.9: [Setup landscape stage mapping](prerequisites/stages)

## Setup of Sample Scenarios

For each sample scenario run through the following steps:

- [Import and deploy the provided integration packages](scenarioSetup/import)
- [Setup the Partner Directory entries](scenarioSetup/partnerDirectory)

**Note**: From Pipeline package **version 1.0.8** on, we have introduced scenario varaints labeled with an additional letter. Those scenario variants leverage new features that we have shipped with new versions. The scenario variants are differently configured in the Partner Directory, e.g., to bypass a pipeline step or using a custom extension, however they share the same integration packages.

## Sample Scenarios

The following sample scenarios are covered:

- [Scenario 1: Recipient List & Interface Split](scenarios/scenario1)
- [Scenario 2: Interface Split with Multi Mapping & XI inbound](scenarios/scenario2)
- [Scenario 3: Interface Split with Maintain Order at Runtime](scenarios/scenario3)
- [Scenario 4: Use Extended Receiver Determination mapping instead of XSLT](scenarios/scenario4)
- [Scenario 5: Point-to-Point (Bypass option)](scenarios/scenario5)
- [Scenario 6: Point-to-Point with IDoc inbound](scenarios/scenario6)

The following sample scenarios and variants are supported from version 1.0.8 on:

- [Scenario 1A: Combined Recipient List & Interface Determination](scenarios/scenario1A)
- [Scenario 2A: Bypass Interface Determination](scenarios/scenario2A)
- [Scenario 2B: Bypass Receiver Determination](scenarios/scenario2B)
- [Scenario 2C: Custom Extension for Interface Determination](scenarios/scenario2C)
- [Scenario 4A: Custom Extension for Receiver Determination](scenarios/scenario4A)
- [Scenario 7: Recipient List with non-XML payload](scenarios/scenario7)

The following sample scenarios and variants are supported from version 1.0.9 on:

- [Scenario 2D: Using Integrated Messaging Runtime](scenarios/scenario2D)
- [Scenario 8: Synchronous P2P with XI Inbound](scenarios/scenario8)
- [Scenario 9: Synchronous Content-Based-Router](scenarios/scenario9)

The following sample scenario is supported from version 1.0.10 on:

- [Scenario 10: Supporting Service Interface Operations](scenarios/Scenario10)
