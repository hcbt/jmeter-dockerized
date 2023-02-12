# **JMeter-test**

This repository includes docker-compose for running JMeter inside a docker container together with Grafana and InfluxDB for visualization and monitoring of JMeter test data.

## **Requirements**

* Docker

## **Usage**

Simply run

```shell
docker-compose up -d
```
and enjoy.

Grafana dashboard can be accessed on [localhost:3000](http://localhost:3000/d/b4kP_KoMz/jmeter-load-test-org-md-jmeter-influxdb2-visualizer-influxdb-v2-0?orgId=1)

## **How it works**

### **Test plan**

Default test plan (test-plan.jmx) includes a single HTTP sampler. Different test plan can be set inside .env file.

### **Environment**

Things like name of test plan, number of threads, hostname, port number etc. are read from .env file which is passed to docker-compose for setting env variables. JMeter accepts user defined variables setting from commandline so whatever is stored in .env file can be passed to JMeter through docker-compose.

### **Statistics**

This repo uses [JMeter InfluxDB v2.0 listener plugin](https://github.com/mderevyankoaqa/jmeter-influxdb2-listener-plugin) for storage of JMeter test results in InfluxDB database for easier access to the data. The plugin makes it easier to visualize test data using grafana as well.


## **Resources used**

* [JMeter InfluxDB v2.0 listener plugin](https://github.com/mderevyankoaqa/jmeter-influxdb2-listener-plugin)
* [docker-jmeter](https://github.com/justb4/docker-jmeter)
* [JMeter Load Test Grafana dashboard](https://grafana.com/grafana/dashboards/13644-jmeter-load-test-org-md-jmeter-influxdb2-visualizer-influxdb-v2-0-flux/)