# TryHackMe – ItsyBitsy

![Platform](https://img.shields.io/badge/Platform-TryHackMe-red?style=for-the-badge&logo=tryhackme)
![Category](https://img.shields.io/badge/Category-SOC%20Analysis-blue?style=for-the-badge)
![SIEM](https://img.shields.io/badge/Tool-ELK%20Stack-yellow?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

## Overview

**ItsyBitsy** is a TryHackMe Premium challenge focused on investigating a potential Command and Control (C2) communication alert using the ELK Stack and Kibana.

The investigation involves analyzing HTTP connection logs, identifying suspicious outbound traffic, tracing malicious file downloads, and extracting a hidden flag.

## Learning Objectives

- Investigate IDS alerts using Kibana.
- Analyze HTTP connection logs.
- Identify suspicious user activity and source IP addresses.
- Investigate Windows LOLBins abused for malicious downloads.
- Identify C2 infrastructure and suspicious URLs.
- Trace malicious files hosted on legitimate filesharing services.
- Extract indicators of compromise (IOCs).

## Lab Environment

| Component | Details |
|---|---|
| Platform | TryHackMe |
| Room | ItsyBitsy |
| Difficulty | Premium Challenge |
| SIEM | ELK Stack |
| Interface | Kibana Discover |
| Dataset | `connection_logs` |
| Investigation Period | March 2022 |
| Log Type | HTTP Connection Logs |

## Incident Scenario

A SOC analyst named John observed an IDS alert indicating potential C2 communication involving Browne, an employee in the HR department.

A suspicious file was accessed from a filesharing service potentially being abused as a C2 server.

A week-long collection of HTTP connection logs was ingested into the `connection_logs` index.

The investigation focused on identifying the infected machine, tracing its network activity, identifying the downloaded file, and retrieving a secret code.

## Investigation Workflow

### 1. Access Kibana

Access the deployed TryHackMe machine and navigate to Kibana Discover.

Provided lab credentials:

- Username: `Admin`
- Password: `elastic123`
- Index: `connection_logs`

### 2. Analyze HTTP Connection Logs

Filter the logs for March 2022.

Determine the total number of events and investigate connections associated with the suspected HR user.

### 3. Identify the Infected Host

Examine the network records to identify the IP address associated with Browne's machine.

### 4. Investigate LOLBins

Identify the legitimate Windows executable used to download the suspicious file.

**Security concept:** Living Off the Land Binaries (LOLBins) are legitimate system utilities that attackers abuse to perform malicious activities.

### 5. Identify C2 Infrastructure

Investigate outbound HTTP connections and identify the legitimate filesharing platform being abused for C2 communication.

### 6. Trace the Malicious URL

Identify the full C2 URL and the filename accessed from the filesharing service.

### 7. Extract the Flag

Inspect the suspicious file and retrieve the hidden TryHackMe flag.

Expected format:

`THM{...}`

## Key Security Concepts

| Concept | Description |
|---|---|
| C2 Communication | Communication between compromised hosts and attacker infrastructure. |
| IDS | Detects potentially malicious network activity. |
| LOLBins | Legitimate binaries abused for malicious purposes. |
| HTTP Logs | Provide visibility into web-based network communications. |
| IOC | Evidence indicating potential compromise. |
| SIEM | Centralized platform for log collection and security analysis. |
| Kibana Discover | Used to search and investigate indexed log events. |

## Investigation Findings

Record the answers obtained during the lab:

| Investigation Question | Finding |
|---|---|
| March 2022 event count | Add verified answer |
| Suspected user's IP address | Add verified answer |
| Windows download binary | Add verified answer |
| Filesharing / C2 service | Add verified answer |
| Full C2 URL | Add verified answer |
| Accessed filename | Add verified answer |
| Secret flag | `THM{...}` |

*Note: Findings have been left as placeholders because the actual answers were not included in the supplied room content.*

## SOC Analyst Takeaways

- Correlate IDS alerts with available network telemetry.
- Investigate suspicious outbound HTTP connections.
- Monitor legitimate Windows binaries for unusual behavior.
- Do not automatically trust traffic to legitimate filesharing platforms.
- Extract URLs, domains, IP addresses and filenames as potential IOCs.
- Reconstruct the attack chain using available evidence.
- Document findings clearly for incident escalation.

## Skills Practiced

- ELK Stack fundamentals
- Kibana Discover
- SIEM log analysis
- HTTP traffic investigation
- C2 detection
- IOC identification
- LOLBin investigation
- Network-based threat hunting
- SOC alert triage

## Conclusion

This challenge demonstrates how a SOC analyst can investigate potential C2 communication using network connection logs and SIEM capabilities.

Even when endpoint telemetry is unavailable, HTTP logs can provide valuable evidence for identifying suspicious downloads, compromised hosts, attacker infrastructure and malicious file access.

**Primary lesson:** Effective SOC investigations depend on correlating available evidence rather than relying on a single security alert.

## Lab Reference

[TryHackMe – ItsyBitsy](https://tryhackme.com/)

---

*Part of my ongoing SOC Analyst and Blue Team learning journey.*
