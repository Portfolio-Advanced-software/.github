# Which technique is the most optimal way of communicating between micro services?
To answer this question I'm going to divide it into sub questions and answer them first and it will result in answering the main question.





## Which techniques for micro service communication are available?


### Literature study 
To come up with as many ways for communication between micro services I consulted the internet and did a community search. I red some articles that discussed different ways of communicating and wrote them down.

#### Web
- HTTP (protocol)
- message communication (pattern)
- event-driven communication (pattern)   

source: https://blog.logrocket.com/methods-for-microservice-communication/

- HTTP
- gRPC
- message brokers AMQP protocol

source: https://medium.com/design-microservices-architecture-with-patterns/microservices-communications-f319f8d76b71

- Streaming Integration

source: https://levelup.gitconnected.com/4-ways-to-establish-communication-between-microservices-984207f29497

- HTTP
- AMQP
- binary protocol like TCP   

source: https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/communication-in-microservice-architecture


#### Community/forum
- Azure Service Bus
- Azure Event Grid

source: https://www.reddit.com/r/microservices/comments/hl9rww/microservices_servicetoservice_communication/





If I translate them down to the same category I get the following list that I will be researching further

- REST
- RPC
- Messaging
- Event driven communication
- Streaming
- binary 


## What are the advantages and disadvantages of each communication technique?

### REST
#### Advantages
- If you need a request/response protocol then REST is good option to do this. It's also a disadvantage if you need more than that. 
- Beside that it's very compatible, because you can implement it in every programming language, because it uses the basic HTTP protocol.

source: http://www.myspsolution.com/news-events/rest-vs-messaging-for-microservices-which-one-is-best/

#### Disadvantages
- Because it is request response it is only linked to one service most of the time so with expansion you need to exclusively link it to a new service. 
- Like discussed earlier you send out a request and wait for a response, so this can become a problem when there are a lot of requests and every request has to wait for the request in front of them to get a response.
- ```Error Handling - HTTP was built for the web and we have all seen our browsers get stuck trying to access a webpage. Usually we click the refresh button and the page displays. But what if it fails again? Try to refresh again? Does one start to implement a human form of exponential back off by getting a cup of coffee and trying again in a few minutes? We do not know what to do as every webpage is different and has unique behavior. The same type of issue occurs when directly invoking a RESTful service. Should this complex retry logic reside in a service's code? If it does the service is even more tightly coupled to other services - again violating the key principle of keeping microservices architecture single in purpose and small in size.```

source: http://www.myspsolution.com/news-events/rest-vs-messaging-for-microservices-which-one-is-best/

### Messaging
#### Advantages
- With messaging you can use a publish subscribe system where the service just subscribes to a channel and will get notified when the publisher sends out a new message. so you're not waiting anymore for a response and this can be asynchronous. This means that you can easily scale services because they're not waiting for a response on each other.
- This also means that a services only has to subscribe to a channel and this doesn't involve doing a lot of technical stuff in the back-end. This makes it easier for expansion.
- Because messaging allows for data queues and guarenteed message deliveried the data is not lost when a services fails after transmitting the message. Therefore a service can come back online and continue as before.

source: http://www.myspsolution.com/news-events/rest-vs-messaging-for-microservices-which-one-is-best/

#### Disadvantages

## What is the role of message brokers?
## What is the role of API gateways in micro service communication?
## How does service discovery work to ensure communication between unknown micro services?
## What is the impact of containerization on micro service communication?
## How does the choice of communication protocol impact the performance and scalability of microservices?
## How can micro service communication be secured to prevent unauthorized access?
## What are the best practices for testing and monitoring microservice communication to ensure reliability and performance?
