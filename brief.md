Version: NAFATH-V2

Track: Cybersecurity

## Overview
A reliable 5G emergency service depends on six IT fields working together. Software teams must handle failed requests so that retries do not cause duplicate actions. This helps mobile apps change safely when connectivity returns, while keeping essential information available offline during outages. AI teams can predict network congestion, but they must test their models on traffic data they have not seen before. These predictions, together with daily regional usage reports from data teams, help networking teams plan resources for a dedicated 5G emergency slice. This slice should provide the capacity and performance emergency responders need. Cybersecurity teams must prepare for incidents, detect threats, contain attacks, and restore affected services while protecting emergency communications. My track focuses on the incident response lifecycle and how it helps keep emergency services running.

## Software
Safe HTTP methods like: GET, HEAD, OPTIONS, and TRACE is do not ask the server to change data. These methods, along with PUT and DELETE, are also idempotent. POST and CONNECT are neither safe nor idempotent by default. If communication fails, emergency apps can retry idempotent requests. They should automatically retry other requests only if repeating them is harmless or they know the original request was not carried out.

Resource: Idempotency definition - https://www.sanity.io/glossary/idempotency
## AI
Overfitting happens when a model works well on the data it learned from but poorly on new data. Cross-validation helps detect this by training the model on one part of the data and checking it on another, several times. For traffic data, use older data for training and newer data for checking, so future information is not used in training. Finally, test the model on separate data that was not used in either step.

Resource: What is overfitting? - https://www.ibm.com/think/topics/overfitting

## Mobile
The app should show saved information When offline, save notes on the device, and display connection status with changes marked as pending or confirmed. When the connection returns, it should send pending changes and get server updates in the background. Temporary failures should be retired with longer waits. Urgent actions needing live confirmation should stay unavailable or marked as unconfirmed until confirmation arrives.

Resource: What is Offline-First Data Synchronization? - https://www.back4app.com/glossary/offline-first-data-sync

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
