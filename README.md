# Techionista Vendée Globe Business Case

## Table of Contents
1. [Introduction](#introduction)
2. [Challenge Overview](#challenge-overview)
3. [Sailing Boat Simulator](#sailing-boat-simulator)
4. [Data Cleaning](#data-cleaning)
5. [Lambda Architecture](#lambda-architecture)
   1. [Event Hub Configuration](#event-hub-configuration)
   2. [Data Storage](#data-storage)
   3. [PowerBI Dashboard](#powerbi-dashboard)
6. [Boat Ranking](#boat-ranking)
7. [Azure Resources Used](#azure-resources-used)
8. [Conclusion](#conclusion)

## Introduction <a name="introduction"></a>
The Vendée Globe is an iconic solo non-stop round-the-world sailboat race. This business case involves processing telemetry data from racing boats during this challenging event using Microsoft Azure technologies.

![](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/2023-09-29%20Vendee%20globe%20route%20portugal%20map.png?raw=true)

## Challenge Overview <a name="challenge-overview"></a>
The challenge was to create a cloud-based Lambda Architecture on Azure to process telemetry data from sailing boats. This architecture should enable real-time data processing and batch processing for data collection and calculations.



## Sailing Boat Simulator <a name="sailing-boat-simulator"></a>
Used a Python-based sailing boat simulator to generate telemetry data for representing the boats. Stream Analytics was used to ingest data from the simulator.

![Sailing Boat Simulator](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/simulator%20run.png?raw=true)

## Data Cleaning <a name="data-cleaning"></a>
Some garbled data was observed during the simulator run. To ensure data quality, data cleaning was performed before processing. The following query was used for data cleaning:

![Data Cleaning Query](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/query%20to%20clean%20data.png?raw=true)

## Lambda Architecture <a name="lambda-architecture"></a>
The Lambda Architecture includes:
- **Event Hub Configuration:** Configured an Event Hub for the ingestion of simulator data.

![Event Hub Configuration](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/stream%20analytics%20input%20event%20hub.png?raw=true)

- **Data Storage:** Data is stored in an Azure Data Lake for batch processing.

![Data Storage](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/stream%20analytics%20outputs.png?raw=true)

- **Batch Processing:** Synapse Analytics Workspace with Serverless SQL Pool is used for batch processing.

![Batch Processing](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/synapse%20workspace%20after%20job%20run.png?raw=true)

- **PowerBI Dashboard:** PowerBI dashboard features a world map displaying boat positions during the race, a table ranking teams by their race positions, and a horizontal bar chart showcasing average boat speeds.

![PowerBI Dashboard](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/vendee%20globe-dashboard.png?raw=true)

## Boat Ranking <a name="boat-ranking"></a>
Boat ranking utilizes the Haversine formula to calculate great-circle distances. It factors in latitude and longitude coordinates for accurate distance measurements. Boat positions are processed, allowing real-time ranking. Boat ranking data is visualized in the PowerBI dashboard.

![Boat Ranking](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/query%20for%20boat%20ranking.png?raw=true)

## Azure Resources Used <a name="azure-resources-used"></a>
The following Azure resources were used in this project:
- Event Hub: For real-time data ingestion.
- Azure Data Lake: For data storage.
- Synapse Analytics Serverless SQL Pool: For batch processing.
- Stream Analytics: For real-time boat location data from the simulator.
![Namespace Configuration](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/namespace%20after%20job%20run.png?raw=true)
## Conclusion <a name="conclusion"></a>
This business case demonstrates the use of Azure technologies to process and visualize telemetry data from the Vendée Globe sailboat race. Boat ranking, real-time tracking, data cleaning, and data processing are key components of this solution.

