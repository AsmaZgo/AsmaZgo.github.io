---
layout: post
title:  "Spark Internals"
date:   2023-09-11 14:34:25
categories: databases feature
tags: featured
image: /assets/article_images/2014-11-30-mediator_features/night-track.JPG
image2: /assets/article_images/2014-11-30-mediator_features/night-track-mobile.JPG
---
# Spark Internals

Apache Spark is a cluster computing framework designed for managing and processing big data. It leverages commodity hardware to scale horizontally, enabling the processing of larger datasets.
Spark employs parallel processing and distributed computing techniques to ensure the efficiency of its data-driven applications. It was developed as a successor to MapReduce, specifically designed to overcome latency and efficiency limitations. Indeed, MapReduce tends to be slow due to its practice of storing intermediate results on disk. In contrast, Spark offers an API with concepts and data structures that enable it to execute data flows in memory, effectively minimizing resource-intensive I/O operations.
Distributed processing: Spark's architecture comprises a master node and worker nodes. The master node receives the workload from the driver program (the client) via the SparkContext defined in the application and orchestrates (/coordinates) the processing: It decomposes the workload into tasks and sends them to the worker nodes, who will take care of the execution. 

Cluster overview [1]

Parallelism: rdds and the api

talk about spark internals
spark 2 vs 3


{% include disqus.html %}
