# Scenario 9

Scenario 9 is a synchronous Content-Based-Router scenario to fetch flight booking information.
- Depending on the airline ID, the synchronous request is routed to either of two receivers.
- The scenario runs on the synchronous integrated messaging runtime which is supported as of integration package version 1.0.9 only.
- The scenario supports different tenant stages like DEV, QA, PRD.

<br>![](/images/Scenario_9.png)

**Note**: We assume that you run the scenario on your quality assurance landscape with stage key **QA**. During runtime the sender names are mapped to their alias and vice versa.
The alias name is actually used across all tenant stages to identify the integration scenario stored in the Partner Directory.
Ensure, that the landscape has been setup in the Partner Directory mapping the stages like **DEV**, **QA**, and **PRD** to the tenant names.

## Test the scenario
To test the scenario, open your Postman client and navigate to the folder **Scenario 9 - Synchronous CBR --> Trigger sample messages** of the provided Postman collection **Pipeline Concept - Sample Scenarios**.

In the message monitor of your SAP Integration Suite tenant, you can monitor the messages which were exchanged.

**Note**: We have prepared different messages using the sender names of the landscape stage **QA**. Depending on your landscape settings, you may have to change the sender name in the header of the message requests.

You can run any of the GET requests below the **Trigger sample messages** folder:
- The first request with airline ID **LH** should run successfully from sender **BS_AG9_Q** to receiver **BS_AL91_Q**:
  - The response should indicate that the flight is fully booked.
  - You should see 3 new logs.
  - You should see a log for the integrated messaging runtime pipeline step.

<br>![](/images/21_01_Scenario9_MPL.png)

- The second request with airline ID **SQ** should run successfully from sender **BS_AG9_Q** to receiver **BS_AL92_Q**:
  - The response should indicate that seats are available.
  - You should see 3 new logs.
  - You should see a log for the integrated messaging runtime pipeline step.
- The third request with airline ID **LH** should run into an error:
  - The response should indicate that the flight class doesn not exist.
  - You should see 3 new logs whereas two are in failed status.
  - You should see a log for the integrated messaging runtime pipeline step.

<br>![](/images/21_02_Scenario9_MPL.png)

Go back to [Main page](../../README.md)
