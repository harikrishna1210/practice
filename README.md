Spark streaming to HBase

Overview
---------
This project is intended to show how to integrate kafka -> Spark Streaming -> HBase

Functionality
--------------
There is a Main class in com.foghorn.main, This class does the following functions:
- TenantHandler:
	-  This class takes zkQuorum,kafkaGroupName,number of threads for each topic,absolute path of tenants.cfg file, 
	   Duration from command line.
	-  Here streaming data is generated from KafkaUtils.createStream() and sent to JavaDStream where it identifies each of the 
           tenants events based on tenant id then perform transformations and ingest processed data into corresponding Hbase tables.
- Transformations:
	-  This is helper class to perform transformations for each channel related to PumpMetrics.
		
How to use
------------
- Generate jar file using below command:
	-  mvn clean install -DskipTests=true
- Copy generated "spark-streaming-jar-with-dependencies.jar" from target directory into /opt/foghorn/foghorn-streaming.jar
	-  target/spark-streaming-jar-with-dependencies.jar /opt/foghorn/foghorn-streaming.jar
- service sparkstreaming start


