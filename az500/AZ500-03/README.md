## Azure SIEM + Attack Simulation Lab

**Deploy a cloud-based Security Information and Event Management (SIEM) environment in Azure, simulate real-world attack scenarios, detect malicious activity using custom rules, and perform incident investigation/response.**

# Project Overview

This lab was built to simulate a real-world Security Operations Center (SOC) workflow using Microsoft Sentinel and the Microsoft Azure environment.

The objective of this project was to:

* Deploy a cloud-based monitoring environment

* Ingest logs from multiple data sources

* Configure detection rules

* Simulate suspicious activities

* Generate security incidents

* Investigate and close incidents within Microsoft Sentinel

This project provided hands-on experience with SIEM configuration, log ingestion, incident generation, alert investigation, and SOC analyst workflows.


# Techologies & Services Used

1. Microsoft Azure

2. Microsoft Sentinel

3. Log Analytics Workspace

4. Microsoft Entra ID

5. Windows Virtual Machine 

6. Microsoft Defender Portal

7. Kusto Query Language (KQL)

8. Remote Desktop Protocol (RDP)


# Objectives

The primary goals of this lab were to:

* Configure a SIEM environment using Microsoft Sentinel

* Connect Azure resources and identity logs

* Create custom detection analytics rules

* Simulate malicious and suspicious activities

* Generate and investigate incidents

* Understand incident triage and false positive analysis


# Lab Deployment Steps

1. Resource Group Creation

A dedicated Azure Resource Group was created to organize and manage all resources related to the lab environment.

<p align="center"><strong>Figure 1: Azure Resource Group Creation </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/01-create-RG.png" width="700" height="400">
</p>

Purpose:

* Centralized resource management

* Easier monitoring and cleanup

* Cost management and resource isolation


2. Virtual Machine Creation

A Windows Virtual Machine was deployed within Azure to simulate an endpoint/device environment for monitoring and event generation.

Configuration Included:

* Public IP assignment

* RDP enabled for remote access

* Security rules configured for connectivity

<p align="center"><strong>Figure 2: Virtual Machine Creation </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/02-create-VM.png" width="700" height="400">
</p>

Purpose:

* Generate authentication and activity logs

* Simulate endpoint behavior

* Perform suspicious sign-in testing


3️. Log Analytics Workspace Creation

An Azure Log Analytics Workspace was created to collect, store, and analyze logs generated within the environment.

<p align="center"><strong>Figure 3: Log Analytics Workspace Creatio </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/03-create-LAW.png" height="400">
</p>

Purpose:

* Centralized log storage

* Enable querying and monitoring

* Integration with Microsoft Sentinel



4. Data Collection Rule (DCR) Configuration

A Data Collection Rule (DCR) was created to define which logs and telemetry data would be collected from the virtual machine.

<p align="center"><strong>Figure 4:  Data Collection Rule </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/04-DCR-configuration.png" width="700" height="400">
</p>

Purpose:

* Collect security-related event logs

* Enable log ingestion into Log Analytics

* Improve monitoring visibility


5. Virtual Machine Connection

The virtual machine was connected to the configured monitoring environment.

Actions Performed:

* Connected VM to Log Analytics Workspace

* Verified agent communication

* Confirmed successful telemetry flow

<p align="center"><strong>Figure 5: Virtual Machine Connection </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/05-connect-to-VM.png" width="700" height="400">
</p>

Challenges Encountered:

* Initial RDP connection issues

* Connectivity troubleshooting and validation


6. Microsoft Sentinel Deployment

Microsoft Sentinel was added and connected to the existing Log Analytics Workspace.

<p align="center"><strong>Figure 6: Microsoft Sentinel Deployment </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/06-add-sentinel-to-workspace.png" width="700" height="400">
</p>

Purpose:

* Enable SIEM functionality

* Centralize security monitoring

* Create and manage incidents and alerts


7. Installed and Configured Data Connectors

Multiple data connectors were configured to ingest logs into Microsoft Sentinel.

Configured Connectors:

* Azure Activity Logs

<p align="center"><strong>Figure 7: Azure Activity Connector </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/07-data-connectors.png" width="700" height="400">
</p>

* Microsoft Entra ID Sign-In Logs

* Audit Logs

Purpose:

* Collect authentication events

* Monitor administrative activity

* Detect suspicious account behavior


8. Created Analytics Rules for Threat Detection

Custom analytics rules were configured within Microsoft Sentinel to detect suspicious activities.

Rules Included:

* Anomalous sign-in detection

<p align="center"><strong>Figure 8: Anomalous sign-in Rule </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/08-analytics-rules1.png" width="700" height="400">
</p>

* Unusual Location Login Detection

* Privilege Escalation Detection

<p align="center"><strong>Figure 9: Privilege Escalation Rule </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/09-analytics-rules2.png" width="700" height="400">
</p>

Purpose:

* Automatically generate alerts

* Simulate SOC detection workflows

* Trigger incident creation


9. Generated Logs Through Simulated Suspicious Activities

Multiple activities were intentionally performed to trigger analytics rules and generate incidents.

Simulated Activities Included:

* Failed Sign-In Attempts

Incorrect credentials were repeatedly used to simulate suspicious authentication attempts.


<p align="center"><strong>Figure 10: Failed Sign-In Attempts </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/11-failed-sign-in.png" width="700" height="400">
</p>


* VPN/Proxy Login Simulation

A VPN/proxy service was used to generate sign-ins from unusual geographic locations.

* Privileged User Creation

A new user account was created and assigned elevated privileges to simulate privilege escalation activity.


<p align="center"><strong>Figure 11: Failed Sign-In Attempts </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/11-failed-sign-in.png" width="700" height="400">
</p>


Purpose:

* Generate security alerts

* Test detection logic

* Validate analytics rule functionality


10.  Configured Diagnostic Settings

Diagnostic settings were enabled to ensure logs were properly collected and forwarded to the monitoring environment.

<p align="center"><strong>Figure 12: Diagnostic Settings </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/13-diagnostic-settings.png" width="700" height="400">
</p>


Purpose:

* Enable continuous log collection

* Improve visibility across resources

* Support incident generation and investigation



11. Verified Successful Log Generation

After configuration and simulations, logs were successfully ingested into the Log Analytics Workspace and surfaced within Microsoft Sentinel.

Verification Included:

* Reviewing sign-in logs

* Confirming audit logs

* Checking alert generation

* Monitoring incident creation


<p align="center"><strong>Figure 13: Alert Generation </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/14-alerts-generated.png" width="700" height="400">
</p>


12. Investigated and Closed Incidents

Generated incidents were investigated within Microsoft Sentinel.

<p align="center"><strong>Figure 14: Incident Investigation </strong></p>

<p align="center"> <img src="az500/AZ500-03/images/18-closed-incidents.png" width="700" height="400">
</p>


Investigation Process:

* Reviewed entities involved

* Analyzed timestamps and user activity

* Examined triggered analytics rules

* Validated source IP behavior

* Assessed incident severity


# Outcome

The incidents were determined to be Benign Positives because the activities were intentionally generated as part of the lab simulation.

The incidents were then properly closed within Sentinel after documentation and analysis.


# Key Skills Demonstrated

* SIEM Configuration

* Cloud Security Monitoring

* Log Analysis

* Incident Investigation

* Security Event Correlation

* Threat Detection

* Azure Administration

* Microsoft Sentinel Operations

* Identity & Access Monitoring

* SOC Analyst Workflow


# Key Takeaways

This lab provided practical experience in deploying and managing a cloud-native SIEM solution using Microsoft Sentinel. It also reinforced critical SOC analyst skills such as troubleshooting, incident investigation, log analysis, and detection engineering.

One of the biggest lessons learned during this project was that troubleshooting and resolving configuration issues is a major part of real-world cloud security operations.

