# JHipster Microservices demo from Devoxx US 2017

To run this microservices architecture locally, you'll need to install Java 8, Maven, Node.js and Docker. Then run the following commands in separate windows:

Terminal 1:
```bash
cd registry
./mvnw
```

Terminal 2:
```bash
cd blog
yarn
yarn webpack:dev
./mvnw
```

Terminal 3:
```bash
cd store
docker-compose -f src/main/docker/mongodb.xml up
```

Terminal 4:
```bash
cd store
./mvnw
```

## Docker ##

To run this application using Docker Compose, run the following commands:

```bash
cd blog 
./mvnw package -Pprod docker:build
cd ../store
./mvnw package -Pprod docker:build
cd ../docker
docker-compose up -d
```

Then use Kitematic to visualize the logs and find the URL for each application.
