# Introduction to Spring Boot
  '''
    
    Spring Boot is the most popular framework for building applications in the Java world.
    Springboot is an Opinionated an Convention Over Configuration based approach to building Spring
    framwork based applications.
    
    Using Spring Boot, you can build different kinds of applications such as monolithic applications, microservices, serverless applications, Batch applications, etc.
    Let us take a quick look at what are the key features of Spring Boot that make it so popular.
    
  '''

# Spring Boot Key Features
## AutoConfiguration --> 
  '''
  
    Spring Boot takes an opinionated view of the application and auto-configures the components(a.k.a beans) based on the default conventions without requiring you to configure everything explicitly. However, you can customize 
    or override the bean configurations in various ways if required. For example, if you add spring-boot-starter-data-jpa dependency it will add Hibernate as the JPA implementation as it is the most commonly used JPA provider. 
    Also, Spring Boot tries to auto-configure the components required for using Spring Data Jpa such as DataSource, EntityManagerFactory, PlatformTransactionManager etc. If there is an in-memory JDBC driver in the classpath 
    like H2 or HSQL then Spring Boot will auto-configure the DataSource with in-memory settings. If you want to use any non in-memory databases like MySQL, Postgresql etc then you can add the respective JDBC driver jar and configure 
    the JDBC connection parameters in application.properties file. Then Spring Boot will use those properties to configure DataSource bean as opposed to using default in-memory database. You can even configure a DataSource bean by 
    yourself using @Bean annotation then Spring Boot will backoff and use the DataSource bean configured by you instead of auto-configuring it.With Spring Boot’s auto-configuration, the need for Spring application configuration is 
    greatly reduced.

  '''
## Convention Over COnfiguration -->
  '''

    Spring Boot relies upon various default conventions so that it can auto-configure the application.For example, in most of the Spring based (not Spring Boot based) applications we use configuration properties and register the 
    PropertySourcesPlaceholderConfigurer bean. In Spring Boot you can put your configuration properties in src/main/resources/application.properties file and Spring Boot will automatically register PropertySourcesPlaceholderConfigurer 
    bean loading the properties from that file. You don’t have to explicitly specify the properties file name. Similarly, you might want to configure different values for properties based on environment (dev, qa, staging, prod). 
    You can configure your configuration properties in application-{profile}.properties where profile can be dev, qa, staging and prod. Then you just need to enable the desired profile for Spring Boot to read values from that specific 
    profile properties file. Spring Boot is very flexible to customize those conventions based on your project or team preferences.
  
  '''
## Dependencies Version Management -->
    '''
    
    Typically, Spring Boot applications inherit from spring-boot-starter-parent which is configured with all the compatible library versions so that you don’t have to hunt for checking which library version is compatible with which version 
    of Spring. You can check pom.xml of org.springframework.boot:spring-boot-dependencies module to see what are all the libraries pre-configured.Production Ready Monitoring Capabilities Monitoring is an important aspect of any application 
    running in production. Spring Boot provides production ready monitoring capabilities via Actuator. You can get the application runtime information like Memory usage, Disk Space, HealthCheck of various components etc via Actuator REST 
    endpoints. Actuator uses Micrometer under-the-hood which you can use to export all those application metrics to various monitoring services like Prometheus, Datadog, Influx etc.

    '''
## Embedded Servers Support -->
'''

    Traditionally, Java based web applications are built as war files and then deployed on a servlet containers or application servers like Tomcat, Wildfly, WebSphere etc. The modern approach is to embed the server runtime within the application
    itself so that you can take the artifact and run it without having to install and configure server externally. Spring Boot provides support for embedding servlet containers like Tomcat, Jetty, Undertow and you can customize various server 
    properties in server-independent way. Spring Boot also provides various server-specific customization properties as well.
    
'''

## Spring EcoSystem -->
  Spring Boot has a hug ecosystem of projects to support wide verity of application types.
  - ### SpringMVC & Spring WebFlux:
      You can build traditional web applications and RESE APIs using SpringMVC or Spring WebFlux.
  - ### Spring Security :
      You can implement Authentication and Authorization using Spring Security. It also supports implementing OATH 2.0 based security.
  - ### Spring Batch:
       You can build robust batch applications using SpringBatch.
  - ### Spring Integration:
      Spring Integration implements many of the Enterprise Integration Patterns which you can use for integration with 3rd party services.
  - ### Spring Cloud:
      Spring Cloud provides support for building Cloud Native applications following 12 Factor Application principles
  - ### Spring Cloud Streams:
      You can build Data Pipelines for processing Stream based Data Sources like Kafka.
