---



typora-copy-images-to: img
---



# Windows

## Docker installation



## Astrocloud CLI Installation

https://docs.astronomer.io/astro/install-cli/



1. ```powershell
   mkdir my-project && cd my-project
   ```

2. ```text
   Invoke-WebRequest -Uri https://goreleaserdev.blob.core.windows.net/goreleaser-test-container/releases/v1.3.1/cloud-cli_1.3.1_Windows_x86_64.tar.gz -o astrocloudcli.tar.gz
   ```
3. ```sh
   tar -xvzf .\astrocloudcli.tar.gz
   ```



4. To run the executable without specifying its file path, save `astrocloud.exe` in a secure location on your machine and add its filepath in the Windows PATH environment variable. For more information about configuring the PATH environment variable, read [Java documentation](https://www.java.com/en/download/help/path.html). 
5. I.E. create  a folder at C: \airflow\  and put the astrocloud.exe and save on the WINDOWS PATH





## Run Commands



```bash
astrocloud dev init (cria ambiente)

astrocloud dev start (inicia)

->components will run

astrocloud dev ps 
-> evaluate process
```



Airflow Webserver: http://localhost:8080
Postgres Database: localhost:5432/postgres
The default Airflow UI credentials are: admin:admin
The default Postrgres DB credentials are: postgres:postgres



##  Update installation

1-change dockerfile 

```bash
FROM quay.io/astronomer/astro-runtime:4.2.0
```

**update installatio

Terminal -> restart

```bash
astrocloud dev stop && astrocloud dev start
```



## Local pip installation

if you do not have python or anything else installed follow the Python environment installation



**pip install apache-airflow --constraint**

```bash
pip install apache-airflow --constraint
https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt
```

ex:  *constraints*-1.10.7/*constraints*-3.7

https://raw.githubusercontent.com/apache/airflow/constraints-2.2.2/constraints-3.9.txt

(latest 10/04/2022)

https://raw.githubusercontent.com/apache/airflow/constraints-2.2.5/constraints-3.9.txt

pip install apache-airflow --constraint https://raw.githubusercontent.com/apache/airflow/constraints-2.2.2/constraints-3.9.txt



## Python Environment

We start by downloading a windows installer from miniconda

1-open the anaconda bash

```bash
conda init bash
```



2-install vscode, and look for python interpreters



3- create an env for airflow

```py
conda create --name airflow_env python=3.9
```
