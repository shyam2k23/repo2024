# Oracle Basics

https://www.tutorialspoint.com/plsql/index.htm  
https://www.geeksforgeeks.org/pl-sql-tutorial/  
https://www.javatpoint.com/pl-sql-tutorial  
https://www.oracletutorial.com/plsql-tutorial/  

## Oracle Exception

# Oracle Exception handling

# 3. Oracle Query Optimization

Developer - Understand query parsing and execution process +  Execution Plan
DBA - Oracle meta data to get tow know + oracle memory mapping - Db Block

# 2. Oracle Architecture

An Oracle Database **Server** consists of two things, **An Instance(Database Instance)** and **A Database**.

* **An Instance** (at least one): A database instance, is the combination of memory and processes that are a part of a running installation.
* **A Database**: It is a set of files that store data.

![image](https://github.com/user-attachments/assets/3eb7cd54-66c4-473f-9c49-411b5aeb4c77)

-------
![image](https://github.com/user-attachments/assets/7ff7cf17-2162-42da-b45c-2b4f202da668)

-------
![image](https://github.com/user-attachments/assets/74219c60-bd9b-4167-b613-b35dc5d0473f)


## 2. (A) Oracle Instance(Database Instance)

An Oracle Instance consists of two different sets of components:
* The first component set is **the set of background processes** (PMON, SMON, RECO, DBW0, LGWR, CKPT, D000 and others). 
>> These processes perform input/output and monitor other Oracle processes to provide good performance and database reliability.
* The second component set includes **the memory structures** that comprise the Oracle instance.
>>  When an instance starts up, a memory structure called the System Global Area (SGA) is allocated. 
>>  At this point the background processes also start.

The SGA is a shared memory structure allocated when the instance started up and is released when it is shut down. The SGA is a group of shared memory structures that contain data and control information for one database instance.

Different from the SGA, which is available to all processes, PGA is a private memory area allocated to each session when the session starts and released when the session ends.


![image](https://github.com/user-attachments/assets/d983cbfd-3798-438e-beb4-363cbe3e33c8)


---------- 

![image](https://github.com/user-attachments/assets/77ed6364-6ca0-4734-8fca-9f6f47f831cd)
----------
#### SGA Components:

* **Database buffer cache**: The Buffer Cache is a portion of the SGA that stores copies of data blocks read from datafiles. It is used to cache frequently accessed data blocks, reducing the number of disks I/Os required to access the data. This can improve performance by reducing disk I/O time and increasing the speed of data retrieval.
* **Redo log Buffer**: The most crucial structure for recovery operations is the redo log, which consists of two or more preallocated files that store all changes made to the database as they occur. Every instance of an Oracle Database has an associated redo log to protect the database in case of an instance failure.
* **Java pool**: The Java Pool is an optional portion of the SGA that is used by Java Virtual Machine (JVM) and related components. It is used to store Java-related data structures, such as Java classes and objects. This pool is used when the Oracle Database is configured to run Java applications or when using Oracle JVM.
* **Large Pool**: The Large Pool is an optional portion of the SGA that can be used for large memory allocation, such as backup and restore operations and I/O server processes. It is typically used to improve the performance of these operations by reducing the amount of disk I/O required.
* **Shared pool**: The Shared Pool is a portion of the SGA that contains shared memory structures, such as shared SQL and PL/SQL areas. It is used to store the parsed representation of SQL statements, execution plans, and PL/SQL program units. This allows for the efficient reuse of frequently executed statements, reducing the need for reparsing and improving performance.

https://www.geeksforgeeks.org/oracle-architecture/

#### Major Oracle Database’s background processes:
* **PMON** is the process monitor that regulates all other processes. PMON cleans up abnormally connected database connections and automatically registers a database instance with the listener process. PMON is a process that must be alive in an Oracle database.
* **SMON** is the system monitor process that performs system-level clean-up operations. It has two primary responsibilities including automatic instance recovery in the event of a failed instance, e.g., power failure and cleaning up of temporary files.
* **DBWn** is the database writer. Oracle performs every operation in memory instead of the disk because processing in memory is faster and more efficient than on disk. The DBWn process reads data from the disk and writes it back to the disk. An Oracle instance has many database writers DBW0, DBW1, DBW2, and so on.
* **CKPT** is the checkpoint process. In Oracle, data that is on disk is called a block and the data in memory is called buffer. When a block is written to the buffer and changed, the buffer becomes dirty, and it needs to be written down on the disk. The CKPT process updates the control and data file headers with checkpoint information and signals writing of dirty buffers to disk. Note that Oracle 12c allows both full and incremental checkpoints.

![image](https://github.com/user-attachments/assets/bcd094fe-1970-4af2-9fee-88ad7efc13db)


* **LGWR** is the log writer process which is the key to the recoverability architecture. Every change that occurs in the database is written out to a file called redo log for recovery purposes. These changes are written and logged by the LGWR process. The LGWR process first writes the changes to memory and then disk as redo logs which then can be used for recovery.
* **ARCn** is the archiver process that copies the content of redo logs to archive redo log files. The archiver process can have multiple processes such as ARC0, ARC1, and ARC3, which allow the archiver to write to various destinations such as D: drive, E drive, or other storage.
* **MMON** is the manageability monitoring process that gathers performance metrics.
* **MMAN** is the memory manager that automatically manages memory in an Oracle database.
* **LREG** is the listener registration process that registers information on the database instance and dispatcher processes with the Oracle Net Listener.

https://www.oracletutorial.com/oracle-administration/oracle-database-architecture/


### Memory Architecture
https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/memory-architecture.html
#### SGA
https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/memory-architecture.html#GUID-24EDB8CD-8279-4CED-82AF-642FC01A4A73

### Process Architecture
https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/process-architecture.html

#### Background Process
https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/process-architecture.html#GUID-D8AE1B78-69D5-4F0F-8BE3-C91AA2514F2D

https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/oracle-database-instance.html#GUID-824DB02D-D382-4B23-9A94-85A3E816B75E

## 2. (B) Oracle Database

One of the essential tasks of the Oracle Database is **to store data**. 
Oracle stores data logically in **tablespaces** and physically in **datafiles** associated with the corresponding tablespace.

### I) Logical storage structures

Oracle database server creates and recognizes logical structures, but the operating system doesn't.
Logical storage helps users find data and improves retrieval efficiency. The Database has a tablespace that stores all the data. Everything inside a database is stored in tablespace.

* **Tablespaces**: A database is divided into logical storage units called tablespaces. A tablespace is a logical container for a segment. Each tablespace consists of at least one data file. This is primary logical structure in a database that contains physical files. 
* **Segments**: A segment is a set of extents allocated for storing database objects, e.g., a table or an index. Contain one or more extents 
* **Extents**: An extent is a specific number of logically contiguous data blocks used to store a particular type of information. Contain multiple data blocks 
* **Blocks**: a data block corresponds to a number of bytes on the disk. Oracle stores data in data blocks. Data blocks are also referred to as logical blocks, Oracle blocks, or pages. Contains general information, such as the disk address and segment type

![image](https://github.com/user-attachments/assets/be821ea9-24fc-4c87-980e-c9c1c97cb716)

https://docs.oracle.com/cd/E11882_01/server.112/e40540/logical.htm

https://www.geeksforgeeks.org/working-on-oracle-tablespaces-for-developers/  

https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/logical-storage-structures.html#GUID-2785BB10-1628-4645-AEE9-27EC18E8BB21


### II) Physical storage structures

The physical files that store data on disk. The operating system can see and operate on these files.

* **Data files**: These files hold the actual data in the database.
* **Redo log files**: These files are used to hold the changes made in the database. Redo log files can be utilized during the database recovery process to retrieve the original information.
* **Control files**: It is a binary file that holds database status-related information like Database Name, Data File, and Redo Log file Names, File Locations, and Log Sequence Number. 
* **Parameter file**: This file contains the parameters which define the way the database is expected to start up.
* **Password file**: This file holds the user passwords and thus maintains the security of databases.


![image](https://github.com/user-attachments/assets/a16971a3-0a16-4314-870d-87d267c07da7)

https://docs.oracle.com/en/database/oracle/oracle-database/23/cncpt/physical-storage-structures.html#GUID-56DFECE5-FB81-494F-9AB8-25F120A1BDDC

https://docs.oracle.com/cd/E11882_01/server.112/e40540/physical.htm

----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------
In databases, "table" and "tablespace" refer to two distinct concepts:

Table

Definition: A table is a structured collection of data organized in rows and columns within a database. Each row represents a record, and each column represents an attribute of that record.
Purpose: Tables store the actual data that users interact with. For example, in a customer database, a table might contain customer information such as names, addresses, and phone numbers.
Example: A table named Customers might have columns like CustomerID, Name, Email, and Phone.
Tablespace

Definition: A tablespace is a storage structure that defines how data is stored in a database. It is a logical grouping of physical files where database objects (like tables, indexes, etc.) reside.
Purpose: Tablespaces help manage storage by allowing administrators to allocate space for different database objects and optimize performance. They can span multiple physical files and can be managed independently.
Example: In an Oracle database, you might have a tablespace named USER_DATA that contains all user-related tables and indexes.

Table is within a tablespace, both are logical within a database.

A DBA generally creates a tablespace and users create tables within it. Tables hold the application data.

An tablespace is linked to a DATAFILE (physical file).

Table (logical) > Tablespace (logical) > Datafile (physical)



A little terminology:

Oracle defines a database as the set of files that you find on your Oracle system. This means all data in your Oracle system is in these database files, commonly known as "data files". There are other files in the database such as parameter files and redo logs.

On the other hand, an instance consists of the processes and memory areas that Oracle database uses. Together, a database and an instance make up a database system. (For more information, see the Oracle Concept guide)

Logically, you will want to define different spaces within that database. This is done via tablespaces (see Oracle Concept guide). A tablespace usually consists of one or more data files. When you define a table with CREATE TABLE, you can specify in which tablespace the table should be created. This allows you to seperate different applications on the same database system, for example.

The Oracle Concepts guide is an excellent source of information for questions like these. See this picture on how data files and tablespaces are composed.

https://docs.oracle.com/cd/E11882_01/server.112/e40540/startup.htm#CNCPT601    
https://docs.oracle.com/cd/E11882_01/server.112/e40540/logical.htm#CNCPT402  
https://docs.oracle.com/cd/E11882_01/server.112/e40540/logical.htm#CNCPT301  



#### References
https://www.geeksforgeeks.org/oracle-architecture/
https://www.oracletutorial.com/oracle-administration/oracle-database-architecture/
https://blog.unisoftindia.org/2014/12/oracle-architecture-explained-in.html
https://argano.com/insights/articles/an-overview-of-oracle-database-architecture.html#:~:text=A%20breakdown%20of%20Oracle%20Database%20architecture&text=The%20database%20has%20logical%20structures,tasks%20is%20to%20store%20data.
https://docs.oracle.com/en/database/oracle/oracle-database/23/dbiad/db_dbserver.html
https://www.oracle.com/webfolder/technetwork/tutorials/architecture-diagrams/19/pdf/db-19c-architecture.pdf
