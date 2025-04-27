# Hive Viva Questions and Answers

---

### 1. Define Apache Hive.  
**Answer:**  
Apache Hive is a data warehouse infrastructure built on top of Hadoop that provides tools for easy data extraction, transformation, and loading (ETL). It allows users to write SQL-like queries (HiveQL) which are then converted into MapReduce jobs for execution.

---

### 2. What is the role of HiveQL in Hive?  
**Answer:**  
HiveQL is a query language similar to SQL that abstracts the complexity of writing MapReduce code. Hive automatically compiles HiveQL into MapReduce jobs, thus simplifying the task of querying and managing large datasets in Hadoop.

---

### 3. Explain the architecture of Hive.  
**Answer:**  
Hive architecture consists of:

- **User Interface (UI):** Where the user submits HiveQL queries.
- **Compiler:** Converts queries into execution plans.
- **Metastore:** Stores metadata such as table schema and location.
- **Execution Engine:** Executes the compiled plans as MapReduce jobs.
- **HDFS/HBase:** The storage layer where actual data resides.

---

### 4. What are the different data types supported in Hive?  
**Answer:**  
Hive supports:

- **Numeric Types:** TINYINT, SMALLINT, INT, BIGINT
- **Date/Time Types:** TIMESTAMP, DATE, INTERVAL
- **String Types:** STRING, VARCHAR, CHAR
- **Complex Types:** STRUCT, MAP, UNION, ARRAY
- **Misc Types:** BOOLEAN, BINARY

---

### 6. How do you create a database and table in Hive?  
**Answer:**  

To create a database:
```sql
CREATE DATABASE database_name;
```

To create a table:
```sql
CREATE TABLE table_name (column1 datatype, column2 datatype)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE;
```

---

### 7. How do you load data into a Hive table?  
**Answer:**  
Use the following command:
```sql
LOAD DATA LOCAL INPATH '/path/to/file.csv' OVERWRITE INTO TABLE table_name;
```

---

### 8. How do you create an External Table in Hive?  
**Answer:**  
External tables use data stored outside Hive’s managed warehouse. Command:
```sql
CREATE EXTERNAL TABLE table_name (column definitions)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
LOCATION '/hdfs/path';
```

---

### 9. What is the difference between Managed and External tables in Hive?  
**Answer:**  

- **Managed Table:** Hive manages both data and metadata; deleting the table deletes the data.
- **External Table:** Hive only manages metadata; data remains even after dropping the table.

---

### 11. How do you perform a join operation in Hive?  
**Answer:**  
Example query:
```sql
SELECT a.fno, a.source, a.year, a.delay, b.dest
FROM flight a
JOIN nflight b
ON (a.fno = b.fno);
```

---

### 12. How do you alter a table in Hive?  
**Answer:**  

To rename a table:
```sql
ALTER TABLE old_table_name RENAME TO new_table_name;
```

To add a column:
```sql
ALTER TABLE table_name ADD COLUMNS (new_column_name datatype);
```

---

### 13. How do you drop a table in Hive?  
**Answer:**  
Command:
```sql
DROP TABLE table_name;
```

---

### 14. What is indexing in Hive? How do you create an index?  
**Answer:**  
Indexing improves the speed of querying large datasets by allowing faster access based on a column.  
Creating an index:
```sql
CREATE INDEX index_name ON TABLE table_name (column_name)
AS 'COMPACT' WITH DEFERRED REBUILD;
```

---

### 18. How do you load a text file into a Hive table?  
**Answer:**  
Prepare the file (example ipp.txt), then use:
```sql
LOAD DATA LOCAL INPATH 'ipp.txt' OVERWRITE INTO TABLE table_name;
```

---

### 19. What happens if you drop an External table?  
**Answer:**  
Only the metadata in Hive is deleted; the actual data in HDFS remains intact.

---

### 20. How does Hive work internally for executing queries?  
**Answer:**  
Hive compiles HiveQL queries into one or more MapReduce jobs using its compiler and execution engine, which are then run on the Hadoop cluster. Results are returned back to the user.

---

### 21. Why is Hive not ideal for low-latency querying?  
**Short Answer:**  
Because queries are heavy jobs (MapReduce/Spark), not lightweight transactions like in traditional databases.

---
2. Explain the concept of "Schema on Read" in Hive.
Short Answer:
Hive applies schema when reading data, not when storing it. Data is loaded as-is and
interpreted using the schema only during queries.
