## Slack Integration with Neva QA system

Overview
---------
SlackBot to call API for QA system and show the same in chat interface

Botkit is a toolkit for making slack bot applications
- https://github.com/howdyai/botkit/

Prerequisites
-------------
- *Steps to install Node.js and NPM*
	
	```bash
    wget https://dl.fedoraproject.org/pub/epel/epel-release-latest-6.noarch.rpm
    rpm -ivh epel-release-latest-6.noarch.rpm
    yum install -y nodejs npm --enablerepo=epel
    yum-config-manager--disable epel
    ```
- *Install Botkit* 
    - Check-out Botkit directly from Git.
    - If you want to use the example code and included bots, it may be preferable to use Github over NPM.
        ```bash
        git clone https://github.com/howdyai/botkit.git
        ```
    - After cloning Git repository, you have to install the node dependencies. Navigate to the root of your cloned repository and use npm to install all necessary dependencies.
        ```bash
        npm install
        ```
- *First make a bot integration inside of your Slack channel. Go here:*
    - https://my.slack.com/services/new/bot (modify my.slack.com points to your slack domain)
    - Enter a name for your bot.
- *When you click "Add Bot Integration", you are taken to a page where you can add additional details about your bot, like an avatar, as well as customize its name & description.*
    - Copy the API token that Slack gives you. You'll need it.
    - Once the bot gets created click on "DIRECT MESSAGES" on the left hand side. In the search box type the bot name & click on "GO". Now the bot name is available

- *Copy ```slack-integration.js``` file to root of your cloned repository and Modify the following properties in ```slack-integration.js```*  
 ```
var qa_system_url = 'http://52.9.55.248:7001/classify/similarDocs/appleforum?row=';
var factiod_url = 'http://52.9.55.248:7002/queryprocessor?row=';
var incident_url = 'http://52.37.217.33:8080/incident/createIncident';
var qtype_url  = 'http://52.9.55.248:7002/classify/qtype/filteredQuestions?row=';
var incident_ui_url = 'http://52.43.240.50:3000/#/incidents/';
```
- Run the slack-integration bot app, using the token you just copied:
    ```token=REPLACE_THIS_WITH_YOUR_TOKEN node slack-integration.js```
    - **testbot** is created for staging and **nevabot**, **neva_agent** is for production, tokens of these bots are placed in **slack-integration.js**. please use them to run these bots
- *Your bot should be online! Within Slack, send it a quick direct message to say hi. It should say hello back!*
    - Sample Chat format
        - neva i need to format my disk
	- neva what is my timezone
	- neva how can i reset my password?
	- neva How can I buy music?
	- neva How can I clean my hard disk?
	- neva Can I print to a printer NOT USB connected directly to an Airport Extreme Base Station?
        - neva HT201659 I have a new bank card, how can I change the card details
        - neva HT201322 My slotomania app disappeared and I did not hide it. It shows installed but don't know where it's at.
        - neva QuickCam Pro 9000 for Mac
