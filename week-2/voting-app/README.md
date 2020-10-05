# Voting Demo Application

Despite the simple way to run (`docker-compose up -d`), it's a complex scalable distributed microservices-oriented application.

It consists of three services:

* [Voting Fronted](./voting) - python application to vote. Available on `port 5000` by default. Sends votes to a redis queue.
* [Worker](./worker) - java worker processing votes in background. Gets tasks from redis queue and stores processed votes to PostgreSQL database.
* [Result](./result) - NodeJS app to show vote results. Reads processed data from PostgreSQL. Available on `port 5001` by default.

![image](https://user-images.githubusercontent.com/1742301/95069792-7a1fc500-0707-11eb-9a8c-e806af5e0e4f.png)
