# Scheduling

The most important part of scheduling a DAG are the :
* START DATE
* SCHEDULE INTERVAL

## Schedule Interval
If you want to only trigger manually, then specify S.I. to *None*

The CRONTAB is specified in
**MINUTES / HOURS / DAYS(MONTHS) / MONTHS / DAYS(WEEK)**

You can use the timedelta option

By using Cron expression, at the end of month there might be some problems. 
Example: If you want to run every three days its recommended to use timedelta

## Backfill & Catchup
Depends on the current date, you can use the DAYS_AGO option

You can limit the number of DagRuns by setting up the **max_active_runs** parameter.

If you want to run backfill manually, you can do it via the CLI:  ```airflow dags backfill```