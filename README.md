1. The Hadoop Distributed File System (HDFS) : 
       The Hadoop Distributed File System (HDFS) is a distributed file system that runs on standard or low-end hardware. Developed by       Apache Hadoop, HDFS works like a standard distributed file system but provides better data throughput and access through the MapReduce     algorithm, high fault tolerance and native support of large data sets.
       The HDFS stores a large amount of data placed across multiple machines, typically in hundreds and thousands of simultaneously         connected nodes, and provides data reliability by replicating each data instance as three different copies - two in one group and one in   another. These copies may be replaced in the event of failure.
       The HDFS architecture consists of clusters, each of which is accessed through a single NameNode software tool installed on a         separate machine to monitor and manage the that cluster's file system and user access mechanism. The other machines install one instance   of DataNode to manage cluster storage.
     
2. Hadoop Cluster: 
       Normally any set of loosely connected or tightly connected computers that work together as a single system is called Cluster. In     simple words, a computer cluster used for Hadoop is called Hadoop Cluster. 
       Hadoop cluster is a special type of computational cluster designed for storing and analyzing vast amount of unstructured data in a   distributed computing environment. These clusters run on low cost commodity computers.
       Hadoop clusters are often referred to as "shared nothing" systems because the only thing that is shared between nodes is the         network that connects them. 
       Large Hadoop Clusters are arranged in several racks. Network traffic between different nodes in the same rack is much more           desirable than network traffic across the racks.
       
3. HDFS BLOCKS :
       Filesystem Blocks: A block is the smallest unit of data that can be stored or retrieved from the disk. Filesystems deal with the data stored in blocks. Filesystem blocks are normally in few kilobytes of size. Blocks are transparent to the user who is performing filesystem operations like read and write.
       Hadoop distributed file system also stores the data in terms of blocks. However the block size in HDFS is very large. The default size of HDFS block is 64MB. The files are split into 64MB blocks and then stored into the hadoop filesystem. The hadoop application is responsible for distributing the data blocks across multiple nodes.
       The benefits with HDFS block are: 
           i) The blocks are of fixed size, so it is very easy to calculate the number of blocks that can be stored on a disk.
           ii) HDFS block concept simplifies the storage of the datanodes. The datanodes doesn’t need to concern about the blocks metadata        data like file permissions etc. The namenode maintains the metadata of all the blocks.
           iii) If the size of the file is less than the HDFS block size, then the file does not occupy the complete block storage.
           iv) As the file is chunked into blocks, it is easy to store a file that is larger than the disk size as the data blocks are            distributed and stored on multiple nodes in a hadoop cluster.
           v) Blocks are easy to replicate between the datanodes and thus provide fault tolerance and high availability. Hadoop framework        replicates each block across multiple nodes (default replication factor is 3). In case of any node failure or block corruption, the        same block can be read from another node.
