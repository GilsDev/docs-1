---
title: 'View Scheduler Logs'
sidebar_label: 'Scheduler Logs'
id: scheduler-logs
description: View your Deployments' Airflow Scheduler logs in the Astronomer Cloud UI.
---

## Overview

Astronomer Cloud exposes your Airflow Deployment's Scheduler logs in the **Scheduler Logs** page of the Astronomer UI. While Airflow task logs available in the Airflow UI are most critical to common troubleshooting, errors specific to the Scheduler component are often helpful to understand task failures.

This guide explains how to access your Deployments' Scheduler logs via the Astronomer Cloud UI. For more information about viewing component logs in a local Airflow environment, see [Access Airflow Component Logs](test-and-troubleshoot-locally.md#access-airflow-component-logs). For Deployments on Astronomer Cloud, logs for the Airflow Webserver, Workers, and Triggerer are not available.

## Access Scheduler Logs

You can access the **Scheduler Logs** page clicking the Logs icon in the Astronomer UI sidebar:

![Logs icon and button](/img/docs/log-location.png)

You can also directly access logs for a given Deployment by clicking the Logs icon in the Deployments table or on the Deployment's information screen.

![Logs icon in the Deployments table](/img/docs/deployment-log-button.png)

## Filter Scheduler Logs

The **Scheduler Logs** page shows all of a given Deployment's recorded Scheduler logs from the last 24 hours. If the Deployment generated more than 500 logs in the last 24 hours, then the UI shows only the most recent 500 logs. Each log is color-coded based on its log level.

At the top of the page, you can filter the types of logs which appear by selecting them from the dropdown log level menu. The log levels you can filter by are:

- `ERROR`: Emitted when a process fails or does not complete. For example, these logs might indicate a missing DAG file, an issue with your Scheduler's connection to the Airflow database, or an irregularity with your Scheduler's heartbeat.
- `WARN`: Emitted when Airflow detects an issue that may or may not be of concern but does not require immediate action. This often includes deprecation notices marked as `DeprecationWarning`. For example, Airflow might recommend that you upgrade your Deployment if there was a change to the Airflow database or task execution logic.
- `INFO`: Emitted frequently by Airflow to show that a standard Scheduler process, such as DAG parsing, has started. These logs are frequent but can contain useful information. If you run dynamically generated DAGs, for example, these logs will show how many DAGs were created per DAG file and how long it took the Scheduler to parse each of them.

![Log filtering menu in Scheduler Logs page](/img/docs/filter-logs.png)

To view a different Deployment's logs, click the name of the current Deployment and select a new Deployment from the dropdown menu that appears:

![Select Scheduler logs menu](/img/docs/select-deployment-logs.png)