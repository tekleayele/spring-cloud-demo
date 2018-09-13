# Spring Cloud Services
This repository contains samples apps which can be deployed to a Pivotal Cloud Foundry environment installed with Spring Cloud Services. There are two application categories, service and client. 

## Hello Service
hello-service is a REST service which returns a hello world message, whose value is configurable. There are three versions of this application:
* [hello-service](hello-service): returns a value configured via configuration on the classpath under resources
* [hello-service-config-server](hello-service-config-server): uses the Configuration Service to configure the hello message as well as log levels. 
* [hello-service-eureka](hello-service-eureka): The same service above, but registers itself with the Service Registry

## Hello Client
hello-client is a REST service which makes a call to hello-service and responds with that hello message. 
* [hello-client](hello-client): makes a call to hello-service with a locally-configured URI
* [hello-client-eureka](hello-client-eureka): makes a call to hello-service with a URI provided by the Service Registry. Requires [hello-service-eureka](hello-service-eureka) to be running.
* [hello-client-hystrix](hello-client-hystrix): same as above, but uses the circuit breaker pattern to return a fallback response in case the hello-service is not reachable. 

This repo has been optimized for IntelliJ primarly but can easily be refactored to support eclipse or any other populate Java IDEs. 





