#discussion_apple_crawl

Overview
---------
Scrapy spiders to crawl data from Discussions Apple community and ingest crawled data into HBase table

Crawling process is divided in two steps: 
----------------------------------------
- Step1:DiscussionAppleCrawl.py: 
    - Crawls both base urls & pagination urls data into text files
- Step2:DiscussionAppleTextSpider.py:
    - It takes text file as input and ingest data into HBase table

Steps to Run Spiders:
--------------------
- git clone https://github.com/nevaai/data-ingestion.git
- cd data-ingestion/discussion_apple_crawl
- DiscussionAppleCrawl:
	- nohup scrapy crawl discussions1 > discussions1.log &
	- After execution of DiscussionAppleCrawl spider, we will have JSON objects of base urls and it's reply content pagination urls in text file (discussions1.log) 
    	- Example Base URL: https://discussions.apple.com/thread/7309088
    	- Example Pagination URL: https://discussions.apple.com/thread/7309088?start=15&tstart=0

- DiscussionAppleTextSpider: Data ingestion from text file into HBase is two steps	
	- scrapy crawl discussionAppleTextSpider -s TEXT_FILE=./discussions1.log  -s EXECUTION_TYPE=1 > textspider.log 2>&1 &
	- scrapy crawl discussionAppleTextSpider -s TEXT_FILE=./discussions1.log  -s EXECUTION_TYPE=0 > textspider.log 2>&1 &
	- Note: EXECUTION_TYPE IS EITHER 1 OR 0 { 1 - TO EXECUTIE BASE URLS/ 0 - TO EXECUTE PAGINATION URLS }
	- Note: nohup - run a command immune to hangups, with output to a non-tty
