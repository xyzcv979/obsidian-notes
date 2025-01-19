
Database should do 2 things
- Keep your data
- Allow you to retrieve your data at any time

Using a simple key value store as a database:
- set() - appends key, value as an entry to a log
- get() - scan the log for all occurrences of the key and get the most recent value
Of course, this is O(n) read time which is slow

## Indexing
Indexing allows you to optimize the read times of queries. 
The general idea is keeping some extra metadata on the side which acts as a bookmark to locate the data you want faster

## SSTables and LSM Trees vs B-Trees


## Storage Engines: OLTP & OLAP
Online Transaction Processing
	- 2 Main schools of thoughts when it comes to updates:
		- Log-structured
			- append to files, delete obsolete files, never update file that has been written
		- Update in-place
			- treats disk as set of fixed sized pages which can be overwritten
			- B-trees for sorted keys
	- Column based storage
		- row based require heavier computation to generate all the rows before parsing for columns
		- Having data grouped into their columns allows you to query much faster (just looks for columns and then create whole row if needed)
		- Good for compressing
			- Column data are converted to bitmasks
	
Online Analytics Processing
	- Create data warehouse which is optimized for Business Analysts to query as much as they want w/o costs. So, optimized for analytics. OLTP databases have heavy processing costs
	- You get upstream data from channels/databases and ETL the data to load into Data Warehouse


## Conclusion
How do databases handle storage and retrieval? What does database do when you query for something?
Looked at 2 different storage engines: OLTP and OLAP.

