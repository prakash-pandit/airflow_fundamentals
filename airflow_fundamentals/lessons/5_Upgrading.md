# Upgrading Airflow

1) Backup Airflow Metadata database
2) Check for deprecated features in the Dags

    2.1)    Pause all Dags
3) Upgrade Airflow by using 
```
<pip install "apache-airflow[any_extra]==2.0.1" --constraint constraint-file>
```
4) Upgrade the DB
```
<airflow db upgrade>
```