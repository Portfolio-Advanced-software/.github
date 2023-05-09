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


```
1. Easy to integrate
A decent RESTful API may be found from the very first URI. This isn’t to say that each application that uses your service will know what to do automatically. It does, however, make things easier for the developer who is attempting to connect your API.


4. Independence
Because of the separation between client and server, the REST protocol allows for autonomous development across several sections of a project. Furthermore, the REST API is adaptable to operational syntax and platform. This allows testing in a variety of contexts throughout development.

5. Uniform Interface
When creating a REST API, developers agree to follow the same standards. Hence, the output is a consistent interface across all APIs. This interface functions as a contract between the client and the service, and it is shared by all REST APIs. How is this useful? When developers utilize APIs, they require global ideas to ensure that they can communicate with one another.

6. Layered System
Every REST-enabled component has no access to components other than the one with whom it is communicating. This means, that a client who connects to an intermediary component does not know with whom that component will engage later. This encourages developers to design separate components that are easy to upgrade.
```

source: https://qodeify.com/advantages-of-restful-api/

#### Disadvantages
- Because it is request response it is only linked to one service most of the time so with expansion you need to exclusively link it to a new service. 
- Like discussed earlier you send out a request and wait for a response, so this can become a problem when there are a lot of requests and every request has to wait for the request in front of them to get a response.
- ```Error Handling - HTTP was built for the web and we have all seen our browsers get stuck trying to access a webpage. Usually we click the refresh button and the page displays. But what if it fails again? Try to refresh again? Does one start to implement a human form of exponential back off by getting a cup of coffee and trying again in a few minutes? We do not know what to do as every webpage is different and has unique behavior. The same type of issue occurs when directly invoking a RESTful service. Should this complex retry logic reside in a service's code? If it does the service is even more tightly coupled to other services - again violating the key principle of keeping microservices architecture single in purpose and small in size.```

source: http://www.myspsolution.com/news-events/rest-vs-messaging-for-microservices-which-one-is-best/


```
1. Increased design complexity.
Although they are easier to use, the design of a REST API can be more complex than other APIs, especially if you are not familiar with web architecture. 

The REST API uses architectural principles that you need to be familiar with in order to develop your API.

2. Web connection
All changes to your REST API must be executed on the web and only on the web. It’s impossible to edit the API from your desktop without an internet connection, unlike HTML web files, for example. You must always connect to make the slightest change.

A REST API requires an Internet connection to function, which means it may be less useful in offline environments.

3. Variable performance and flexibility
On the other hand, REST APIs can have slightly lower performance than other APIs, depending on the servers and their internet speed.

And in some cases, a REST API may be less flexible than other APIs because of the same architectural principles it must follow. 

In other words, although its architecture is quite versatile and can be synchronized with other applications, the development of this architecture is less flexible.

Despite its unfavorable points, REST APIs are a must-have for web developers and companies worldwide. 

This is the API of choice for millions of companies and development teams, so knowing it will give you access to countless opportunities. 

At the same time, we recommend you to complement your repertoire of tools with other API models, as well as programming languages. 

You can start with HTML and JavaScript and their different formats, such as Node.JS JSON, and if you want to go a step further, you can delve into Python and more complex languages such as C and C++.

Also, if you want to become a web development specialist, we invite you to check out our training and boot camps.


```

source: https://www.thepowermba.com/en/blog/rest-api-what-is-it-how-does-it-work-advantages-and-disadvantages
### RPC




### Messaging
#### Advantages
- With messaging you can use a publish subscribe system where the service just subscribes to a channel and will get notified when the publisher sends out a new message. so you're not waiting anymore for a response and this can be asynchronous. This means that you can easily scale services because they're not waiting for a response on each other.
- This also means that a services only has to subscribe to a channel and this doesn't involve doing a lot of technical stuff in the back-end. This makes it easier for expansion.
- Because messaging allows for data queues and guarenteed message deliveried the data is not lost when a services fails after transmitting the message. Therefore a service can come back online and continue as before.

source: http://www.myspsolution.com/news-events/rest-vs-messaging-for-microservices-which-one-is-best/

#### Disadvantages



### Event driven

### Streaming

### Binary



## What kind of things does the way of communication have impact on as well?
The previous question answered some of the 



## How can we monitor these things and test it?

