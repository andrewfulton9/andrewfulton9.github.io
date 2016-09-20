---
layout: post
title:  "Path Specifications for Pyspark on Mac OSX"
date:   2016-09-20
author: Andrew Fulton
categories: Programming
tags:	Programming, Pyspark, Spark, Python
---

I recently began exploring spark a bit. Spark is really cool, and I have been enjoying learning more about it, but I found a couple of things annoying. First I couldn't run the pyspark shell outside of the spark directory, and second I couldn't run python files outside the spark directory without first going to the spark directory and typing `$ bin/spark-submit file.py`. In order to deal with this, I needed to alter my path in my .bash_profile so that I could 1) run the pyspark shell from any directory and 2) run a python file that used pyspark within any directory. Although I was able to figure out what to do for each thing seperately, I couldn't find anywhere that helped me figure out the paths to do both in one place so I thought that I would write what I did here for someone else trying to figure it out in the future.

First I had to set the path for spark:
```
export SPARK_HOME="/Users/[user]/spark-2.0.0-bin-hadoop2.7"
```

Next, I set my path for running python files with pyspark in any directory:
```
export PYTHONPATH=$SPARK_HOME/python:$SPARK_HOME/python/build:$PATH
```

Finally, I set my path to run the pyspark shell from any directory
```
export PATH=$SPARK_HOME/bin:$PYTHONPATH
```

That's it! All in all it was a pretty easy task. I hope this helps!
