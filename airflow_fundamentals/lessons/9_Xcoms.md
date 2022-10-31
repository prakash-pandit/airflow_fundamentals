# XCOM Cross Account Communications
Inside a Python function, you can just use the RETURN

- **ti.xcom_pull(keys='return_value', task_ids=['task_name'])**
- **ti.xcom_push(key='my_key', task_ids=['task_name'])**

Different airflow metadatabase databases allow different amounts of data to be shared in XCom. 

SQLite : up to 2GB
Postgress: 1GB
Mysql: 64kb
