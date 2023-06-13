## ACID Properties

1. Atomicity
    - use write ahead logs and write everything before doing, in case of issue you can undo it from there.
2. Consistency
3. Isolation
4. Durability

-   If a database is loaded with all the different data like products, orders, videos etc and if number of users are high then it will be difficult to find out the cause for slow database.
-   so for database you should follow single responsibility principle.
-   there will be reduced traffic on each database

    -   cons are :-->
    -   application side becomes heavy, because now it needs to know which db to contact
    -   you need to take joins from different db which is slow
    -   be careful before doing this and dont introduce redundant db.

| SQL                                                      | No-SQL                                               |
| -------------------------------------------------------- | ---------------------------------------------------- |
| Difficult to add black boxes like color, ram in products | To types (1) key/value, and (2) document DB          |
| Can not store images                                     | Black boxes can be handeled easily                   |
| Sometimes joins are slow due to gib database             | Difficult to search by columns, needs to build index |
| This db has ACID properties                              | Here we apply base properties                        |
| To store more data it needs to do sharding               | It can store petabytes of data                       |

-   Other examples are --> Graph DB and Timestamps databases
