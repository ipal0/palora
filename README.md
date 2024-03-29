## Wrapper Class around cx_Oracle for Oracle Autonomous Database
* This class supports multiple connections to the database using session pool. The minimum and maximum number of sessions can be defined. 
* In cx_Oracle after connecting to the database, for every query statement the data needs to be fetched and for evey update or insert statement the data needs to be committed. But this class eliminates these requirements and make it simple to read and write to the database.

# Files:
* palora/__init__.py

## Installation:
* sudo pip3 install palora

## Usage Examples:
* import palora
* db = palora.db('user', 'password', 'tsn-entry')  ##-connect to the database with user, password, tsn. Optional parameters are min, max, increment & encoding.
* db.read("sql statement")  ##-returns the read data from database with flat=True
* db.read("select item from table", flat=False)  ##-returns the raw read data 
* db.read("select item from table where item = %s", (sub1,))  ##-read with string substitution
* db.read1("sql statement")  ##-returns the first read data similar to fetchone
* db.write("sql statement")  ##-writes the data and commits to the database

## For other cx_Oracle connection commands use the connection class
* db.conn....
