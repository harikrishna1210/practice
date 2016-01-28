Black Box Application Automation using selenium

Overview
--------
It will run automated test cases of Black Box Application on chrome browser

Includes Below Test Cases
-------------------------
- Start  - Login 
- test01 - Validate fields,elements displayed in every screen throughout the anomaly workflow 
- test02 - Create anomaly workflow and verify the created workflow display in the dashboard 
- test03 - Validate fields,elements display in every screen throughout the ARIMA workflow
- test04 - Create ARIMA workflow and verify the created workflow display in the dashboard
- test05 - Validate fields,elements display in every screen in Linear regression evaluation workflow
- test06 - Create Linear regression evaluation workflow and verify the created workflow display in the dashboard
- test07 - Validate fields,elements display in every screen in Linear regression + Optimization workflow
- test08 - Create Linear regression + Optimization workflow and verify the created workflow display in the dashboard
- Stop   - Logout

Prerequisite
------------
- Please follow instructions from "docs/selnium\_integration\_with\_jenkins.docx" to run this project on Jenkins
- Please modify the IP address in BASE\_URL appropriate to your server IP in config.properties file
	- src/main/resources/config.properties
