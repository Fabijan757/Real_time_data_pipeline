Real-Time Streaming Project (Kafka + Spark + MySQL + Streamlit)

This project demonstrates how data can be produced and processed in real time.
The goal is to build a system that sends events (views, clicks, purchases),
stores them in a database, and visualizes them on a dashboard.

1. Data producer
A Python script continuously sends random product events:
- item
- color
- action (view, click, purchase)
- timestamp
Data is sent to the Kafka topic 'live_events'.

2. Kafka
Kafka acts as a message broker that receives events and forwards them to Spark.
It runs in Docker together with Zookeeper.

3. Spark Streaming
Spark reads data from Kafka in real time and writes it into MySQL.
Each event is transformed into a structured table format before storage.

4. MySQL database
Spark populates the 'events_stream' table:
- item
- color
- action
- event_time

5. SQL analytics
After data ingestion, analytical queries are executed:
- top selling items
- most clicked items
- most viewed items
- conversion rate (purchase / view)

6. Streamlit dashboard
The dashboard displays:
- total events
- total views, clicks, and purchases
- top selling items chart
- most clicked items chart
- most viewed items chart

7. Final result
Complete real-time data flow:
Producer → Kafka → Spark → MySQL → Streamlit Dashboard
