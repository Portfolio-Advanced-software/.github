# Which technique is the most optimal way of communicating between micro services?
This semester we will be developing skills that are useful in a micro service architecture, software build using this architecture is split in multiple small independent services that are separate of each other. Because of this approach they need a way to communicate together, for example when they need data from each other. Therefore it seems a good subject to do a research about, there are a lot of ways of communicating and they will definitely have an impact on the system overall.

I will search for an answer to the main research question in two scenario's: my individual project and the group project. The first one will be a clone of the famous video streaming platform Netflix and the second one is a testing platform for trading strategies using MetaTrader 5.

To answer the question I'm going to research multiple sub questions to get to a final answer and help me along the way.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/c2bd61a1-8dc0-4947-9032-0d73f3f52157)




## Which techniques for micro service communication are available?
I’m already familiar with some techniques, but to broaden my knowledge and create a good base for the research. I did research to different ways of communicating and selected the most popular one and therefore kept it limited. There are also alternative ways, but they’re not included in this research.
I read some articles describing approaches to communicate and which protocols they used to achieve this. I will be naming the articles and what techniques I came across while reading them.

### DOT-methods
- Literature study
- Community research

### Literature study
#### [3 methods for microservice communication](https://blog.logrocket.com/methods-for-microservice-communication/)
- HTTP
- Message communication
- Event-driven communication 


#### [Microservices Communications](https://medium.com/design-microservices-architecture-with-patterns/microservices-communications-f319f8d76b71)
- HTTP
- gRPC
- Message brokers (with AMQP protocol)

#### [4 Ways to Establish Communication between Microservices](https://levelup.gitconnected.com/4-ways-to-establish-communication-between-microservices-984207f29497)
- REST
- (g)RPC
- Messaging integration
- Streaming Integration

#### [Communication in a microservice architecture](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/communication-in-microservice-architecture)
- HTTP
- AMQP
- Binary protocol (like TCP)   




#### [Reddit](https://www.reddit.com/r/microservices/comments/hl9rww/microservices_servicetoservice_communication/)
Forums are also a good point to retrieve information, the chance that this question is already been discussed is high. Therefore I started looking for forums and came across some interesting new ways.
- Azure Service Bus
- Azure Event Grid


#### Summary
I noticed reading the articles that some articles where describing the used protocol and other where talking about architectural approaches. Therefore I narrowed it down to a list of terminologies used to implement micro service architecture.

- REST
- RPC
- Messaging
- Event driven communication
- Streaming
- Binary 


### Community research
To test my list for completeness I asked around on Reddit if there were any other popular ones. The best addition was this comment:  

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/4d71d7de-35a4-4b16-b89a-eab26fc3c81b)

I meaningly left out SOAP, because from former experience I know that is slightly outdated, so I added one addition to the list being:
- GraphQL


### Conclusion
Combining the two methods of researching I used I get the following list that will be the starting point of this research:
- REST
- RPC
- Messaging
- Event driven communication
- Streaming
- Binary
- GraphQL

