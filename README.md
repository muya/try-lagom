# try-lagom
Project to play around with the Lagom Framework: https://www.lagomframework.com/get-started-scala.html

Hello world based off the default template

#### Running the project
1. Ensure you have SBT installed (at least 0.13.13), and Java 8+
2. Clone this repo
3. Enter the `hello` directory
```
$ cd hello
```
4. Run the project
```
$ sbt runAll
```

#### Summary of the Lagom Framework exploration
- Uses macwire for DI (rather than Guice, which is what's in Play) -- Good read: [http://di-in-scala.github.io/](http://di-in-scala.github.io/)
- I'd describe it as a framework for implementing an already thought out & designed micro-service architecture
    - They have very detailed guidelines on how to approach micro-service design (https://www.lagomframework.com/documentation/1.3.x/scala/MicroserviceSystemDesign.html)
- Only seems to support Apache Kafka as the pub-sub system
- They're promoting use of Cassandra for storage, but it supports PostgreSQL, MySQL, Oracle & H2 as well

- Relatively young, just over 1 year old

- Setting up the hello world project took me less than 5 minutes (excluding packages download time), and it shows very easily how things fit together

- The approach is a multi-module SBT project, with each micro-service having an api (handles the contract) & an implementation (service logic)

- Async is by default. Support for different message formats (JSON, protobuf) over different protocols (HTTP, Websockets) - this would allow implementation for use by external systems, as well as other internal services that need to consume it

- I'd recommend going through the core concepts: https://www.lagomframework.com/documentation/1.3.x/scala/CoreConcepts.html
