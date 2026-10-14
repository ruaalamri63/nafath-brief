Version: NAFATH-V2

Track: Cybersecurity

## Overview
A reliable 5G emergency service depends on six IT fields working together. Software teams must handle failed requests so that retries do not cause duplicate actions. This helps mobile apps change safely when connectivity returns, while keeping essential information available offline during outages. AI teams can predict network congestion, but they must test their models on traffic data they have not seen before. These predictions, together with daily regional usage reports from data teams, help networking teams plan resources for a dedicated 5G emergency slice. This slice should provide the capacity and performance emergency responders need. Cybersecurity teams must prepare for incidents, detect threats, contain attacks, and restore affected services while protecting emergency communications.  My track focuses on the incident response lifecycle and how it helps keep emergency services running.

## Software
Safe HTTP methods like: GET, HEAD, OPTIONS, and TRACE is do not ask the server to change data. These methods, along with PUT and DELETE, are also idempotent. POST and CONNECT are neither safe nor idempotent by default. If communication fails, emergency apps can retry idempotent requests. They should automatically retry other requests only if repeating them is harmless or they know the original request was not carried out.

Resource: RFC 9110: HTTP Semantics - https://www.rfc-editor.org/rfc/rfc9110.html

## AI
Overfitting happens when a model works well on the data it learned from but poorly on new data. Cross-validation helps detect this by training the model on one part of the data and checking it on another, several times. For traffic data, use older data for training and newer data for checking, so future information is not used in training. Finally, test the model on separate data that was not used in either step.

Resource: Cross-validation: evaluating estimator performance - https://scikit-learn.org/stable/modules/cross_validation.html

## Mobile
The app should show saved information When offline, save notes on the device, and display connection status with changes marked as pending or confirmed. When the connection returns, it should send pending changes and get server updates in the background. Temporary failures should be retired with longer waits. Urgent actions needing live confirmation should stay unavailable or marked as unconfirmed until confirmation arrives.

Resource: Build an offline-first app - https://developer.android.com/topic/architecture/data-layer/offline-first

## Networking
5G network slicing creates virtual networks on shared infrastructure, each designed for different needs. An emergency slice can prioritize responders and support low delay, suitable speeds, and reliable connections during congestion. It should cover the radio, transport, and core networks, with monitoring and backups that can take over during failures. A slice alone does not protect against physical outages.

Resource: Network slicing - https://www.ericsson.com/en/network-slicing

## Cybersecurity
NIST’s incident response lifecycle focuses on Detect, Respond, and Recover, supported by preparation and ongoing improvement. Preparation sets clear roles, protections, and recovery plans. Detect finds and checks signs of attacks. Respond investigates, isolates affected systems, removes threats, and keeps teams informed while protecting emergency communications. Recover restores services and checks they work correctly. Lessons from every stage help improve security and procedures.

Resource: Incident Response - https://csrc.nist.gov/projects/incident-response
## Data
A star schema links a fact table directly to dimension tables. A snowflake schema splits dimension data into smaller tables, reducing repeated information but making queries more complex. For daily regional reports, I would choose a star schema with one row per region per day, linked to Date and Region tables. This makes filtering and adding session counts and data volumes across regions and days easier.

Resource: Understand star schema and the importance for Power BI - https://learn.microsoft.com/en-us/power-bi/guidance/star-schema

## Misconception in My Track
A common misconception is that incident response planning starts only after an attack is detected. In fact, the telecom operator should prepare responsibilities, security controls, and recovery plans before an attack occurs. Under the “Overview” heading, NIST’s Incident Response page explains that Govern, Identify, and Protect support preparation, while Detect, Respond, and Recover form incident response itself. For the emergency 5G service, this preparation helps teams act quickly and consistently during attacks. Lessons learned throughout the lifecycle should also improve future preparation and response.

## Open Question
How can the operator isolate an attacked part of the 5G network while keeping emergency communications available? I would next verify whether its backup connections and recovery plans can maintain the service during a cyber attack
