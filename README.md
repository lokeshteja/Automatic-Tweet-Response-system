# Airline Twitter Support

Twitter Customer Support is a flexible, scalable, and highly impactful solution built with a combination of data science and big data tools. User tweet data will be streamed in real-time using spark streaming. Data is then parsed through a two-level ML algorithm to finally get classified into the complaint category and a support ticket is auto-generated according to the complaint class. 

### Data Flow

Data Flows from one system to other, enriching via Deep Learning algorithm embedded as a UDF to Spark Streaming.

Hierarchy is as follows: 
 
1) Twitter
2) Kafka Topic
3) Spark Streaming
4) ML Model 1 (Sentiment Analysis)
5) ML Model 2 (Complain Classification)
6) API Call to generate Ticket
7) Sinking to Data Lake (Parquet / Kafka / Others)


## Code Overview

### Part 1: Engines



    File Name : Enginer_BinaryClassifier.py
    File Description : File to train and infer sentiment analysis
    
    File Name : Enginer_MulticlassClassifier.py
    File Description : File to train and infer Complain classification
    
    File Name : Enginer_Kafka.py
    File Description : File to push tweets to kafka topic
    
    File Name : Enginer_NER.py
    File Description : File to train and infer Name Entities

    File Name : Enginer_SparkJob.py
    File Description : Main file to create Spark job and embedded using UDF
    
    
### Part 2: Helpers

    
    File Name : BinayInference.py
    File Description : Helper class to infer sentiment analysis
    
    File Name : Evaluate.py
    File Description : Helper class to evaluate model performance
    
    File Name : ModelStruct.py
    File Description : Helper class to structure models and save it
    
    File Name : MulticlassComplainInference.py
    File Description : Helper class to infer complain classes
    
    File Name : NameEntityInference.py
    File Description : Helper class to infer name entities
    
    File Name : Preprocess.py
    File Description : Helper class to preprocess text
    
    File Name : References.py
    File Description : Helper class for all the constants and URL
    
    File Name : ReplyTweets.py
    File Description : Helper class to reply to tweets
    
    File Name : RequestParams.py
    File Description : Helper class to send request to API
    
    File Name : TweetsListener.py
    File Description : Helper class to structure twitter input
    
    File Name : TwitterAuth.py
    File Description : Helper class to authenticate twitter app
    
    File Name : TwitterStreamer.py
    File Description : Helper class to stream tweets
    
    File Name : WordEmbedding.py
    File Description : Helper class to convert text to sequences



## AWS Commands

Commands to setup aws kafka and submit spark job

- `sudo apt update` : upate packages

- `sudo apt install default-jdk ` : install jdk

- `sudo wget https://packages.confluent.io/archive/5.5/confluent-5.5.0-2.12.tar.gz` : Download confluent kafka

- `sudo tar xvzf confluent-5.5.0-2.12.tar.gz ` : Extract package

- `sudo vi /etc/profile` : Set env variable

- `export PATH=/home/ubuntu/confluent-5.5.0/bin:$PATH` : paste this to profile

- `source /etc/profile` : Run the file

- `echo $PATH` : check if path is correct

- `/home/ubuntu/confluent-5.5.0/bin/confluent-hub install --no-prompt confluentinc/kafka-connect-datagen:0.1.0` : Install hub

- `/home/ubuntu/kafka/kafka/confluent-5.5.0/bin/confluent start` : Start the env

- `confluent local start` : Start env

- Filezilla to copy code

- install Requirement.txt

- `spark-submit --packages org.apache.spark:spark-sql-kafka-0-10_2.12:3.1.2 --py-files MLPipeline.zip  Engine_SparkJob.py localhost 9999` : Sample Spark Submit

