# Devops Web app 

### Lembrar de instalar os pacotes npm

### Requeriments

- PORT: the listening PORT
- API_HOST: the full url to call the API app. An example http://web-api-host:port

These two variables need to be set with docker-compose (WEB_PORT, API_HOST).

fork from repository https://github.com/samcavallieri/devops_challenge

Functionality:
![image](https://user-images.githubusercontent.com/70732391/128958652-af2d1ed4-5506-4341-9884-c61c2cd6fb9b.png)

As you can see this application is made up with 3 containers, one for database, another for api and the last for web access, to test the application you can use the docker-compose to build the environment, and test acessing localhost:8080 , in short all three containers need to be working and configured correctly (env variables), if one fails it will return an error. 

