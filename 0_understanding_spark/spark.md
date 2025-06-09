spark architecture



spark storage

Delta Lake is comprised of the following elements: a delta table, delta files, a delta engine, a delta lake storage layer, and a delta transaction log.

Delta Table

A delta table is a collection of data kept using the Delta Lake technology and consists of three components:
 * Delta files contain data and are kept in object storage. 
 * The delta table is registered in the metastore, making it possible to have different versions of the table—for example, managed and unmanaged tables. There are a couple of metastore options you can use like Hive metastore or the AWS Glue catalog. For more info, see docs.databricks.com/metastores. 
 * The delta transaction log is kept with the delta files in object storage. We will go over the main idea behind this later in this chapter. 

Delta files can be available for many object stores with built in support for AWS S3, Microsoft Azure Storage, and HDFS. Support of Google cloud storage, Oracle Cloud Infrastructure and IBM Cloud object storage will be available in the upcoming releases.

Delta Files

By design, Delta Lake uses Parquet files (sometimes referred to as delta files) to store an organization’s data in their object storage. 
Parquet files are a state-of-the-art file format for keeping tabular data. They are faster and considered more powerful than traditional methods for storing tabular data because they store data using columns, not rows.
Delta files leverage all of the technical capabilities of working with Parquet files. However, they also track data versioning and metadata and store transaction logs to keep track of all commits made to a table or object storage directory to provide ACID transactions.  


Delta Engine

Delta Engine is a high-performance, Apache Spark compatible query engine that provides an efficient way of processing data in data lakes, including data stored in the open-source Delta Lake. Delta Engine optimizations accelerate data lake operations, supporting a variety of workloads ranging from large-scale ETL processing to ad hoc interactive queries. Because Delta Lake is specifically designed to be used with Apache Spark, reads and writes made to delta tables benefit from the inherent massively parallel processing capabilities of Apache Spark.


When Apache Spark code is run to read and write to Delta Lake, the following optimizations are available: 

- File management optimizations, including compaction, data skipping, and localized data storage
- Auto-optimized writes and file compaction
- Performance optimization via delta caching



Delta Lake Storage Layer

When building with Delta Lake, we store data using Delta Lake and then access it via Apache Spark. With this pattern, organizations have a highly performant, persistent storage layer built on low-cost, easily scalable object storage (Azure Data Lake Storage/ADLS, Amazon Web Services, or Simple Storage Service/S3).

Keeping all of your data in files in object storage is the central design pattern that defines a data lake.

Using the Delta Lake storage layer design pattern ensures data consistency and allows for the flexibility of working with a data lake.


Delta Transaction Log

The Delta Lake transaction log (also known as the DeltaLog) is an ordered record of every transaction that has ever been performed on a Delta Lake table since its inception. It is the Delta Lake central repository that serves as the single source of truth—the central repository that tracks all changes that users make to the table.

Delta Lake: Concepts and Features

Next, let's look at the fundamental concepts behind Delta Lake. Delta Lake is built upon three pillars that address reliability, performance, and engineering challenges. It provides clean, quality data; consistent views across batch and stream data workloads; and is optimized and easy to adopt.

Pillar 1: Clean, Quality Data 

Delta Lake provides high quality and reliable data that is always ready for analytics through a range of features for ingesting, managing, and cleaning data.
According to this pillar, Delta Lake has the following features:
 * "ACID transactions" ensure that only complete writes are committed.
 * "Schema enforcement" automatically handles schema variations to prevent insertion of bad records during ingestion.
 * "Time Travel," part of Delta Lake's built-in data versioning, enables rollbacks, full historical audit trails, and reproducible machine learning experiments.
 * "Exactly once semantics" ensures that data is neither missed nor repeated erroneously.



"Exactly once semantics" ensures that data is neither missed nor repeated erroneously.

Delta Lake supports multiple simultaneous readers and writers for mixed batch and stream data.
According to this pillar, Delta Lake has the following features:
- "Snapshot isolation" provides support for multiple simultaneous writers and readers.
- "Mixed streaming and batching" data means that a table in Delta Lake is a batch table as well as a streaming source and sink. Streaming data ingestion, batch historic backfill, and interactive queries all work right out of the box.


Pillar 3: Optimized and Easy to Adopt

Delta Lake is easy to adopt and optimized for the cloud, and using Delta Lake avoids data lock-in. 
According to this pillar, Delta Lake has the following features:

- "Scalable metadata handling" leverages Spark's distributed processing power to handle all the metadata for petabyte-scale tables with billions of files with ease.
- "Scalable metadata handling" leverages Spark's distributed processing power to handle all the metadata for petabyte-scale tables with billions of files with ease.
- "Compatibility with Spark APIs" means that Delta Lake is easy for Spark users to adopt.
- As an "open-source format," Delta Lake eliminates data lock-in. With Delta Lake, there is no requirement to use only Delta Lake.
- "Local development" means that Delta Lake supports laptop-based development and testing.
- "In-place import" allows efficient, fast import from Parquet to delta format.

