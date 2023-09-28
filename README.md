# Vendée Globe Business Case

![Vendée Globe Logo](image-reference-for-logo.png)

## Table of Contents
1. [Introduction](#introduction)
2. [Challenge Overview](#challenge-overview)
3. [Sailing Boat Simulator](#sailing-boat-simulator)
4. [Lambda Architecture](#lambda-architecture)
   1. [Event Hub Configuration](#event-hub-configuration)
   2. [Data Storage](#data-storage)
   3. [PowerBI Dashboard](#powerbi-dashboard)
5. [Boat Ranking](#boat-ranking)
6. [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>
The Vendée Globe is an iconic solo non-stop round-the-world sailboat race. This business case involves processing telemetry data from racing boats during this challenging event using Microsoft Azure technologies.

![Vendée Globe Race](image-reference-for-race-image.png)

## Challenge Overview <a name="challenge-overview"></a>
The challenge was to create a cloud-based Lambda Architecture on Azure to process telemetry data from sailing boats. This architecture should enable real-time data processing and batch processing for data collection and calculations.

## Sailing Boat Simulator <a name="sailing-boat-simulator"></a>
Used a Python-based sailing boat simulator to generate telemetry data for representing the boats.

## Lambda Architecture <a name="lambda-architecture"></a>
The Lambda Architecture includes:
- **Event Hub Configuration:** We configured an Event Hub to ingest telemetry data.
- **Data Storage:** Data is stored in Azure Data Lake for batch processing.
- **Batch Processing:** Synapse Analytics Workspace with Serverless SQL Pool is used for batch processing.
- **PowerBI Dashboard:** Our PowerBI dashboard features a world map displaying boat positions, a table ranking teams by their race positions, and a horizontal bar chart showcasing average boat speeds.

## Boat Ranking <a name="boat-ranking"></a>
- Boat ranking utilizes the Haversine formula to calculate great-circle distances.
- It factors in latitude and longitude coordinates for accurate distance measurements.
- Boat positions are processed, allowing real-time ranking.
- Boat ranking data is visualized in the PowerBI dashboard.

## Conclusion <a name="conclusion"></a>
This business case demonstrates the use of Azure technologies to process and visualize telemetry data from the Vendée Globe sailboat race. Boat ranking, real-time tracking, and data processing are key components of this solution.
