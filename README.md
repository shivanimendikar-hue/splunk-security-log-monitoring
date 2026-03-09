# Security Log Monitoring using Splunk

## Project Overview
This project demonstrates how Splunk SIEM can be used to monitor Windows Security Event Logs and analyze login activity.

## Data Source
Windows Security Event Logs collected from the local system and ingested into Splunk.

## Event IDs Investigated
- Event ID 4624 – Successful login
- Event ID 4625 – Failed login attempt

## SPL Queries Used
source="WinEventLog:Security" EventCode=4624

source="WinEventLog:Security" EventCode=4625

| stats count by Account_Name host

| timechart count

## Analysis Performed
- Monitored successful and failed login activity
- Identified login frequency by user accounts
- Investigated login patterns over time
- Visualized authentication activity using Splunk charts

## Tools Used
- Splunk Enterprise
- Windows Event Logs


![Log Ingestion](log%20ingestion.png)

![Login Success](login%20success.png)

![Login Failure](login%20failure.png)

![Stats by Account](stats%20by%20account.png)

![Timechart](timechart%20visualization.png)
