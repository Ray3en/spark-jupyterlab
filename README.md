Author (https://github.com/cluster-apps-on-docker/spark-standalone-cluster-on-docker)

***
## Spark Local
Spark is running in local mode on your machine.

1. Git clone this repo
```bash
git clone git@github.com:Ray3en/spark-jupyterlab.git
```
2. Download datasets
```bash
cd spark-jupyterlab/build/workspace && \
mkdir -p data && \
curl -L -o data/orders.csv "https://huggingface.co/datasets/Ray3en/synthetic_clients_dataset/resolve/main/users_data.csv?download=true"
```

3. Install pyspark and Jupyter Lab
```bash
pip install pyspark jupyterlab
```

4. Start Jupyter Lab
```bash
jupyter lab
```

5. Open **spark.ipynb** in Jupyter Lab

- [Spark Notebook](build/workspace/spark.ipynb)

***
❌ **If you encounter the following error when running PySpark:**
```
RuntimeError: Python in worker has different version 3.12 than that in driver 3.10, PySpark cannot run with different minor versions. Please check environment variables PYSPARK_PYTHON and PYSPARK_DRIVER_PYTHON are correctly set.
```
✅ **Solution**

You can do this by adding the following code snippet at the beginning of your PySpark script or notebook:
```python
import os
import sys

os.environ['PYSPARK_PYTHON'] = sys.executable
os.environ['PYSPARK_DRIVER_PYTHON'] = sys.executable
```

***
## Spark Cluster
**Spark Cluster with 4 executors**

Run docker-compose
```Dockerfile
docker-compose up -d
```

Run your spark cluster here

- [Spark Notebook](build/workspace/spark.ipynb)

Review the out-of-memory and spill cases in Spark
- [Spark Notebook 2](build/workspace/spark_oof_spill.ipynb)

