Oozie


How to use
------------
- By using batchprocessing code generate jar file using below command:
	-  mvn clean install -DskipTests=true
- Copy generated dependency jar file from target directory to oozie/batch_analytics & oozie/batch_analytics/lib directories
- Copy multi-tenancy/tools/lib/htrace-core-3.1.0-incubating.jar to oozie/batch_analytics & oozie/batch_analytics/lib directories
