# Which technique is the most optimal way of communicating between micro services?
This semester we will be developing skills that are useful in a micro service architecture, software build using this architecture is split in multiple small independent services that are separate of each other. Because of this approach they need a way to communicate together, for example when they need data from each other. Therefore it seems a good subject to do a research about, there are a lot of ways of communicating and they will definitely have an impact on the system overall.

I will search for an answer to the main research question in two scenario's: my individual project and the group project. The first one will be a clone of the famous video streaming platform Netflix and the second one is a testing platform for trading strategies using MetaTrader 5.

To answer the question I'm going to research multiple sub questions to get to a final answer and help me along the way.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/c2bd61a1-8dc0-4947-9032-0d73f3f52157)


<br>

## Which techniques for micro service communication are available?
### DOT-methods
- Literature study
- Community research

<br>

### Literature study
I’m already familiar with some techniques, but to broaden my knowledge and create a good base for the research I did research about different ways of communicating and selected the most popular one and therefore want to keep it limited. There are also alternative ways, but they’re not included in this research.
I read some articles describing approaches to communicate and which protocols they used to achieve this. I will be naming the articles and what techniques I came across while reading them.

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

<br>

### Community research
To test my list for completeness I asked around on Reddit if there were any other popular ones. The best addition was this comment:  

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/4d71d7de-35a4-4b16-b89a-eab26fc3c81b)   
[The post](https://www.reddit.com/r/microservices/comments/13coix7/popular_ways_of_communicating_between/)


I meaningly left out SOAP, because from former experience I know that is slightly outdated, so I added one addition to the list being:
- GraphQL

<br>

### Conclusion
Combining the two methods of researching I used I get the following list that will be the starting point of this research:
- REST
- RPC
- Messaging
- Event driven communication
- Streaming
- Binary
- GraphQL

<br>

## What are the relevant criteria for selecting a communication method?
The criteria that are relevant are specific per scenario, therefore the research will be splits in two per scenario from now on.

### DOT-methods
- Brainstorm
- Explore user requirements
- Problem analysis
- Stakeholder analysis
- Survey

<br>

### Brainstorm
Before I begin to decide which criteria are relevant to each use case I want to make a selection of criteria that I will pick from. I started brainstorming and writing a lot of criteria I could test and after combining some I came up with a list of 7 criteria that I will be using to answer this research question.

- Scalability (How will it handle horizontal scaling?) 
- Performance (How fast will it perform?)
- Reliability (How will it handle errors and how is it's fault tolerance?)
- Maintainability (Is it easy to implement and keep working?)
- Security (What security measures can be taken and how safe are they?)
- Flexibility (How will it work with different systems?)
- Costs (How much does it cost to implement?)

<br>

### BingeBuster
BingeBuster is a project I'm creating individually as a tool to prove my knowledge this semester. More information can be found [here](https://github.com/Portfolio-Advanced-software/BingeBuster-WebUI)

#### Explore user requirements
I will developing this product for my own use so I created user stories based on my own preferences. These stories can be found [here](https://github.com/Portfolio-Advanced-software/.github/blob/main/BingeBuster/User%20stories%20BingeBuster.md). Based on the user stories and my requirements I selected the following criteria:





#### Stakeholder analysis
#### Survey

<br>


### Stockbrood
Stockbrood is our organization name for our group project that will be a part of our semester. The project will be build for a product owner (PO) who wants a platform for (stock) traders to test their trading strategies on, more can be found [here](https://github.com/S-A-RB05).

#### Explore user requirements
As a group we created user stories in consultation with our PO, they can be found [here](https://github.com/S-A-RB05/.github/blob/main/User%20stories.pdf). Based on the stories and the multiple meetings we had with our PO about important factors in the platform. I selected the following criteria of importance:





#### Problem analysis
#### Stakeholder analysis
#### Survey
