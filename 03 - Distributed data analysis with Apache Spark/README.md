# Week 7: Intro to Spark

This is the first in a three-week introduction to Apache Spark series of
lectures and lab exercises.


## Getting started

The notebooks in this series will most easily be run on the IC Cluster. To set up your linux `PATH` and `PYTHONPATH` correctly, log in to your iccluster account and copy/paste the two commands below:

```
$ echo "export PATH=/opt/anaconda3/bin:$PATH" >> ~/.bash_profile
$ echo "export PYTHONPATH=/usr/hdp/current/spark2-client/python/lib/py4j-0.10.4-src.zip:/usr/hdp/current/spark2-client/python" >> ~/.bash_profile
```

To begin this week's exercises, make a fork of this repository in your own
namespace on gitlab and then clone the fork in your account on the iccluster:

```
$ git clone https://git-dslab.epfl.ch/<gitlab-username>/week7-intro-to-spark.git
```

```
$ git clone https://git-dslab.epfl.ch/<gitlab-username>/week8-spark-datasets.git
```

In the notebooks, you will see that some cells are fully runnable, while
others contain a comment that says `"TODO"` and/or some part of the cell
includes `<FILL>` -- this is your clue that you need to complete the cell
input to make it function properly.


### Starting notebooks

To start the notebook on the iccluster, type

```
$ pip install --user -r requirements.txt
$ jupyter notebook --ip 10.90.38.21
```

Browse to the clone of the repository and click on the `python-
refresher.ipynb` notebook.

If you close your browser window on accident and need to get back to your
notebook, you can find the currently-running notebook servers with:

```
$ jupyter notebook list
Currently running servers:
http://10.90.38.21:8889/?token=1234 :: /home/roskar
```

### Local setup

Due to problems with the iccluster over the past few days, the notebook for this week's exercise can be run locally on your laptop. Install Spark and the python dependencies yourself : 

* download spark from [here](https://www.apache.org/dyn/closer.lua/spark/spark-2.2.0/spark-2.2.0-bin-hadoop2.7.tgz)
* untar, e.g.

```
$ cd ~/
$ tar xvf PATH_TO_SPARK_TGZ_FILE .
```

Make sure you have python>3.5 installed. If not, try with Anaconda python.
The command below will install the requirements into your current python
environment -- if you prefer, you can set up a conda environment or a
virtualenv for the lab beforehand.

```
$ cd /path/to/week8-spark-datasets
$ pip install -r requirements.txt
```

Download the `gutenberg_cleaned_rdd.tar.gz` from
https://polybox.ethz.ch/index.php/s/rv4VTSmXvJhvq9B  and untar the archive in
the `data` subdirectory of the `week8-spark-datasets` repo.


### Starting notebooks locally

To start the notebook on your own machine, type

```
$ jupyter notebook
```

and open the link that appears at the bottom of the startup message.

Browse to the clone of the repository and click on the `language-
classification.ipynb` notebook.

If you close your browser window on accident and need to get back to your
notebook, you can find the currently-running notebook servers with:

```
$ jupyter notebook list
Currently running servers:
http://localhost:8889/?token=1234 :: /home/<username>
```

## Python refresher

We will continue using Python for this part of the course. Spark itself is
written in Scala, but can be used from Python and R. In order to use Spark
efficiently in Python, a few somewhat advanced Python concepts are useful.
You've already seen some of these in the earlier weeks of the course (list
comprehensions, lambda functions etc.), but unless you are a Python veteran it
is recommended that you warm up your python skills with the [`python-
refresher`](notebooks/1_python-refresher.ipynb) notebook found in this
repository. If you know what you are doing it shouldn't take more than a few
minutes. In any case, it's best to get some practice now and this notebook
will also serve as a reference for you as you work through the rest of the
lab.

## Intro to Spark

The notebook [`spark-intro.ipynb`](notebooks/2_spark-intro.ipynb) will guide you through some very basic Apache Spark concepts. This week and part of the next, we will be sticking to the "lower-level" RDD (Resilient Distributed Dataset) part of the Spark API, which will give you some insight into the way that distributed computation works. Next week we will also introduce the DataFrame API, which is the more user- friendly "higher level" interface to Spark that will feel somewhat like Pandas dataframes that you've worked with earlier in the course.


## Introducing the Gutenberg Corpus

The third notebook, [`gutenberg.ipynb`](notebooks/3_gutenberg.ipynb) will use basic Spark RDD methods to analyze a real-world text-based dataset. You will learn how to use some essential patterns that are very commonly used in Spark.

## Gutenberg text modelling

The final notebook, [`language-classification.ipynb`](notebooks/4_language-classification.ipynb) will guide you through the basics of Spark’s DataFrames.

## Useful links

At the very least, scan through these so you know what is available,
especially in the machine learning (ML) library and the API Reference docs.

General Spark docs: http://spark.apache.org/docs
Spark DataFrame intro (good for a lookup of basic syntax): http://spark.apache.org/docs/latest/sql-programming-guide.html
Spark DataFrame Reference: http://spark.apache.org/docs/latest/api/python/pyspark.sql.html
Spark ML Reference: http://spark.apache.org/docs/latest/api/python/pyspark.ml#pyspark-ml-package
