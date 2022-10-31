# Operators

- An operator is simply a TASK.
- Should have unique IDs inside of DAG / all other operators

**Idempotency** : Whenever the operator is executed with the same input we should get the same results. 

```from airflow.operators.XXX import ```

default_args = {dictionary}
Can be applied to DAG so that all tasks share the same common properties.
If you have default args applied to DAG and a specific argument assigned to a TASK, the latter takes precedence. 

## PythonOperator
```from airflow.operators.python import PythonOperator```
If you want to access the context inside of the PythonOperator, you can add the ****kwargs** to a python function. 

To add our custom arguments , you can add the ```op_kwargs``` to the Operator, then add a dictionary. 

## File Sensor
```from airflow.sensors.filesystem import FileSensor```

Waits for something to happen before proceeding to next task
Whenever you want to interact with an external system you have to create a new **connection** .
You can also define the *poke_interval* 

## Setting up Dependencies
- **Set downstream** will specify which task should be executed after
- **Set upstream** will specify which task should be executed before
- **chain** its the same as adding the >> between tasks 
- **cross_downstream** Can add cross dependencies between tasks. This is because you cant have >> between two lists. 