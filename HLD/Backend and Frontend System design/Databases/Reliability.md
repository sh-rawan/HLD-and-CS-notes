# Database

## Reliability

1. How to avoid single point of failure where if the one server goes down then the whole system stops.
    - Replication is the solution, and it can be two types Synchronus and asynchronus updates -->

### Synchronus Updates

-   Synchronus Updates where user is given acknowledgement only when all the database are updated
-   Issues
    -   It gives increased `latency`.
    -   Even if one of the DB server is down then the transection is incomplete.
    -   To solve this issue you can use the geart beat check and find out if the DB is down.

### Asynchronus updates

-   Here database is updated and responded user with ACK after this behind the scene all the other databases
    -   Issue is if the database dies after informing the user with OK. It violates the `durability` principle.
    -   Another issue is there is replication lag where suppose if you make a post it might not be visible everywhere.

### Hybrid Updates

-   This model says that you should respond user with of if for example 3 out of 5 databases respond with OK.
-   With the help of this model we have almost eliminated issues with other model.

2. How to handle incomplete transaction for ex during payment database goes down.

## CAP Theorem

It say that you can have only two of the above three at one time.

-   Consistency
    -   Weak consistency, like logging analytics data. Even if data is consistent over a day then it is okay.
    -   Eventual consistent, like email which can perform async updates. And might need few minutes to be consistent.
    -   Strongly consistent, like bank transcation
-   Availability
-   Partition

1. Read your write consistency

    - You should get the read data back after you perform write.
    - Needs to create a session which talks to the same DB on which it has done write.

2. Monotonic consistency

    - If some user is sitting between two database then he might get different read results at different times.
    - You need to create a session which rember the database and reads from the same database from the second time.

3. Relibality of different writes at the same time. Based on this there can be different data on different databases.

### Leaderless replication model

-   This models is called is `Quorems`.
-   Write to more than one data base and read from more than one database.
-   And the sum of number of write database and number of read database should be greater than total number of database.

### Single leader replication model

-   We have one db which is the master and other are slaves.
-   Any write will only happen to the master, read can also happen with the slaves.
    -   (1) In case of master failover you need to promotes one of the slaves to become master.
    -   (2) You need to set some timer to make sure the slave is dead.
    -   (3) You can use sequence model or latest update model to create new master..
    -   (4) Routing to new master need to be done using redirecting by slave.
    -   (5) In case old master comes up suddenly during new master creationn you need to kill one of them.

### Multi leader replication

-   You can have more than one master here but you need to keep some database
