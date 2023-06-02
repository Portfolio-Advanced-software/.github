# Scalability inside my deployed MongoDB cluster
For my individual project I'm using MongoDB as a database. Currently my MongoDB is running in a free shared cluster on their cloud platform. MongoDB takes care of it's scaling and to know how they do it I will be looking into the options they (and the free tier) provide.


## Scalability options for MongoDB
I read multiple articles to research the scalable ways of MongoDB and [this one](https://www.mongodb.com/basics/scaling) described all the possibilities in short. I will shortly describe them down here and eventually dive deeper in the one that the free tier uses.

### Vertical scaling
Vertical scaling means that the node where the database is running on, virtually scales to more resources like cpu power and ram. Therefore it can handle more traffic.

### Horizontal scaling
Horizontal scaling means that there will be more nodes, meaning more database instances created inside the cluster to handle the traffic. It's a bit more complicated than just assigning more resources to a node. To do horizontal scaling MongoDB provides two approaches in the article:

#### [Sharding](https://www.mongodb.com/basics/sharding)
Sharding is essentially spreading the data across multiple instances, meaning the first 100 objects are stored on instance 1 and the next 100 on instance 2, etc. for example. Inside such a cluster the instances are called shards, each shard has a primary shard and the rest are secondary ones. The primary handles incoming traffic. A shard is simply a subset of all the data that needs to be stored. To access the right data there is a mongos router that uses the config server to get the corresponding data. If one of the primary shards fails there will be an election on which secondary shard replaces the primary one. If the primary one eventually comes back online it is shifted back the way it was. During this process it is not possible to use all its functionality. 

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/e27ac559-e29b-489f-9e03-03160db97d15)


#### [Replica sets](https://www.mongodb.com/basics/replication)
This means that it will be replicating all the data across all multiple nodes, meaning every node has the same data which improves read functionality because every node can be adressed. On the other hand if you have high read write actions it could happen that the data is not yet processed on one of the nodes. There is still a primary node that handles all the write actions and is in control of creating these replicas to the other nodes. If the primary fails the same thing happens like sharding, an election.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/b59f33a6-25f9-42b7-b2e0-2c612d6b63e3)

<br>

### M0 tier
The free tier M0 that I'm using makes use of a replica set of 3 nodes.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/a2ee06cb-c550-4b25-9b3b-ee958f4dad9e)

<br>

#### Characteristics
- Replication is asynchronous so primary node stays available
- If no nodes are left after the election an arbiter comes in to take the secondary nodes responsibility, but can never become a primary one
- Write acknowledgement can be set from none to acknowledgement from the primary only to the amount of secondary ones that need to ackowledge. 
