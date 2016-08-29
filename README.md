##  support_apple_data

Overview
---------
- We used 80 legs to crawl support.apple.com and saved the corpus in S3:

    ``` 
    s3://neva-knowledge-base/support.apple/raw_data_files/1-200.zip
    s3://neva-knowledge-base/support.apple/raw_data_files/201-400.zip
    s3://neva-knowledge-base/support.apple/raw_data_files/401-600.zip
    s3://neva-knowledge-base/support.apple/raw_data_files/601-774.zip
    ```

CleanAppleSupportDocs.py:  
------------------------
```
git clone https://github.com/nevaai/data-ingestion.git
cd support_apple_data
mkdir raw_data_files
mkdir cleaned_data_files
- cd raw_data_files
- Download the above files from s3 and extract here
- cd ..
./clean.sh ./raw_data_files/1-200 ./cleaned_data_files
./clean.sh ./raw_data_files/201-400 ./cleaned_data_files
./clean.sh ./raw_data_files/401-600 ./cleaned_data_files
./clean.sh ./raw_data_files/601-774 ./cleaned_data_files
```

IngestAppleSupportDocs.py
-------------------------
- cd support_apple_data
- Modify "baseurl" property points to HBase Rest server in IngestAppleSupportDocs.py
    - Example: baseurl = "http://172.31.19.25:20550"
- Create HBase table using below command:
    - HBase shell <<< "create 'support.apple.com','pageInfo'"
    - Modify "table_name" property points to newly created HBase table in IngestAppleSupportDocs.py
    - Example: table_name = "support.apple.com"
- ./ingest.sh ./cleaned_data_files
