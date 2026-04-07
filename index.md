---
layout: default
title: OpenRAG Docs
---




# OpenRAG Docs

Welcome to the documentation.


Ray Dashboard
Ray provides a web-based dashboard for monitoring and debugging Ray applications. The visual representation of the system state, allows users to track the performance of applications and troubleshoot issues.


Set up Dashboard
To access the dashboard, use ray[default] or other installation commands that include the Ray Dashboard component. For example:

pip install -U "ray[default]"
When you start a single-node Ray Cluster on your laptop, access the dashboard with the URL that Ray prints when it initializes (the default URL is http://localhost:8265) or with the context object returned by ray.init.

import ray

context = ray.init()
print(context.dashboard_url)
127.0.0.1:8265
INFO worker.py:1487 -- Connected to Ray cluster. View the dashboard at 127.0.0.1:8265.
Note

If you start Ray in a docker container, --dashboard-host is a required parameter. For example, ray start --head --dashboard-host=0.0.0.0.

When you start a remote Ray Cluster with the VM Cluster Launcher, KubeRay operator, or manual configuration, Ray Dashboard launches on the head node but the dashboard port may not be publicly exposed. View configuring the dashboard for how to view Dashboard from outside the Head Node.

Note

When using the Ray Dashboard, it is highly recommended to also set up Prometheus and Grafana. They are necessary for critical features such as Metrics View. See Configuring and Managing the Dashboard for how to integrate Prometheus and Grafana with Ray Dashboard.

Navigate the views
The Dashboard has multiple tabs called views. Depending on your goal, you may use one or a combination of views:

Analyze, monitor, or visualize status and resource utilization metrics for logical or physical components: Metrics view, Cluster view

Monitor Job and Task progress and status: Jobs view

Locate logs and error messages for failed Tasks and Actors: Jobs view, Logs view

Analyze CPU and memory usage of Tasks and Actors: Metrics view, Cluster view

Monitor a Serve application: Serve view

Jobs view

The Jobs view lets you monitor the different Jobs that ran on your Ray Cluster. A Ray Job is a Ray workload that uses Ray APIs (e.g., ray.init). It is recommended to submit your Job to Clusters via Ray Job API. You can also interactively run Ray jobs (e.g., by executing a Python script within a Head Node).

The Job view displays a list of active, finished, and failed Jobs, and clicking on an ID allows users to view detailed information about that Job. For more information on Ray Jobs, see the Ray Job Overview section.

Job Profiling
You can profile Ray Jobs by clicking on the “Stack Trace” or “CPU Flame Graph” actions. See Profiling for more details.

Task and Actor breakdown

