# spring cloud configuration server
- This is a test project represent cloud configuration server between many microservices to hold
each service configuration.
- This project read the configuration files for different services from git repository https://github.com/maboalim/microservice-config.git to be published to other services under port 8888
- The configuration files determine the stage of the application (dev, qc, prod, ...)

# Examples
URL examples:
http://localhost:8888/limits-service/dev
http://localhost:8888/limits-service/default
http://localhost:8888/currency-exchange-service/qc

# Summary
This project is part from some projects created for testing microservice cloud. Those projects are
- spring-cloud-config-server

This service load the configuration for the microservices from repository on github called microservice-config and expose it as web services to be called by other microservices

- eureka naming server

This is a naming server to register the microservices on it to be able to
retrieve the URLs for different microservices by microservice name which defined inside application.properties file

- zuul-api-gateway-server

This is a gateway server to handle the authentication/authorization and the communication between microservices.
This project is created without implementing the business for authentication/authorization for testing.
This service register itself in eureka naming server.
The API gateway know the services URLs which should be called for each request from the eureka naming server
 
- limits-service

This service used to test loading configuration from spring-cloud-config-server. It is also used to test the hystrix and resilience circle breaker for fault tolerance
This service register itself in eureka naming server.

- currency-exchange-service

This service used to test the rest template, feign rest client, rubbon client load balancer. It callect the currency exchange rate information from external API
This service register itself in eureka naming server.

- currency-conversion-service

This service used to call the currency-exchange-service to get the currency exchange rate.
This service created to test the rest template, feign rest client, rubbon client load balancer.
This service register itself in eureka naming server.


Tested inside those projects:
- JPA
- Spring cloud configuration server read from git repository
- Rest template
- Feign rest client 
- Ribbon client load balancer
- Eureka naming server
- Zuul api gateway
- Spring cloud sleuth to add unique ID to logs
- Zipkin distributed tracing system using Rabbit MQ [required rabbitMQ and zipkin to be running]
- Hystrix and resilience circle breaker for fault tolerance.

