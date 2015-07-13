HBase Rest API's

Overview
---------
Rest API services will query on Hbase tables based on tenant's id and device id, then returns the data in Jason format to Freeboard dashboard.

Functionality
--------------
Here we are showing Rest API services for PumpCavitation and Car tenants.

- Service 1:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getLastRecord?tenantId=PumpCavitation&deviceId=pump1
	- To plot the graphs: "Inlet Pressure", "Outlet Pressure", "Pressure Differential", "Flow"
- Service 2:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecords?recordsCount=150&tenantId=PumpCavitation&deviceId=pump1
	- To plot the graphs: "Pump Metrics", "Pump Flow Characteristics"
- Service 3:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getRecentRecords?recordsCount=1&tenantId=PumpCavitation&deviceId=pump1
	- To plot the graph: "Average of Flow"
- Service 4:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getCavitationDetected?pressure=5&tenantId=PumpCavitation&deviceId=pump1
	- To plot the graph: "Cavitation Detected"
- Service 5:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getCarLastRecord?tenantId=Car&deviceId=Car1
	- To plot the graph: "Accelerator Pedal%","Engine RPM","Course"
- Service 6:
	- URL: http://130.211.121.169:8080/foghorn-rest/service/getCarRecords?recordsCount=10&tenantId=Car&deviceId=Car1
	- To plot the graph: "Acceleration","Speed"

How to use
------------
Generate war file from eclipse and deploy it in /opt/jetty/webapps
