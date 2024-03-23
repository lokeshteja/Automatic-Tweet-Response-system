# Automated Tweet Response System

This project offers an advanced solution for Twitter customer support, combining real-time data streaming, machine learning, and automated ticket generation, enhancing the efficiency of customer service.

## Key Features

- **Real-Time Tweet Processing**: Utilizes Spark Streaming for instantaneous tweet analysis to reduce response times.
- **Intelligent Complaint Analysis**: Employs a two-stage ML process:
  - Sentiment analysis to assess user sentiment.
  - Complaint classification into categories like billing or technical issues.
  - Named Entity Recognition (NER) model to extract entities like location from tweets.
- **Automated Ticketing**: Creates support tickets and routes them based on analysis results.
- **Data Storage**: Archives processed data in a data lake for in-depth future analysis and prompt issue resolution.

## Project Structure

- **Engines**: Houses ML models and the core processing logic.
- **Helpers**: Assists with text preprocessing, model evaluation, API interactions, and Twitter communications.

## Technologies Used

- Spark Streaming for real-time data ingestion.
- Machine Learning Libraries (e.g., Scikit-learn, PyTorch, TensorFlow).
- Kafka for message queueing and handling.
- Twitter API for data stream integration.
- Data Lake solutions for scalable storage.
- Finally Deployed this in AWS
<!-- 
## Getting Started

### Prerequisites

*(List of prerequisites and configurations for the project setup.)*

### Installation

*(Step-by-step guide on setting up and running the project.)*
-->
## How It Works

1. Tweets are captured in real-time via streaming.
2. Sentiment analysis evaluates user emotions within the tweets.
3. The complaint is categorized by the classification model.
4. NER model extracts relevant entities from the tweet content.
5. Tickets are generated and routed based on the analysis.
6. Data is stored for strategic insights and effective problem resolution.

**Workflow Diagram**

![image](https://github.com/lokeshteja/Automatic-Tweet-Response-system/assets/28762945/98f26e52-a3e4-40e0-b329-9faccc46369b)

## Potential Applications

Ideal for sectors with high volumes of social media traffic, such as:

- Customer Support Centers
- E-commerce Platforms
- Tech Corporations
- Airlines & other Travel Agencies 

