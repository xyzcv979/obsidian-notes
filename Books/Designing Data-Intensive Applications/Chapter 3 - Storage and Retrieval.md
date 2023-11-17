
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
