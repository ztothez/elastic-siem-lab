# Building a Cloud-Based SIEM with Elastic Stack

This repository contains configuration files and notes for building a cloud-based SIEM using the Elastic Stack.

The project focuses on collecting, normalizing, and analyzing security-relevant telemetry from both Windows and Linux endpoints in order to support detection and investigation workflows.

## Overview
The setup demonstrates how endpoint and network telemetry can be shipped into a centralized Elastic Stack deployment for security monitoring purposes.

The emphasis is on **visibility, structure, and clarity**, rather than production hardening.

## Data sources
The following Elastic Beats are used to collect telemetry:

- **Winlogbeat** – Windows Security and Event Logs
- **Auditbeat** – Linux audit and file integrity events
- **Filebeat** – System and application logs
- **Packetbeat** – Network traffic metadata

Both Windows and CentOS/Linux examples are included.

## Repository contents
- `winlogbeat.yml` – Windows event log collection
- `auditbeat-win10.yml` – Auditbeat configuration for Windows
- `auditbeat-centos.yml` – Auditbeat configuration for Linux
- `filebeat-centos.yml` – Linux log ingestion
- `packetbeat-win10.yml` – Windows network telemetry
- `packetbeat-centos.yml` – Linux network telemetry

## Intended use
This repository is intended for:
- Learning SIEM fundamentals
- Understanding Elastic Beats configuration
- Building SOC / blue-team lab environments
- Experimenting with log ingestion and visibility

It is **not** intended to be a production-ready deployment.

## Tech stack
- Elastic Stack (Elasticsearch, Kibana)
- Elastic Beats (Winlogbeat, Auditbeat, Filebeat, Packetbeat)
- Windows and Linux endpoints

## Notes
The configura
