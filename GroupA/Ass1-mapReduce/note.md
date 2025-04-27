# Viva Questions and Answers

### 1. Define MapReduce.
**Answer:**  
MapReduce is a programming model and a distributed processing framework developed by Google, used for processing large data sets across clusters of computers.  
It works by dividing the task into two main phases: **Map**, which processes and filters data into key-value pairs, and **Reduce**, which aggregates and summarizes those results.

---

### 2. What are the two main components of a MapReduce job?
**Answer:**  
The two main components are:
- **Mapper:** Takes input and produces key-value pairs.
- **Reducer:** Takes the grouped output from the mapper and summarizes or processes it to produce final output.

---

### 3. Explain the flow of a MapReduce program.
**Answer:**  
The flow of a MapReduce program is:
- **Input Splitting:** Input data is split into manageable chunks.
- **Mapping:** Each chunk is processed by a Mapper to generate intermediate key-value pairs.
- **Shuffling and Sorting:** Intermediate results are shuffled and sorted by key.
- **Reducing:** The Reducer aggregates the values for each key and produces the final output.

---

### 5. What is HDFS and why is it important for MapReduce?
**Answer:**  
HDFS (Hadoop Distributed File System) is the storage system used by Hadoop.  
It allows storage of large files across multiple nodes in a cluster, providing high availability and fault tolerance, which is crucial for MapReduce to operate on big datasets.

---

### 6. What are Writable and WritableComparable interfaces in Hadoop?
**Answer:**  
- **Writable:** Allows Hadoop to serialize data types for network communication.
- **WritableComparable:** Extends Writable and adds a comparison method, enabling Hadoop to sort keys during the shuffle phase.

---

### 7. What is pseudo-distributed mode in Hadoop?
**Answer:**  
Pseudo-distributed mode is a Hadoop configuration where all Hadoop services (NameNode, DataNode, ResourceManager, NodeManager, etc.) run on a single machine, simulating a distributed environment for testing and development.

---

### 8. Explain the Map stage in MapReduce.
**Answer:**  
In the Map stage, each input record is processed by the Mapper function to produce intermediate key-value pairs, which are then passed to the shuffle and sort stage.

---

### 9. Explain the Reduce stage in MapReduce.
**Answer:**  
In the Reduce stage, intermediate key-value pairs are aggregated based on their keys.  
The Reducer processes these grouped data and outputs a summarized set of results.

---

### 10. What is the role of the shuffle and sort phase in MapReduce?
**Answer:**  
The shuffle phase transfers Mapper outputs to the appropriate Reducer based on the key.  
The sort phase organizes the data by key so that all values for the same key are sent together to the Reducer.

---

### 11. Why do we create a JAR file in a Hadoop project?
**Answer:**  
We create a JAR file to bundle all the compiled Java classes and configuration files.  
This JAR can then be executed on the Hadoop cluster using the `hadoop jar` command.

---

### 13. What is the purpose of Manifest.txt in the project?
**Answer:**  
Manifest.txt defines the entry point (**Main-Class**) for the JAR file so Hadoop knows which class to run when executing the JAR.

---

### 14. How do you copy data from local filesystem to HDFS?
**Answer:**  
Using the command:
```bash
hadoop fs -put /path/to/localfile /destination/on/hdfs
```

---

### 15. How do you view the output of a MapReduce job?
**Answer:**  
After the job runs, you can view the output using:
```bash
hadoop fs -cat /output_directory/part-00000
```

---

### 16. What are the commands to start Hadoop services?
**Answer:**  
Start HDFS:
```bash
start-dfs.sh
```

---

### 19. Explain how MapReduce achieves parallel processing.
**Answer:**  
Each Mapper and Reducer runs independently on different nodes or containers.  
Input data is split and processed in parallel, and the final results are merged, allowing massive scaling and faster processing.

---

### 20. What is the role of the Driver class in a MapReduce program?
**Answer:**  
The Driver class sets up the job configuration: specifying input/output paths, setting Mapper and Reducer classes, setting key/value output types, and launching the job.

---

### 15 (Duplicate). Why do we use MapReduce instead of simple Java programs for counting accesses?
**Short Answer:**  
MapReduce can parallelize the counting across a distributed cluster handling large datasets, which normal Java cannot scale for.

---
