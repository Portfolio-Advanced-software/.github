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
- Survey

<br>

### Brainstorm
Before I begin to decide the importance of certain criteria in a project I have to decide which ones are relevant to use, so I have to make a selection. I started brainstorming and writing a lot of criteria I could test and after combining some I came up with a list of 7 criteria that I will be using to answer this research question.

- Scalability (How will it handle horizontal scaling?) 
- Performance (How fast will it perform?)
- Reliability (How will it handle errors and how is it's fault tolerance?)
- Maintainability (Is it easy to implement and keep it working?)
- Security (What security measures can be taken and how safe are they?)
- Flexibility (How will it work with different systems?)
- Costs (How much does it cost to implement?)

<br>

### BingeBuster
BingeBuster is a project I'm creating individually as a tool to prove my knowledge this semester. More information can be found [here](https://github.com/Portfolio-Advanced-software/BingeBuster-WebUI)

#### Explore user requirements
I will developing this product for my own use so I created user stories based on my own preferences. These stories can be found [here](https://github.com/Portfolio-Advanced-software/.github/blob/main/BingeBuster/User%20stories%20BingeBuster.md). Based on the user stories and my requirements I added the importances of each criteria for this project by using points (more points means more important):

##### Scalability (4 points) 
This platform will be build around the design of scalability meaning it's very important that the type of communication is also scalable and will not be a bottleneck in this application.

##### Performance (2 point)
The performance of communication isn't that important, the performance of the streaming service is. 

##### Reliability (3 points)
Because the speed of communication isn't important, the reliability is because users will depend on it and when the communication doesn't work users can't stream content.

##### Maintainability (2 point)
It's important for it to be implemented easily to speed up the development time, but once it is implemented it doesn't need to be maintained a lot. 

##### Security (1 point)
While security is always important it won't be as important, because the communication that will occur is mostly with non sensitive information.

##### Flexibility (1 point)
I won't be using a lot of different types of services written in different languages so the flexibility isn't that important to me.

##### Costs (2 points)
I have to implement this on my own therefore the costs will be important. I don't have any budget.

<br>

#### Survey
I created a survey where other developers could give their opinions and see what they find important. I created an average weight per criterium. The final result is:

- Scalability (4,6 points) 
- Performance (4,2 points)
- Reliability (4,2 points)
- Maintainability (3 points)
- Security (3 points)
- Flexibility (2,8 points)
- Costs (3,4 points)


<table>
  <tr>
    <td><img src="https://github.com/Portfolio-Advanced-software/.github/assets/73555911/3f17ca25-4b0c-4eea-a7a6-e020e683d6ff" width=500 height=800></td>
    <td><img src="https://github.com/Portfolio-Advanced-software/.github/assets/73555911/d7b54375-d014-44bb-9f82-1de25d7f710f" width=500 height=800></td>
  </tr>
</table>


<br>



### Stockbrood
Stockbrood is our organization name for our group project that will be a part of our semester. The project will be build for a product owner (PO) who wants a platform for (stock) traders to test their trading strategies on, more can be found [here](https://github.com/S-A-RB05).


#### Problem analysis
While discussing the case and project with our PO we came to the conclusion that there was a problem. The problem is that manually testing takes a lot of time and therefore you can not keep up to date with the strategies and the current market. After doing more investigation about the problem our PO was facing we came to the conclusion that there is to much manual labor required to efficiently make use of completely testing a trading strategy. This makes the criterias scalability and performance important ones.

#### Explore user requirements
As a group we created user stories in consultation with our PO, they can be found [here](https://github.com/S-A-RB05/.github/blob/main/User%20stories.pdf). Based on the stories and the multiple meetings we had with our PO about important factors in the platform. I weighted the criteria as following:

##### Scalability (5 points) 
This platform will be build to run a lot of (options on) trading strategies therefore being able to scale is the most important thing.

##### Performance (4 points)
A lot of different strategies' options will be tested by a lot of users so there will be a lot of communicating between services therefore it could be a bottleneck in the system's speed and therefore it is an important criteria.

##### Reliability (3 points)
It should be reliable because there is a lot of scaling involved and therefore is a service is lost or doesn't scale correctly the communication should continue to work with the new services.

##### Maintainability (2 point)
It is nice to have a maintainable solution and it is to a certain level even needed, but the maintainability is in this use case not the most important criteria.

##### Security (2 point)
While security is always important it won't be as important, because the communication that will occur is mostly with non sensitive information.

##### Flexibility (3 points)
This platform has a lot of potential to expand this means that other systems might come or go and therefore it needs to integrate with each other in the future.

##### Costs (1 point)
Because it's a fictional project the costs doesn't really matter, but in a real situation should still be noticed. 


<br>


#### Survey
I created a survey where other developers could give their opinions and see what they find important. I created an average weight per criterium. The final result is:

- Scalability (4,6 points) 
- Performance (4,6 points)
- Reliability (4,2 points)
- Maintainability (3 points)
- Security (3,6 points)
- Flexibility (3,2 points)
- Costs (3,2 points)


<table>
  <tr>
    <td><img src="https://github.com/Portfolio-Advanced-software/.github/assets/73555911/e99a4632-4455-40a6-9b96-6892805d507c" width=500 height=800></td>
    <td><img src="https://github.com/Portfolio-Advanced-software/.github/assets/73555911/ace2943d-76ef-4514-8a54-8c2128e6eacc" width=500 height=800></td>
  </tr>
</table>

<br>

### Conclusion
When looking over the results to create a top 3 I can conclude that for both projects it's the same 3 criteria that are the most important to test. So I will continue my research looking for the most optimal way of communicating based on these 3 criteria:

- Scalability
- Performance
- Reliability




<br>

## How can I test different criteria on these types of communication?

### DOT-methods
- Literature study

### Scalability


### Performance
I will be testing the performance by looking at response time, throughput and error rate. These three seem the most useful to compare the different types of communication.

I went looking for concrete ways to test my selected criteria on the types of communication. Therefore I started looking at ways to test it on the REST type, so I have a good starting point. Beside that I did a cource on Apache Jmeter because I already read a lot about it and wanted to use it for my personal project. 

[CertificateOfCompletion_JMeter Performance and Load Testing.pdf](https://github.com/Portfolio-Advanced-software/.github/files/11469195/CertificateOfCompletion_JMeter.Performance.and.Load.Testing.pdf)


[How to do Performance and Load Testing on your REST API in simple way](https://medium.com/@yadav.lavisha2212/how-to-do-performance-and-load-testing-on-your-rest-api-in-simple-way-5d934769bc2)
This article perfectly explains how I can test the performance. 





### Reliability

<br>

## How does each type of communication test to the researched criteria?

### REST
I created a basic application to test the criteria on, this prototype can be found [here](https://github.com/Portfolio-Advanced-software/micro-service-communication-prototype/tree/main/REST).

#### Scalability
#### Performance
#### Reliability


<br>


### RPC
I created a gRPC prototype already so I will be testing it on [that one](https://github.com/Portfolio-Advanced-software/Golang-gRPC-POC).

#### Scalability
#### Performance
#### Reliability


<br>


### Messaging/Event driven communication
While doing research about implementing a prototype I concluded that it is an architectural approach but they both use a broker to send and receive data. The prototype I created can be found [here](https://github.com/Portfolio-Advanced-software/micro-service-communication-prototype/tree/main/RabbitMQ).

#### Scalability
#### Performance
#### Reliability


<br>



### Streaming
The article mentioned that streaming is possible with gRPC or a streaming broker like Kafka. So I will be using the [gRPC prototype](https://github.com/Portfolio-Advanced-software/Golang-gRPC-POC) and the [Kafka one](https://github.com/Portfolio-Advanced-software/micro-service-communication-prototype/tree/main/Kafka).

#### Scalability
#### Performance
#### Reliability


<br>



### Binary
I created a prototype using the binary protocol TCP to communicate, it can be found [here](https://github.com/Portfolio-Advanced-software/micro-service-communication-prototype/tree/main/TCP).

#### Scalability
#### Performance
#### Reliability

<br>


### GraphQL
At last I created a prototype using GraphQL to query messages, that one can be found [here](https://github.com/Portfolio-Advanced-software/micro-service-communication-prototype/tree/main/GraphQL).

#### Scalability
#### Performance
#### Reliability
