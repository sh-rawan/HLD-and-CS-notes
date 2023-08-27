# Backend

## Load balancers

1. For the backend looad balancers(also called as reverse proxies) Round robin or random server allocation is best.
2. To implement stickness you can implement consistent hashing.
    - Problem may arise when a new server joins hashing might change.
3. You can create a ring of loads and assign servers to them. And now if the new servers join you can allot them the empty seats in the ring.
4. You should divide your website into microservices like payments, Orders, products.
    - For such structure you need to do integration testing.
    - Microservices should be decoupled.
    - But now failure can be avoided, and website can be scaled easily.
    - You can also use different language for different microservices.
    - The problem is with Microservices discoverability which can be dealt with help of load balancers.

### Scalibility

1. for something like codechef you can not scale it because there are codes wich needs to be run.
2. Here you need to use the queues where the backend server will store the code.
3. Now another server can poll these files and start to run them.
4. Here you need to use websocket apis, which are bidirectionals. Which will respond to the query and also send you the result when it has without query.

5. Frontend scalability can be increased by using CDN(Cloudfront distribution network) which are place in every country and many places.
6. These are fast and robust and can scale your frontend and decrease your loading time.
