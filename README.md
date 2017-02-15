# assignment-2.2
QN 1 HDFS
• The file store in HDFS provides scalable, fault-tolerant storage at low cost. 
• The HDFS software detects and compensates for hardware issues, including disk problems and server failure. 
• HDFS stores files across the collection of servers in a cluster. 
• Files are decomposed into blocks and each block is written to more than one of the servers. 
• The replication provides both fault-tolerance and performance.
HDFS has been designed keeping in view of the following features: 
• Very large files: Files that are megabytes, gigabytes, terabytes, or petabytes of size.
 • Streaming data access: HDFS is built around the idea that data is written once but read many times. A dataset is copied from source and then analysis is done on that dataset over time. 
• Commodity hardware: Hadoop does not require expensive, highly reliable hardware as it is designed to run on clusters of commodity hardware.
QN 2 HADOOP CLUSTER
1.A Hadoop cluster is a special type of computational cluster designed specifically for storing and analyzing huge amounts of unstructured data in a distributed computing environment. 
2.Such clusters run Hadoop's open source distributed processing software on low-cost commodity computers. Typically one machine in the cluster is designated as the NameNode and another machine the as JobTracker; these are the masters. The rest of the machines in the cluster act as both DataNode and TaskTracker; these are the slaves. Hadoop clusters are often referred to as "shared nothing" systems because the only thing that is shared between nodes is the network that connects them. 

3.Hadoop clusters are known for boosting the speed of data analysis applications. They also are highly scalable: If a cluster's processing power is overwhelmed by growing volumes of data, additional cluster nodes can be added to increase throughput. Hadoop clusters also are highly resistant to failure because each piece of data is copied onto other cluster nodes, which ensures that the data is not lost if one node fails.

QN 3 HDFS Blocks
For HDFS, since it is designed for large files, the block size is 128 MB by default. Moreover, it gets blocks of local file system contiguously to minimise the head seek time.
 When you store a file in HDFS, the system breaks it down into a set of individual blocks and stores these blocks in various slave nodes in the Hadoop cluster. This is an entirely normal thing to do, as all file systems break files down into blocks before storing them to disk.
HDFS is often blissfully unaware that the final record in one block may be only a partial record, with the rest of its content shunted off to the following block. HDFS only wants to make sure that files are split into evenly sized blocks that match the predefined block size for the Hadoop instance (unless a custom value was entered for the file being stored). In the preceding figure, that block size is 128MB.
Every data block stored in HDFS has its own metadata and needs to be tracked by a central server so that applications needing to access a specific file can be directed to wherever all the file’s blocks are stored
HDFS is designed to enable high throughput so that the parallel processing of these large data sets happens as quickly as possible. The key to Hadoop’s scalability on the data processing side is, and always will be, parallelism — the ability to process the individual blocks of these large files in parallel.

