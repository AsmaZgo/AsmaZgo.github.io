---
layout: post
title:  "A Recommander System Architecture Design"
date:   2023-06-01 10:34:25
categories: machine-learning feature
tags: featured
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.JPG
image2: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop_mobile.jpeg
---
# **A Recommander System Architecture Design**

As the second installment in a blog series on Machine Learning system design, I present a straightforward architecture for training and maintaining a recommender system tailored to video sharing platforms such as YouTube.

This problem of ML system design consists of two major building blocks:

1- Offline component: This component focuses on training and validating the recommender model.

2- Online component: This component is responsible for generating (inferring) recommendations in real-time.

![Figure 1- System architecture design](/assets/article_images/rec_sys_simple_design/sysdiag.png)

The initial offline training process follows the classic Data Science lifecycle, beginning with data collection and transformation into features, and concluding with model building and validation. The outcome of these steps is a dataset that captures the features and is stored in a feature store, along with a model that is persisted in a blob storage medium, such as a distributed file system like S3.

This article focuses specifically on the online component. In this subsystem, a user submits a request through a REST API, for instance. The request is then forwarded to an application server that encompasses the recommender functions. In our architecture, we propose utilizing a load balancer to provide increased scalability, performance, reliability, and redundancy to the service layer []. Scaling this layer horizontally enables us to handle requests from billions of users and deliver improved response times by minimizing throughput.

As depicted in the architecture, the recommender module consists of two components: (i) a content filtering algorithm that identifies relevant videos for each user based on their profile and historical viewing data, and (ii) a ranking algorithm that assigns scores to the recommended videos.

The techniques employed in content filtering can range from basic approaches, such as simple similarity matching, to more advanced methods involving deep neural network models. In this particular example, we focus on utilizing a model for the content filtering algorithm.

{% include disqus.html %}




