# Task Lifecycle
* Whenever a Task is triggered, it is considered a *Task Instance*
* Dependencies are set by "set_upstream" & "set_downstream" or using >> <<

## How does a Task gets executed
1) First you create a new dag in the dags folder
2) The WebServer parses Dag (default every 30 seconds)
3) The Scheduler parses Dag (default every 5 mins)
4) If Dag is ready to be executed, the Scheduler creates a DagRun object (instance of my Dag) and passes it to the metastore
5) The Scheduler creates a new TaskInstance object (Scheduled)
6) Scheduler sends Task Instance into the Executor (Queued)
7) Executor Sends Task Instance and sends it to a Worker
8) Executor updates status of task to Metastore to Running / Success / Failed
9) Scheduler checks if there are any more tasks in the DagRun 
10) Webserver updates status by fetching it from the MetaStore.

## Task Instance Status
0) No Status
1) Scheduled
2) Queued
3) Running
4) Success / Failed