# Executors
There are several executor types
- **LocalExecutor** Used for a single node Architecture. Used with other DBs such as Postgres
- **Celery Executor** Executes on Celery Cluster (multiple machines). You need a Queue component (like Redis/RabbitMQ), then run the airflow celery worker on each of the Worker machines. 
- **Kubernetes Executor**
- **Sequential Executor** depends on SQLite , default 

To understand which executor is being used you need to run the container and open it’s command line 
```
docker ps
# copy the corresponding id as container_id
docker exec -t container_id /bin/bash

# inside the container
grep executor airflow.cfg

grep sql_alchemy_conn airflow.cfg
```

- There is always a QUEUE behind each executor

## Concurrency and parameters

### Airflow instance level:
- parallelism: 32 - amount of tasks that can be executed in parallel in the entire airflow instance
- dag_concurrency: 16 - number of tasks for a given DAG that can be run in parallel per DAG 
- max_active_dag_runs_per_dag : 16 

### DAG object level:

- max_active_runs : 6 - number of dag runs that can run in parallel 
- concurrency: 1 - number of tasks to run in parallel for a specific dag
