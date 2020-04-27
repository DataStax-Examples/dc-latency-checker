# Data Center Latency Checker
This a simple program that can be run to check the difference in latencies between 2 data centers and calculates an ongoing average.

Contributor(s): [Patrick Callaghan](https://github.com/PatrickCallaghan)

## Objectives
Observe latency difference between two data centers.

## Project Layout
* [Main.java](/src/main/java/com/datastax/test/Main.java) - Runs a test with either a 1KB or 5 MB payload.

## How this Works
A description of how this sample works and how it demonstrates the objectives outlined above

## Setup and Running

### Prerequisites

* Java 8
* A DSE cluster running across two dcs
* Maven to compile and run code

### Running
* **1KB payload test**

To run the simple test with a 1KB payload and pause time of 1 second, execute the following
```
mvn clean compile exec:java -Dexec.mainClass="com.datastax.test.Main" -DcontactPoints=<localdc-ip> -Dlocaldc=<localdc> -Dremotedc=<remotedc>
```

* **5MB payload test**  

To use a larger 5MB payload and change the pause time to 3 seconds, add the file and pauseInSeconds arguments, for example
```
mvn clean compile exec:java -Dexec.mainClass="com.datastax.test.Main" -DcontactPoints=<localdc-ip> -Dlocaldc=<localdc> -Dremotedc=<remotedc> -Dfile=bigfile5M -DpauseInSeconds=3
```

You can add pass any file to simulate your payload. 
  	bin/dsetool create_core datastax_banking_iot.latest_transactions generateResources=true reindex=true coreOptions=rt.yaml

* **Sample queries**
