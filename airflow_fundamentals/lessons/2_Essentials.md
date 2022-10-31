# Essentials
## Why Airflow?
+ can handle complex differences between your tasks
+ is able to monitor tasks automatically
+ is able to retry them
+ is able to get warned if a task fails
+ has a user interface to manage all of your data pipelines
## What is Airflow?
Apache Airflow is an open source platform to programatically author, schedule and monitor workflows. 
* **It is an Orchestrator, not a Straming or Data Processing Framework**
* It is **Dynamic** (Python), **Scalable**, **Interacive** (CLI) and **Extensible** 

## Benefits:
+ data pipelines are dynamic (and coded in Python)
+ highly scalable
+ highly interactive
+ highly extensible

## Components
1) Web Server (UI interface)
2) Scheduler 
3) Metadata Database (must be compatible with SQLAlchemy)
* Executor (HOW - Celery, Kubernetes, Local, default: Sequential)
* Worker (Where my tasks are executed )

## Core Concepts

+ **DAGs** (data pipelines) or Directed Acyclic Graphs
+ **Operator**: task in a dag (a node in the graph)
    + Action operators (execute something)
    + Transfer operators
    + Sensor operators
+ **Task** (concrete instance of an operator)
+ **Dependencies** or relationships between operators (edges or arrows)
+ **Workflow** is the combination of tasks and dependencies

Whenever a Task is triggered, it is considered a *Task Instance*
Dependencies are set by "set_upstream" & "set_downstream" or using >><<