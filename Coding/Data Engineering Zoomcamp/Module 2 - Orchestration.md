https://github.com/DataTalksClub/data-engineering-zoomcamp/tree/main/02-workflow-orchestration#221----intro-to-orchestration
## What is orchestration?
Data orchestration is process of dependency management. Scheduling, triggering, monitoring. A form of automation
A sequential order of steps to carry out, using DAGs (Directed Acyclic Graphs), meaning graph with no cycles.

A good orchestrator handles:
- Workflow management
- Automation
- Error handling
- Recovery
- Monitoring, alerting
- Resource Optimization
- Observability
- Debugging 
- Compliance/Auditing

## What is Mage?
Mage is an orchestrator like Airflow without the complexity of Airflow
Hybrid approach - both GUI and code

Blocks = Airflow nodes

Following along: https://github.com/mage-ai/mage-zoomcamp
- Initial steps:
	- `git clone https://github.com/mage-ai/mage-zoomcamp.git mage-zoomcamp`
	- `cd mage-zoomcamp`
	- `docker compose build` to build the container
	- `docker compose up` to start the Docker container
	- Open `http://localhost:6789` in browser to view the image gui
- First make sure Postgres database is connected with mage. Add postgres credentials to .env file and do a SQL query on that database
	- Add dev profile in io_config.yml and copy and paste the postgres details. Add .env parameters like: "{{POSTGRES_DBNAME}}"
- Do an API request with whatever dataset (this uses NYC taxi data)
	- Load into csv via pandas
		- Create datatype schema
		- return pandas read csv
	- Create transform block
		- We loaded the data, now to transform the data to fit our needs
	- Query data in postgres to verify correct data and transformation
		- Select postgresSQL db and dev profile 
- Now let's configure GCP to connect with mage
	- Create GCS bucket
	- Create service account > get private key > copy that key into Mage project directory as json file
	- In Mage GUI, go to io_config.yml > edit Google variables and set path to path you saved credentials
	- Query bigquery to test connection
	- To test Google Cloud Storage > use built-in data loader for GCS. Add in your project and bucket names 
- ETL: API to GCS
	- Using a datalake (GCS) for storage solution
	- Blocks:
		- load api data
		- transform the data (clean it up)
		- Export the data (to GCS)
			- Load as 1 file
			- Or load as many: You can partition 1 file into a folder of files (by time), so that you can load the files in parallel instead of uploading 1 big monofile
- ETL: GCS to BigQuery
	- Process the data from data lake(gcs) to bigquery
	- Blocks
		- load data
		- transform the data
		- write the data to bigquery
	- To schedule this pipeline, add a Trigger. Can set the time, frequency, etc.
- Parameterized Execution
	- Example use: storing a file for each day.
	- Runtime variables
	- Either parameterize in python code or use Runtime Variables via Trigger settings
- BackFills
	- Backfilling pipelines
	- Say you need to rerun pipelines, in typical system, you need to build backfill pipeline simulating the exact days. This can be tricky
	- Using Backfills side panel option, you can backfill pretty easily
- Deployments Videos:
	- Deployment Prereqs
		- Terraform, gcloud cli, Mage Terraform templates
	- Google Cloud Permissions
		- Assign roles to the service account in IAM
	- Deploying to Google Cloud
		- When pushing to Git, sync with Mage, deploy
- Next steps

		


