# Interacting with Airflow

There are 3 ways to interact with Airflow:
* UI
* CLI
* REST API

Dag Views
- Tree view: the default DAG view
- Graph view: good to check dependencies and status of tasks for last run
- Gantt view: allows to analyze task duration and overlaps, perfect to spot bottlenecks and understand tasks that run in parallel 

If you want to see all the details of a Task across DagRuns, you can click on *"ALL INSTANCES"* button on the TASK Instance Context Menu

## Interacting with tasks

CLI commands to know:
```
docker exec -it {ID} /bin/bash #run container of web server
airflow db init #initialize airflow database and files
airflow db upgrade #upgrade metadatabase schema
airflow db reset 

airflow webserver #start UI
airflow scheduler #stop scheduler
airflow celery worker #start celery worker
```

```
airflow dags pause
airflow dags unpause
airflow dags trigger /-e
airflow dags list
airflow tasks list dag_id

airflow tasks test dag_id task_id yyyy-mm-dd #execute task independently of dependencies
airflow dags backfill -s start_date -e end_date --reset_dagruns example_dag #rerun past dag runs
```
