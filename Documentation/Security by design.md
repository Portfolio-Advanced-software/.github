# Security by design

## OWASP
OWASP stands for The Open Worldwide Application Security Project and it's main goal is to improve the security of software all over the world. They provide a standard top 10 document for every developer. I will be using this document to select what is importing to take into account for my individual project BingeBuser, a netflix clone.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/f4fbc04a-47bb-4aa4-8bbc-47730e628279)


### 1. Broken Access Control 
Risk: The first one is already relevant, because of manipulating data without the right permission could cause serious harm in my application. Like removing movies which the whole platform relies on it. This could also result in exposing personal information and a privacy debreach.

Solution: A simple way is to deny every access point by default, I don't have public ones so this would be an easy way to already cover some risks.


### 2. Cryptographic Failures 
Risk: Exposing encrypted values, this could happen it my application uses old hashing methods or with a default key, but also transporting sensitive information on non-encrypted communication protocols like HTTP. 

Solution: It's better to use HTTPS or TLS and check if hashing methods are out of date.


### 3. Injection
Risk: This one is a bit less risky, because I don't have post requests on every api endpoint and I'm not using SQL. SQL is a bigger risk then NoSQL or at least that's what I'm noticing around the internet and the OWASP site. 

Solution: I could implement escaping special characters, but in a manner this also has to do with access control, if you can't get to it in the first place you don't have to worry about it.


### 4. Insecure design 
Risk: I think it's good to see implementing security as a process, meaning while developing looking at it in different phases of the development. I also noticed that exposing credentials online is irreversible, so you can never take it back so setting this up from day one is a good implementation.

Solution: Spend time thinking about security aspects in your project and look into when it is important and how to begin with it.


### 5. Security misconfiguration
Risk: Exposable information that gets exposed in your code or by other settings, like not used features or default credentials. This could be a risk for my application as I installed a lot of dependencies and am not sure if I still use them. I also haven't changed my basic credentials from my cloud providers.

Solution: Change all credentials with a password generatore and don't store on public accesible storage. Also do a dependency check. 


### 6. Vulnerable and Outdated Components
Risk: having outdated dependencies or outdated versions, this could lead to security risks that are discovered in that specific version. 

Solution: Normally I just grab the lastest version, but sometimes when following a tutorial I might unawerely use an older version. I already implemented static security checks that I will discuss later in this document. This helps shine some light on these risks.




### 7. Identification and Authentication Failures
Risk:

Solution:


### 8. Software and Data Integrity Failures
Risk:

Solution:


### 9. Security Logging and Monitoring Failures
Risk:

Solution:


### 10. Server-Side Request Forgery (SSRF) 
Risk:

Solution:



# Sonarcloud



## WatchHistory-service
First report

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/e3ca7930-e4fe-4d68-a19e-7e7b1f37a9a1)



## Auth-service
First report

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/7d7f96fd-d8d0-4986-be3d-42defa5a850d)

It says to not let it build and run with root user permissions therefore i started to look what it is and how to fix it.

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/bdcd7628-df16-4023-bd95-bc4e2987c0f4)

[this forum post](https://stackoverflow.com/questions/68155641/should-i-run-things-inside-a-docker-container-as-non-root-for-safety) cleared it up

by adding this line I create a user that will be used to start the docker and resolving the security risk
![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/4aa4bb11-cbc4-4806-84d3-ddda1643074d)



## Movie service
First report

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/79626c00-14d9-4bc2-a44b-705a0e164cbc)


I already knew I got to fix this and therefore I'm not surprised this came back
![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/21128cea-5f5d-4c55-8ed9-d3a3b0400757)


I already worked with environment variables but I deleted them when building my pipeline because I didn't how to use it in there. I know saw on this [post](https://www.reddit.com/r/github/comments/13kfg0s/what_is_the_proper_way_to_hide_sensitive/) that you could store them somewhere in the cloud encrypted. It seems like a good and easy managable way to handle this. Firstly I will store them in an environment file for cleannes and better handling, by [this](https://towardsdatascience.com/use-environment-variable-in-your-next-golang-project-39e17c3aaa66). But unfortunately Azure for students fontys has managed the restrictions very poorly therefore I could not find the why I don't have access to my own created resource. So I went back by just using a .env file and putting that one in my .gitignore. 

And I will be using github actions secrets with enviroment variables for the docker and passing the variables when starting.



![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/faf72a81-fbfe-474e-b10f-ef4c5fa526a2)

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/67e88248-c0a4-45ad-a89c-d085489a61ba)



I also got some duplicated code warning that i fixed by creating a function so i can reuse the rabbitmq functionality connect 

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/a3bd7eb2-66cb-4260-a6e4-757b9e063800)

And at last this one but It's my own repo therefore I trust all its content
![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/c0588926-e465-470f-8a20-ccdb769a8ae1)




The rest was the same




# Snyk


## Api gateway

analyze after sonarcloud
![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/1d7e5e28-d55b-48a7-972c-44f5edb0cfe9)


I need to upgrade the alpine version to fix some dependencies issues it already created a pr so I'm going to try to use this


After fixing it with the pr
the only issues left are outdated dependecies
![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/99b4b0b8-a75f-4777-be30-f89a3f10ab63)

I manually fixed them

I got a new one I studied it closely and It seems this security risk is only involved in using SQL lite which I don't

![image](https://github.com/Portfolio-Advanced-software/.github/assets/73555911/222cc0bd-7c80-4dd2-a3f5-a4e24eb50455)



While looking around I came across owasp dependency checks but I saw that snyk already did this
