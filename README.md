#  Stock Data Pipeline
Welcome to the Stock Data Pipeline project! This fully automated pipeline fetches the latest stock data for NASDAQ (NDAQ) from the Tiingo API, performs ETL (Extract, Transform, Load) transformations using a DataProc PySpark cluster, and loads the processed data into BigQuery. The entire process is seamless and requires no manual intervention, thanks to the use of automation scripts for infrastructure setup and execution on Google Cloud Platform (GCP).

## Technologies used
- Google Cloud Platform (GCP)
- Tiingo API
- DataProc
- BigQuery

##Requirements
-gcsfs
-fsspec
-pyspark
-pandas-datareader
-pandas
-google
-google-cloud
-python-dotenv

## How to Run
1.Tiingo API Setup:

Create an account on Tiingo to obtain API access for fetching stock data.

2.Service Account Setup:

Create a service account with BigQuery and DataProc Editor or Admin access.

Download the service account key in JSON format.

3.Environment Configuration:

Upload both the api key and service.json key files to the .env folder.

4.Run the Pipeline:

Trigger the GitHub Action through run-scripts.yml located in .github/workflows/run-scripts.yml.

## Architecture
                                +----------------+
                                |    Tiingo API  |
                                +----------------+
                                          |
                                          |
                                          |
                                          v
                                +----------------+
                                |                |
                                |   Fetch Latest |
                                |     Stock Data |
                                |                |
                                +-------+--------+
                                        |
                                        |
                                        |
                                        v
                          +-------------+------------+
                          |                          |
                          |     GitHub Repository    |
                          |                          |
                          +-------------+------------+
                                        |
                                        |
                                        |
                                        v
                    +-------------------+------------------+
                    |                                      |
                    |          GitHub Actions              |
                    |      (Automated ETL Pipeline)        |
                    |                                      |
                    +-------------------+------------------+
                                        |
                                        |
                                        |
                          +-------------v------------+
                          |                          |
                          |     DataProc PySpark     |
                          |                          |
                          +-------------+------------+
                                        |
                                        |
                                        |
                                        v
                           +--------------+-------------+
                           |                            |
                           |           BigQuery         |
                           |                            |
                           +--------------+-------------+
                                          |
                                          |
                                          |
                                          v
                                +----------------+
                                |                |
                                |   Processed    |
                                |   Stock Data   |
                                |                |
                                +----------------+


## Precautions
- Keep the bucket name same everywhere, if changing then then pay attention to worklfows.
- Keep api_key and service_account_key safe.






## Contributing
Feel free to contribute to this project by opening a pull request. For major changes, please open an issue first to discuss what you would like to change.

## Contact
For any queries or suggestions, please email me at tyagishreya2k388@gmail.com.
