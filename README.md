# Techionista Vendée Globe Business Case

## Table of Contents
1. [Information about Vendée Globe](#information-about-vendée-globe)
2. [Foreword](#foreword)
3. [Created the Event Hub](#created-the-event-hub)
4. [Getting Started - Python Simulator](#getting-started---python-simulator)
   1. [Download and Configure the Python Sailing Simulator](#download-and-configure-the-python-sailing-simulator)
   2. [Run the Python Sailing Simulator](#run-the-python-sailing-simulator)
5. [Challenges](#challenges)
6. [Lambda Architecture in Azure](#lambda-architecture-in-azure)
7. [Stream Analytics Job](#stream-analytics-job)
8. [Incoming Data After Running The Stream Analytics Job](#incoming-data-after-running-the-stream-analytics-job)
9. [Data Storage and Batch Processing](#data-storage-and-batch-processing)
10. [Created External Table](#creating-external-table)
11. [Calculated Boat Ranking](#calculating-boat-ranking)
12. [PowerBI Dashboard](#powerbi-dashboard)
13. [Azure Resources Utilized](#azure-resources-utilized)
14. [Conclusion](#conclusion)

## 1. Information about Vendée Globe <a name="information-about-vendée-globe"></a>
The Vendée Globe is a solo non-stop round-the-world sailboat race known for its extreme challenges and tests of individual endurance. Founded by Philippe Jeantot in 1989, this race occurs every four years and attracts sailors from around the world. In the 9th edition, held in 2020-2021, French sailor Yannick Bestaven emerged victorious after a thrilling 80-day journey.

![](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/2023-09-29%20Vendee%20globe%20route%20portugal%20map.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 2. Foreword <a name="foreword"></a>
The task was to take on the role of Nokia to build a cloud-based Lambda Architecture on Microsoft Azure. The goal was to process telemetry data from sailing boats in real-time and in batches by using various Azure services, including Event Hub, Stream Analytics, data lake, Synapse, and PowerBI, to achieve this.

## 3. Created the Event Hub <a name="how-to-create-the-event-hub"></a>
To start, created an Event Hub Namespace. Here are the steps:
1. Created a free azure subscription.
2. A new resource group was created to organize all Lambda Architecture resources.
3. Configured Namespace for Event Hub by selecting the 'West Europe' region for proximity.

![Configure Event Hub]()

<br> <!-- HTML line break for spacing -->

![Configure EventHub Namespace]()

<br> <!-- HTML line break for spacing -->

## 4. Getting Started - Python Simulator <a name="getting-started---python-simulator"></a>

### 4.1 Download and Configure the Python Sailing Simulator <a name="download-and-configure-the-python-sailing-simulator"></a>
Python sailing simulator was set up to send telemetry data every 60 seconds to our Event Hub. This involved downloading the simulator and configuring it:
- **Download:** Downloaded the Python Sailing Simulator and installed Python on the local machine.
- **Configuration:** Configured the simulator to use the connection string obtained from the Event Hub Namespace.

### 4.2 Run the Python Sailing Simulator <a name="run-the-python-sailing-simulator"></a>

![Sailing Boat Simulator](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/simulator%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 5. Challenges <a name="challenges"></a>
Challenges were to build the Lambda Architecture in Azure, storing and processing data, calculating boat rankings, and creating a PowerBI dashboard to visualize the race.

![Project Challenge](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/project%20challenge.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 6. Lambda Architecture in Azure <a name="lambda-architecture-in-azure"></a>

- **Real-time Path:** Use Event Hub and Stream Analytics for real-time data processing.
- **Batch Processing Path:** Data is stored in Synapse Analytics Workspace with Serverless SQL Pool for batch processing.

<br> <!-- HTML line break for spacing -->

## 7. Stream Analytics Job <a name="stream-analytics-job"></a>
With data flowing into the Event Hub, the next steps include running the stream analytics job.
Some garbled data was observed during the simulator run. To ensure data quality, data cleaning was performed before processing and running the job. The following query was used for data cleaning:

![Data Cleaning Query](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/query%20to%20clean%20data.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 8. Incoming Data After Running The Stream Analytics Job <a name="incoming-data-after-running-the-stream-analytics-job"></a>
- **Event Hub Namespace:**
![](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/namespace%20after%20job%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

- **Stream Analytics:**
![](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/stream%20analytics%20after%20job%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

- **Stream Analytics Input Table:**
![](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/stream%20analytics%20table%20after%20job%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 9. Data Storage and Batch Processing <a name="data-storage-and-processing"></a>
Synapse analytics Workspace in serverless SQL pool and Data lake is used for batch processing.

![Synapse Workspace container after job run](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/synapse%20workspace%20after%20job%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 10. Created External Table <a name="creating-external-table"></a>
Following query was used to create external table in Synapse serverless SQL Pool:

![Query for External Table](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/ext.%20table%20query.png?raw=true)

<br> <!-- HTML line break for spacing -->

External Table After Running The Query:

![External Table Query](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/ext.%20table%20after%20query%20run.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 11. Calculated Boat Ranking <a name="calculating-boat-ranking"></a>
Used SQL query to calculate the table of teams ranked by position in the race as well as the average speed of boats. Boat ranking utilizes the Haversine formula to calculate great-circle distances. It factors in latitude and longitude coordinates for accurate distance measurements. Boat positions are processed, allowing real-time ranking. Following query was used to calculate boat ranking and average speed:

![Query For Boat Ranking](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/query%20for%20boat%20ranking.png?raw=true)

<br> <!-- HTML line break for spacing -->

Ranking Table created after running the query:
![Boat Ranking Table](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/rank%20table%20in%20develop%20window.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 12. PowerBI Dashboard <a name="powerbi-dashboard"></a>
A PowerBI dashboard displays a world map with the current location of each racing team, along with a table showing teams ranked by position in the race. Also included a table for the average current speed of boats.

![PowerBI Dashboard](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/vendee%20globe-dashboard.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 13. Azure Resources Utilized

![Resource Group](https://github.com/Javeria-Umer/Techionista-Vendee-Globe-Race/blob/main/resource%20group.png?raw=true)

<br> <!-- HTML line break for spacing -->

## 14. Conclusion <a name="conclusion"></a>
Successfully set up a Lambda Architecture on Azure to process telemetry data from the Vendée Globe sailing boats. With real-time and batch processing, boat rankings, and a dynamic PowerBI dashboard. 
This business case demonstrates the use of Azure technologies to process and visualize telemetry data from the Techionista Vendée Globe sailboat race. Boat ranking, real-time tracking, data cleaning, and data processing are key components of this solution.

