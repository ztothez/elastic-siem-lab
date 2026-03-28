# Elastic SIEM Lab
A hands-on SIEM lab built using the Elastic Stack, focused on **centralized telemetry ingestion, log analysis, and detection engineering across Windows and Linux endpoints**.

This repository contains configuration files and notes for building a **cross-platform security monitoring pipeline** using Elastic Beats and endpoint telemetry.

## Overview
This project demonstrates how endpoint and network telemetry can be:
* collected from distributed systems
* normalized and shipped to a central platform
* analyzed for security-relevant signals

The setup reflects a **SOC-oriented workflow**, where raw logs are transformed into structured data for detection and investigation.

The emphasis is on:
* **Visibility** → understanding what data is available
* **Structure** → organizing telemetry for analysis
* **Detection thinking** → preparing data for meaningful security use

## Architecture
```text
[Windows / Linux Endpoints]
    ├─ Winlogbeat (Windows logs)
    ├─ Auditbeat (audit + file integrity)
    ├─ Filebeat (system/application logs)
    ├─ Packetbeat (network metadata)
            ↓
[Elastic Stack]
    ├─ Elasticsearch (storage & indexing)
    ├─ Kibana (analysis & visualization)
            ↓
[Detection & Investigation Workflows]
```

## Data Sources
The following Elastic Beats are used to collect telemetry:

* **Winlogbeat**
  Windows Security and Event Logs (authentication, system activity)

* **Auditbeat**
  Linux audit events and file integrity monitoring

* **Filebeat**
  System and application log ingestion

* **Packetbeat**
  Network traffic metadata and protocol-level visibility

Both Windows and Linux (CentOS) configurations are included to simulate **heterogeneous environments**.

## Repository Contents
* `winlogbeat.yml` – Windows event log collection
* `auditbeat-win10.yml` – Auditbeat configuration for Windows
* `auditbeat-centos.yml` – Auditbeat configuration for Linux
* `filebeat-centos.yml` – Linux log ingestion
* `packetbeat-win10.yml` – Windows network telemetry
* `packetbeat-centos.yml` – Linux network telemetry

## Use Cases
* **SOC Lab Simulation**
  Understanding how telemetry flows through a SIEM pipeline

* **Detection Engineering Experiments**
  Preparing and structuring data for rule creation

* **Cross-Platform Visibility**
  Comparing Windows and Linux telemetry sources

* **SIEM Pipeline Prototyping**
  Testing ingestion, normalization, and analysis workflows

## Tech Stack
* Elastic Stack (**Elasticsearch**, **Kibana**)
* Elastic Beats (**Winlogbeat**, **Auditbeat**, **Filebeat**, **Packetbeat**)
* Windows & Linux endpoints

## Design Principles
* **Telemetry First**
  Focus on collecting meaningful and relevant data

* **Cross-Platform Coverage**
  Visibility across both Windows and Linux systems

* **Modular Configuration**
  Each component can be adapted or extended

* **Detection-Oriented Approach**
  Built with downstream analysis and detection in mind

## Limitations
* Not production-hardened
* No scaling, access control, or resilience considerations
* Detection rules and alerting are minimal

This project is intended as a **practical lab environment**, not a production deployment.

## Positioning
A hands-on project demonstrating:
* SIEM pipeline architecture
* Endpoint and network telemetry collection
* Cross-platform log ingestion
* Detection engineering fundamentals

## Future Improvements
* Add detection rules (e.g., Sigma-based)
* Create Kibana dashboards for visualization
* Implement alerting and correlation logic
* Simulate attack scenarios for validation
* Add log enrichment and normalization layers
