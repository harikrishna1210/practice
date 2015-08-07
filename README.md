HBase Rest API's

Overview
---------
Rest API services will query on Hbase tables based on tenant's id and device id, then returns the data in Jason format to Freeboard dashboard.

Functionality
--------------
Here we are showing Rest API services for PumpCavitation and Car tenants.

- Service 1:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecord?tenantId=PumpCavitation&deviceId=pump1
	- To plot the graphs: "Inlet Pressure", "Outlet Pressure", "Pressure Differential", "Flow"
- Service 2:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getTransformedRecords?recordsCount=10&tenantId=PumpCavitation&deviceId=pump1
	- To plot the graphs: "Pump Metrics", "Pump Flow Characteristics"
- Service 3:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getTransformedRecord?recordsCount=1&tenantId=PumpCavitation&deviceId=pump1
	- To plot the graph: "Average of Flow"
- Service 4:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getCavitationDetected?pressure=5&tenantId=PumpCavitation&deviceId=pump1&attribute=pressure_differential
	- To plot the graph: "Cavitation Detected"
- Service 5:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecord?tenantId=Car&deviceId=car1
	- To plot the graph: "Accelerator Pedal%","Engine RPM","Course"
- Service 6:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecords?recordsCount=10&tenantId=Car&deviceId=car1
	- To plot the graph: "Acceleration","Speed"
- Service 7:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getTransformedRecords?recordsCount=1&tenantId=PumpCavitation&deviceId=all
	- To plot Averages of "Inlet Pressure", "Outlet Pressure", "Pressure Differential", "Flow" across all EdgeDevices
- Service 8:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getAnomalyDetection?tenantId=PumpCavitation&deviceId=pump1&attribute=pressure_differential&thresholdValue=20.0&channelList=pump1,pump2
	- To display "Alert message"
- Service 9:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecord?tenantId=PumpCavitation&deviceId=batch-analytics
	- To plot graphs for Batch Analytics

How to use
------------
- Generate war file using below command:
    - mvn clean install -DskipTests=true
- Deploy generated "foghorn-rest.war" from target directory  into /opt/jetty/webapps

