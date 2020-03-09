# Airflow Prometheus Exporter

[![Build Status](https://travis-ci.org/robinhood/airflow-prometheus-exporter.svg?branch=master)](https://travis-ci.org/robinhood/airflow-prometheus-exporter)

The Airflow Prometheus Exporter exposes various metrics about the dags and scheduler which helps improve the observability of an Airflow cluster.

The exporter is based on this [Prometheus Exporter for Airflow](https://github.com/epoch8/airflow-exporter).

## Requirements

The plugin has been tested with:

- Airflow >= 1.10.4
- Python 3.6+

## Installation

The exporter can be installed as an Airflow Plugin using:

```
$ pip install airflow-prometheus-exporter
```

This should ideally be installed in your Airflow virtualenv.

## Metrics

Metrics will be available at

`http://<your_airflow_host_and_port>/admin/metrics/`

#### `airflow_dag_status`

Number of dag run states for the current hour

All the possible states are listed [here](https://github.com/apache/airflow/blob/master/airflow/utils/state.py#L59).

#### `airflow_dag_run_duration`

Duration of successful dag runs in seconds

#### `airflow_dag_schedule_delay`

Airflow dag schedule delay in seconds

The schedule delay is measured as the difference between a dag's planned and actual start dates.
