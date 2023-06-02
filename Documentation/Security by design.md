# Security by design

- Access only the data that users have access to
- 




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

