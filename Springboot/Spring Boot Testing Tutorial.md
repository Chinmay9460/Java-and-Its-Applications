# Testing SpringBoot Applicaitons -->

- We will learn how to write unit, slice and integration tests for my Spring Boot Application.
  We should write Unit Tests to verify the business logic of a perticular unit(a class, a method, or
  a set of classes), and they shouldn't be talking to any external services like database, queue or
  other web services etc. If the unit we are testing depends on any of those external serices, then
  we can provide mock implementations of those dependencies and verify the unit's behaviour.

- In addition to Unit Tests, we should write integration tests which exercise the behaviour of a 
  sub-system or a component by talking to the real services and dependent collaborators.

- When we generate our spring boot application spring-boot-starter-test dependency is automatically
  added which transitively adds the most commonly used testing libraries such as SPringTest, JUnit5,
  Mockito, Assertjm JsonPathm JsonAssert to out application as test dependencies.

# Types of Tests -->
-  ## Unit Tests
    : These are the tests to verify the behaviour of a single unit, and ideally they shouldn't
     depend on frameworks like Spring or Hibernate, etc.

-  ## Slice Tests -->
    : These are tests to verify a slice of a application such as Web layer or Persistence layer etc.
     Spring Boot provides support for testing slices of the application using @WebMvcTest, @DataJpaTest,
     @DataMongoTest etc.

- ## Integration Testng -->
    : These are the tests, which tests the application in a blackbox manner. We pass in some input,
     and we expect specific output, we don’t know or care how it works internally. Spring Boot
     provides support for writing Integration Tests using @SpringBootTest.
