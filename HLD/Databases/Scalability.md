# Scalability

1. Improving performance
    - Right DB
    - Denormalization --> It mean breaking the normal rules of DB design to makee the db faster
        - You can store some important data that you need to query again and again, in the same table without creating new table for it.
          for ex save the average score of the participant
        - Some fields like phone number doesnot need to have saperate table, when you know that this field is not used for searching frequently.
    - Indexing --> create a map (ordered or unordered) of for example email and id. And now for any query you just need to go to the map search email and get the id.
2. Split the load
    - Federation --> dividing different databases based on table.
    - Sharding --> dividing different tables on different table into different databases.
        - You can use the hash function to convert id into database shard.
        - You can also create a table of id and corresponding shard number.
        - Cons
            1. The system will become complex and difficult to maintain.
            2. Data can be non uniform and increase load on one shard.
            3. Queries may be accross shards.
