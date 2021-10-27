# App

This is a repository containing a simple node app (api, web) that will be used for K8S-CICD (https://github.com/DaviAraujoCC/K8s-CICD)

These two variables need to be set with docker-compose (WEB_PORT, API_HOST).

Functionality:
![image](https://user-images.githubusercontent.com/70732391/128958652-af2d1ed4-5506-4341-9884-c61c2cd6fb9b.png)

As you can see this application is made up with 3 containers, one for database, another for api and the last for web access, to test the application you can use the docker-compose to build the environment, and test acessing localhost:8080 , in short all three containers need to be working and configured correctly (env variables), if one fails it will return an error. 


fork from repository https://github.com/samcavallieri/devops_challenge