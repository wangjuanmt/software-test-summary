# Performance-Test
We have different levels of performance test: database level, API level, and system level.

## MySQL Performance Test
MySQL test (db level) is the bottom and fundamental of the system.
In this part, we will focus on the performance of MySQL server self.
Requests and processes all happen in the server.
We can take this server for a independent-system and this test for no-dependency test.

### Key Metric
* IOPS (Input/Output operations Per Second)
* QPS (Query Per Second)
* TPS (Transaction Per Second)
* CPU/MEM Consuming

Because IOPS is a fixed data once hardware(disk) is fixed, we will not explore IOPS value here.
The other 3 will be concerned.

### Test Method and Tools
#### Load Generator
Use the following command which is along with MySQL. No need install.
`mysqlslap -h localhost –u user –p password --query="select * from iaas.subscriber" --number-of-queries=100000 -c 30 -i 10 --create-schema=iaas`

Tips:
--number-of-queries: Number of queries (load)

-c, -concurrency: number of virtual users , concurrency

-I, --iterations: iteration numbers

#### QPS Monitoring
Use the following command which is along with MySQL. No need install.

`mysqladmin -h localhost -u user –p password extended-status -r -i 1 |grep "Questions"`

Attention: Please use the correct MySQL user and password to replace the charactors of “user” and “password” in command lines above.
#### TPS Monitoring
Use the following command. No need install.
`iostat vda2 1`
#### CPU/MEM Consuming Monitor
Use the following command. No need install.
`top`

## API Performance Test
It is not easy to find tools which can generate load and monitor results at api level.
We will use a tool named JMeter deployed at a LAN (local area network) environment with the target server.

### Key Metric
* Response Time
* Throughput
* Error%
* CPU/MEM Consuming (API Server)
* Disks I/O (API Server)

### Test Method and Tools
#### Load Generator
JMeter  Thread and HTTP Request Sample
The Apache JMeter™ application is open source software, a 100% pure Java application designed to load test functional behavior and measure performance. It was originally designed for testing Web Applications but has since expanded to other test functions.
The offical website is http://jmeter.apache.org/index.html .
#### Response Time, Throughput and Error% Monitor
JMeter Aggregate Report, in JMeter Listener, no need install.
#### CPU/MEM and Disks I/O Monitor
PerfMon Metrics Collector. Need install JMeterPlugins-Standard (the latest version is JMeterPlugins-Standard-1.3.0.zip) and ServerAgent (the latest version is ServerAgent-2.2.1.zp), for more information, view http://jmeter-plugins.org/ .

