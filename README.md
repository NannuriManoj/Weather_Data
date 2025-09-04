 # Weather Dashboard - Save Weather Data to AWS S3

This is a Python application that:

Fetches current weather data from the OpenWeather API.

Ensures an Amazon S3 bucket exists (creates it if not).

Saves weather data as JSON files in your S3 bucket with timestamps.

## Features

Fetches live weather for one or more cities.

Stores results in Amazon S3.

Automatically creates the S3 bucket if missing.

Adds a timestamp to each file for unique storage.

## Requirements

Python 3.8+

AWS Account with an IAM user that has S3 permissions.

OpenWeather API key (free signup at OpenWeather).

## Setup Instructions

Make a project folder and move your script there.
Example structure:

weather-app/
├── src/
│   └── weather.py       # Your Python script
├── .env                 # Store API keys and AWS details here
└── requirements.txt     # Python dependencies


## Install dependencies:
Create a requirements.txt file with the following:

boto3
requests
python-dotenv


## Then run:

pip install -r requirements.txt


## Set up environment variables
Create a .env file in the project root:

OPENWEATHER_API_KEY=your_openweather_api_key_here
AWS_BUCKET_NAME=your-s3-bucket-name
AWS_REGION=ap-south-1


 Bucket name rules: must be all lowercase, no spaces, and globally unique (example: weather-bucket-09032025).

Configure AWS credentials
Run:

## aws configure


Enter your AWS Access Key, Secret Key, Region, and Output format.

Running the Application

From the root folder, run:

python src/weather.py


## Example output:

Bucket weather-bucket-09032025 not found, creating...
Successfully created bucket weather-bucket-09032025 in ap-south-1

Fetching weather for Hyderabad...
Temperature: 81.16°F
Feels like: 83.73°F
Humidity: 63%
Conditions: overcast clouds
Successfully saved data for Hyderabad to S3


Your S3 bucket will now contain files like:

weather-data/Hyderabad-20250903-120045.json
