---
aliases:
  - tig
tags:
  - defense
  - pcap
  - pandas
last_tested: 06/2024
transferable: N/A
---
---
## **PoC**

https://github.com/mundruid/iot_spy

## **Details**

**Goal**: Use Telegraf, Influx, Grafana (TIG) open source telemetry stack for network traffic monitoring.

- TIG stack is open source and has good containerization so it can be span up easily. Here is a basic [TIG configuration](https://github.com/mundruid/tig) to set up all three containers.
  - Telegraf is a collector and has useful plugins for network trafic
  - Influx is a time series database, made for fast and efficient queries that are indexed by time
  - Grafana is an open source visualization tool that has some neat customizations and robust API
- Telegraf netflow is used
- `sshdump` dumps packets to influx real time
- Alerts can be setup with Grafana for unusual activity

[Video](https://grafana.com/go/observabilitycon/2021/security-metrics-smart-devices/)
[Slides](https://docs.google.com/presentation/d/199MunnWc3g9UhRyBe3Zmz6VraImR5b5P/edit?usp=sharing&ouid=108545322802236598515&rtpof=true&sd=true)