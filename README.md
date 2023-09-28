# Vendée Globe Business Case

![Vendée Globe Logo](image-reference-for-logo.png)

## Table of Contents
1. [Introduction](#introduction)
2. [Challenge Overview](#challenge-overview)
3. [Architecture](#architecture)
   1. [Event Hub Configuration](#event-hub-configuration)
   2. [Azure Lambda Architecture](#azure-lambda-architecture)
   3. [Data Storage](#data-storage)
   4. [PowerBI Dashboard](#powerbi-dashboard)
4. [Boat Ranking](#boat-ranking)
5. [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>
The Vendée Globe is an iconic solo non-stop round-the-world sailboat race. This business case involves processing telemetry data from racing boats during this challenging event using Microsoft Azure technologies.

![Vendée Globe Race](image-reference-for-race-image.png)

## Challenge Overview <a name="challenge-overview"></a>
Challenge was to create a cloud-based Lambda Architecture on Azure to process telemetry data from sailing boats. This architecture should enable real-time data processing and batch processing for data collection and calculations.

### Key Objectives:
- Implement a Lambda Architecture to process telemetry data.
- Display boat positions on a world map in real-time.
- Rank racing teams by their current positions.
- Utilize a Python-based simulator for data injection during inter-race periods.

## Architecture <a name="architecture"></a>

### Event Hub Configuration <a name="event-hub-configuration"></a>
Configured an Event Hub and Namespace to ingest telemetry data. 

### Azure Lambda Architecture <a name="azure-lambda-architecture"></a>
Lambda Architecture includes:
- Event Hub for real-time data ingestion.
- Stream Analytics Job for real-time processing.
- Synapse Analytics Workspace with Serverless SQL Pool for batch data processing.

### Data Storage <a name="data-storage"></a>
Data is stored in Data Lake for batch processing.

### PowerBI Dashboard <a name="powerbi-dashboard"></a>
PowerBI dashboard features:
- A world map displaying boat positions.
- A table ranking teams by their race positions.
- A horizontal bar chart showcasing average boat speeds.

## Boat Ranking <a name="boat-ranking"></a>
- Boat ranking utilizes the Haversine formula to calculate great-circle distances.
- It factors in latitude and longitude coordinates for accurate distance measurements.
- Boat positions are processed, allowing real-time ranking.
- Boat ranking data is visualized in the PowerBI dashboard.

## Conclusion <a name="conclusion"></a>
This business case demonstrates the use of Azure technologies to process and visualize telemetry data from the Vendée Globe sailboat race. Boat ranking, real-time tracking, and data processing are key components of this solution.


