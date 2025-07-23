# A simple MERN stack application 

##  Create a network for the docker containers <br>

`docker network create demo`



## Build the client 

```sh
cd mern/frontend
docker build -t mern-frontend .
```

## Run the client

`docker run --name=frontend --network=demo -d -p 5173:5173 mern-frontend`

## Verify the client is running

Open your browser and type `http://localhost:5173`

## Run the mongodb container

`docker run --network=demo --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongodb:latest`

## Build the server

```sh
cd mern/backend
docker build -t mern-backend .
```

## Run the server

`docker run --name=backend --network=demo -d -p 5050:5050 mern-backend`

<br>

# Instead of Doing the above all , we can just use one command to do all of those that is Docker Compose

`docker compose up -d`

### Finally we have created Three tier application into containers and merge them in a network using docker compose!




## Got any Problem! no worries

## 1. If you do these all in EC2 instance, Make sure you configured Inbound rules in aws console
```
     {
        Go to EC2 -> Security Groups -> add inbound traffic for the above ports!
     }
```
