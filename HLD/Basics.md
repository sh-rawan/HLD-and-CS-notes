# Basics of computer architecture

1. `Reliability` --> No matter what happenes the system still keeps giving valid results.
    - Hardware faults --> Avaoid by creating multi systems.
    - Software faults --> Avoid by (a) Good test coverage, (b) System monitoring and exception handling, (c) Keep errors logging
2. `Scalability` --> sccaling of a system
    - (1) Number of user increase, like more people join the platform.
    - (2) More number of request, like people are more active on your platform on christmas.
    - (3) Size of data is large, on platforms like Netflix.

| No. | `Scalability`                        | `Performance`               |
| --- | ------------------------------------ | --------------------------- |
| 1.  | Accptable performance for 93% prople | Average delay of 99% people |

| No. | `Latency`                                                       | `Throughput`                         |
| --- | --------------------------------------------------------------- | ------------------------------------ |
| 1.  | Time consumed between send the request and receive the response | Number of request handled per second |

Try to increase the Throghtput while increasing Latency under acceptable limits.

3. `Maintainability` --> keep system simple and easy which can also evolve over a period of time.
