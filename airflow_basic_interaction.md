---



typora-copy-images-to: img
---



# Interacting with apache airflow


## UI 

- Main interface
- Views: 
  - Tree: dag runs (circles) / tasks (squares). Spots **all Dags** status
  - Graph View: Check **dependencies** and relations of the data pipeline
  - Gantt View: Analyze tasks durations / overlapping (parallel). Evaluate bottlenecks
- Task Instance Context Menu
  - Instance details: dag_id, end_data, ...
  - Rendered: What is the output
  - Log: See logs of the task. Outputs, success or fail
  - All Instances: See all instances that have been created. 
  - Actions: 
    - Run: not allowed in local executor
    - Clear: Restart the task (retry)
    - Mark failed or success: experiments

  
  
- REST APIs: build something on top of airflow
  - other tools that need to interact with airflow

## CLI Commands

CLI commands: useful in special cases.

- test tasks, initialize, upgrade



Connect to Docker container in a airflow instance

```bash
docker ps
docker exec -it <id_container_web_server> /bin/bash

now at the astro user
(initialize)
airflow db init 

airflow db upgrade

airflow db reset (not use in production)

airflow webserver (start webserver)

airflow scheduler

airflow celery worker

airflow dags pause/unpause

airflow dags trigger

aiflow dags list(the new file is there?)

aiflow dags list <dag> (lists all tasks)

airflow tasks test <dag_id> <task_name> <date> yyyy-mm-dd (VERY IMPORTANT, ALWAYS USE)

airflow dags backfill -s <start_date> -e <end_date> --reser_dagruns (useful to rerun past dag runs)

```



![image-20220309224228386](E:\Dropbox\Profissional\formacao\data_engineer\airflow\img\image-20220309224228386.png)

## REST APIs

[See documentation here](https://airflow.apache.org/docs/apache-airflow/stable/stable-rest-api-ref.html)

- build something on top of airflow / other tools that need to interact with airflow

