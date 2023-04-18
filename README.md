# Client-server Databases and Concurrent access

### Client-server Databases

A client server database system provides simultaneous access to a database for multiple clients. For example, social media websites store information on databases that are continuously being accessed and modified by different users simultaneously. Issues rarely arise when two users are requesting access to different, unrelated fields in a database. However, when different users attempt to access the same field at the same time, a problem known as concurrent access occurs. Concurrent access can result in database updates being lost if two users edit a record at the same time and can be managed with the use of record locks, serialisation, timestamp ordering and commitment ordering.

### Concurrent access preventions

- **Record locks** - When a record is accessed by one user, it is immediately locked to other users until the 
first user has finished using it. Other users are blocked from accessing or modifying the 
content of a field until it has been unlocked.

- **Serialisation** - Rather than locking a field, requests from other users are placed in a queue. Once the first user has finished using the field, the next command in the queue is executed and so on.

- **Timestamp ordering** - When multiple commands are sent to the same field in a database, each is assigned a timestamp which marks the point in time at which the command was initiated. Commands are carried out on the field in the order of their timestamps. 

- **Commitment ordering** - When a database uses commitment ordering, an algorithm is used to work out an optimum 
order in which to execute commands for the same field. This algorithm will take into
account the impact of commands on other parts of the database and attempt to minimise 
issues from occurring with the database. 
