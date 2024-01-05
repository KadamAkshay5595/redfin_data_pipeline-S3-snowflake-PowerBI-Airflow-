# redfin__dataanalytics_data_engineering_project_

## Airflow [ Redfine --> AWS S3 --> Snowflake ] --> PowerBI 


## Overview

This project automates the ingestion, transformation, and analysis of real estate data from a website, providing a streamlined process for data-driven decision-making. The pipeline, orchestrated with Apache Airflow, utilizes Amazon S3 for storage, Snowflake as the data warehouse, and PowerBI for creating insightful dashboards.

## Project Structure

- **airflow/**: Contains Airflow DAGs and related configuration files.
- **scripts/**: Houses scripts for data transformation and additional processing.
- **snowflake/**: Includes SQL scripts for managing the Snowflake database schema.
- **powerbi/**: Stores PowerBI files for dashboard creation.
- **README.md**: Project overview and setup instructions.

## Requirements

- Python 3.x
- Apache Airflow
- AWS Account (for S3)
- Snowflake Account
- PowerBI Desktop (for dashboard editing)

## Setup

1. **Airflow Setup:**
    - Install AWS CLI on your server and configure the Access and secret keys there.
    - Install Apache Airflow: `pip install apache-airflow`
    - Configure Airflow settings in `airflow.cfg`.
    - Start Airflow webserver and scheduler: `airflow webserver -p 8080` and `airflow scheduler`.

2. **AWS S3 Setup:**
    - Create an S3 bucket for real estate data storage.
    - Configure AWS credentials on the machine running the pipeline.

3. **Snowflake Setup:**
    - Set up a Snowflake database and user with necessary permissions.
    - Update Snowflake connection details in Airflow DAGs.

4. **Event Trigger Setup:**
    - Configure event triggers to detect new data in the S3 bucket.
    - Triggers will automatically initiate Snowflake data ingestion.
    - after running necessary snowflake commands, copy sqs link after executing this command-  
       DESC PIPE redfin_database_1.snowpipe_schema.redfin_snowpipe;
    - attach this link in trigger.

5. **PowerBI Dashboard Setup:**
    - Import Snowflake data into PowerBI.
    - Design and customize the real estate dashboard using PowerBI Desktop.
    - Publish the dashboard to the Power BI service.

## Usage

1. **Airflow DAGs:**
    - Place DAGs in `airflow/dags`.
    - Manually trigger or schedule DAGs based on requirements.

2. **Snowflake Ingestion:**
    - Ensure event triggers detect new S3 data.
    - Snowflake automatically ingests new data on trigger.

3. **PowerBI Dashboard:**
    - Connect PowerBI Desktop to the Snowflake database.
    - Edit and customize the dashboard, then publish to the Power BI service.

## Contributing

Feel free to contribute through issues or pull requests. Please follow [contributing guidelines](CONTRIBUTING.md).

## License

This project is licensed under the [MIT License](LICENSE).
