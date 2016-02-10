# config-broker

Multi-Application centralised configuration manager

Most enterprise applications will define a number of configuration variables such as database connections, external service URLs, passwords, etc. These are generally buried in text files (Java properties, XML, YAML,JSON, etc) in the application servers. In some cases, they are manually edited/created during the deployment in other cases they are created by deployment scripts in which the values are hardcoded, including sensitive values like passwords.

With config-broker the application will only need at most the one parameter, the URL of the config-broker, to access the configuration during start up. All the configurations will be stored and maintained in the config-broker, which will ensure that only authorized applications access the configurations. See the security section for more details on this. 


This is an attempt to solve the problem described in http://stackoverflow.com/questions/25333337/configuration-management-server-for-java-enterprice-application.  

## Features
 * Configuration Management, versioned per application and environment
 * REST API
 * Bulk loading of configurations in JSON, Java Properties, EDN, YAML formats
 * Authentication support: ssh pub-key, temporary keys (for deployment window)
 * Password generation
 * Client library for integration with Spring, Java, and other languages


## Security

There's a chicken and egg problem when it comes to authorize applications to access a particular config-set from the config-broker. 
Let's see some alternatives on this:
* Applications are initialised with some credentials in order to access the config-broker. 
* Applications use a temporary single use key to bootstrap trust relationshipt with the broker.

 
