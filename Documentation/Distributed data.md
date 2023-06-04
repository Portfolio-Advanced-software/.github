# How to take care of distributed data?



## Introduction:
In a micro service architecture, like my personal project where multiple services handle user information and credentials, communication is needed to ensure data persistency. Problems like how can we keep persistent data across multiple data sources? occur. This is because micro services have their own database to be loosely coupled from other services. Some things that I considered or implemented are:

## 1. Messaging for Data handling:
When retrieving user information and credentials from distributed services, messaging is a great way to query your data. It's because it is asynchronous, meaning it doesn't have to wait for every respond from each micro service. This also proves that they are loosely coupled and continue to work. Beside that if a service is offline it can still consume the message when it comes back online. 

## 2. ACID
To ensure data persistency over all records you can easily implement a feedback message yourself or implement parts of ACID in your database. I read a bit about this that this proves acknowledgement of handling data records. MongoDB, the database I'm using, should offer support for the A in Acid, standing for Atomicity. This means that multiple actions to the database are only considered done if they're all done


## 3. Scaling
Distributed data also occurs in the same micro service if the database scales. To handle the full data to be available in that service you have solutions like replica sets or sharding. I wrote a document about how my database implementation uses them, you can find it [here](https://github.com/Portfolio-Advanced-software/.github/blob/main/Documentation/MongoDB.md).

## 4. Other
Another way to handle data changes are to store the data changes rather then updating the data this has more potential to keep data persistent, because if a system disfunctions it cannot accidentally delete a record.


<br>


## Implementation
I implemented some bits myself for example:

### Register
I have 4 services that save user data: auth-, authz-, user- and watchhistory-service. When registering the auth service puts a copy of some details into the user service database that's responsible for all its users actions. I do this by sending a message with the data and an action fields that a switch loop can go through to determine what action to perform in the database.

### Delete all user records
If a user wants to delete its account and all data, it will call the user service and the user service sends a message with the according user id and an action to the queue that the services are consuming messages from. When received they search all records with that id and delete it.

### Get all user records
If a user wants to download their data the user service again sends a message with an id and different action then delete to retrieve them all. The service waits till it gets back all the results before returning it to the user.
