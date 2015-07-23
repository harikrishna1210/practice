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
	-  Here streaming data is generated from KafkaUtils.createStream() and sent to JavaDStream where it identifies each of 
	   the tenants events based on tenant id then perform transformations and ingest processed data into corresponding Hbase table           s.
- Transformations:
        - This is helper class to perform transformations for each channel related to PumpMetrics.
		
How to use
------------
spark-submit --master yarn-client --driver-class-path $BASE_DIR/lib/SparkHBase.jar:$BASE_DIR/lib/spark-hbase-0.0.2-clabs.jar:$BASE_DIR/lib/htrace-core-3.1.0-incubating.jar --class com.foghorn.main.TenantHandler $BASE_DIR/foghorn-streaming.jar 127.0.0.1:2181 group1 5 $BASE_DIR/tenants.cfg 5000
