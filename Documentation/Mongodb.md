# Scalability inside my deployed MongoDB cluster

## Scalability options for MongoDB
I read multiple articles to research the scalable ways of mongodb and [this one](https://www.mongodb.com/basics/scaling) described them all in short.

### Vertical scaling
This means that the node where the database is running virtually gets more power to handle the traffic.



### Horizontal scaling
Horizontal scaling means that there will be more nodes created to handle the traffic. To do horizontal scaling mongodb provides two approaches:

#### Sharding (Spreading the data across multiple nodes)
Sharding essentially is spreading the data across multiple nodes, meaning the first 100 objects are stored on node 1 and the next 100 on node 2, etc. There is a primary node and the rest are secondary nodes. If the primary nodes fails there will be an election on which secondary node becomes the primary. It the primary comes back online it is shifted back the way it was. During this process you temporarily can not use all its functionality. 


#### Replica sets
This means that it will be replicating all the data across all multiple nodes, meaning every node has the same data which improves read functionality because every node can be adressed. On the other hand if you have high read write actions it could happen that the data is not yet processed on one of the nodes. There is still a primary node that handles all the write actions and is in control of creating these replicas to the other nodes. If the primary fails the same thing happens like sharding, an election.


### M0 tier
The free tier M0 that I'm using makes use of a replica set of 3 nodes.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/a2ee06cb-c550-4b25-9b3b-ee958f4dad9e)


charachteristics
- Replication is asynchronous so primary node is available
- If no nodes are left after the election an arbiter comes in to take the secondary nodes position, but can only fullfil this position
- Write acknowledge can be set from none, acknowledge from primary only and last the amount of secondary ones need to ackowledge 
