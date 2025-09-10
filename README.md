# NYC Taxi Data Analytics & Prediction Platform
An end-to-end serverless data platform on AWS for processing, analyzing, and predicting NYC taxi trip data.

## Description
This project demonstrates a complete, professional data engineering and machine learning workflow on the cloud. It ingests millions of NYC taxi trip records, processes them in a serverless environment, and makes the data available for analytics. The platform culminates in the development of a machine learning model to predict trip durations and an interactive dashboard for visualizing key business metrics. This project was built to showcase a modern, scalable, and automated data architecture using Infrastructure as Code (IaC) and CI/CD principles.

## Tech Stack
Cloud Provider: AWS

Infrastructure as Code: Terraform

Containerization: Docker

CI/CD: GitHub Actions

Core AWS Services:

- Storage: S3 (Data Lake)

- Compute: Fargate on ECS (Serverless Container Orchestration)

- Analytics: Athena (Serverless SQL Query Engine)

- Container Registry: ECR

- Permissions: IAM

Programming & Data Science:

- Language: Python

- ETL & Manipulation: Pandas

- Machine Learning: Scikit-learn

- Cloud SDK: Boto3

Dashboarding: Jupyter Notebook, Matplotlib, Seaborn

## Features
Automated Infrastructure: The entire cloud infrastructure is defined as code using Terraform, allowing for repeatable and version-controlled deployments.

Serverless ETL Pipeline: A containerized Python script running on AWS Fargate performs the ETL process, transforming raw Parquet files into a clean, analytics-ready format.

CI/CD Automation: A GitHub Actions workflow automatically deploys infrastructure changes and publishes new container images on every push to the main branch.

Interactive Data Analysis: An interactive Jupyter Notebook connects directly to AWS Athena to perform exploratory data analysis using standard SQL.

Predictive Modeling: A linear regression model is developed with Scikit-learn to predict taxi trip durations based on features like distance, fare, and passenger count. The project also demonstrates how to prepare this model for scalable training with Amazon SageMaker.

Setup & Local Execution
To clone and run this project locally, you will need the following prerequisites:

An AWS Account with credentials configured locally.

Terraform installed.

Docker Desktop installed and running.

Python 3.9+ and pip installed.

## Instructions:

Clone the repository:

git clone [https://github.com/YOUR_USERNAME/nyc-taxi-platform.git](https://github.com/MarshallWilliams1/taxi.git)
cd taxi

Deploy the AWS Infrastructure:

cd terraform
terraform init
terraform apply -auto-approve
cd ..

Run the ETL and Analysis Notebook:

Install Python dependencies:

pip install -r requirements.txt

Start the Jupyter server:

jupyter lab

Open analysis.ipynb in your browser and run all cells.

## Screenshots & Demos
Rider Demand Hotspots
This chart shows the top 20 taxi pickup locations in NYC, providing clear insights into areas with the highest demand.

<img width="1064" height="747" alt="image" src="https://github.com/user-attachments/assets/07759b48-129b-4af0-bf6c-55fbe483f939" />


Fare & Trip Duration Analysis
These charts break down the most common fare brackets and show how average trip duration changes throughout the day, highlighting the impact of rush hour.

<img width="908" height="599" alt="image" src="https://github.com/user-attachments/assets/820e6862-3945-4155-985b-74bab27d4ae0" />

Machine Learning Prediction
The trained Scikit-learn model in action, predicting the duration for a new, hypothetical trip.

<img width="461" height="118" alt="image" src="https://github.com/user-attachments/assets/a234deb7-477f-4c3b-94b8-5c1ee0f15da4" />


More Images

<img width="1056" height="599" alt="image" src="https://github.com/user-attachments/assets/b112fc31-9674-43a4-89bb-9b3857eef7b3" />

<img width="655" height="707" alt="image" src="https://github.com/user-attachments/assets/98bdf3ef-fb96-4c8a-afe1-d17ccf31c9c8" />

<img width="565" height="476" alt="image" src="https://github.com/user-attachments/assets/448e3c19-9aa2-4f9e-be1f-f42a387d03da" />


## Future Work
Deploy Model to SageMaker Endpoint: Take the trained Scikit-learn model and deploy it to a real-time SageMaker Endpoint. This would provide a REST API for applications to get live trip duration predictions.

Automate Fargate Job Trigger: Implement an S3 event trigger with AWS Lambda. When a new raw data file is uploaded, the Lambda function would automatically start the Fargate ETL task, making the entire pipeline event-driven.
