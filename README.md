## Express Mongoose docker(Mongo Mongo-Express) CRUD App

#### global

`npn install -g express generator`

#### in home dir user~

`express --view=ejs crudjs`

#### enter directory

`cd crudjs`

#### setup

`npm install mongoose`

#### docker setup for mongo and mongo express

```bash
  docker pull mongo
  docker pull mongo-express
  docker network create mongo-network
  docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo

  docker run -d -p 8081:8081 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express
```

#### to stop mongo and mongo-express

`docker ps -a`

#### stop mongo-express forst

`docker stop d9832ds02`

`docker stop 1jd902392`

#### to restart mongo and mongo-express

`docker start d9832ds02`

`docker start 1jd902392`

#### mount container for command line access

`docker container exec -it d9832ds02 /bin/bash`

`mongosh admin -u admin -p password`

#### Mongo express from localhost

[http://localhost:8081/](http://localhost:808)


#### mongoose conection 

```bash
mongoose.connect("mongodb://localhost:27017/test", {
authSource: "admin",
user: "admin",
pass: "password",
});
```

#### running app

`npm run start`

#### browser access

[http://localhost:3000/](http://localhost:3000/)




