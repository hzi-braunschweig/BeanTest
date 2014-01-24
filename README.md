# Bean Testing for JEE Applications using CDI

This project attempts to show an interesting approach on testing JEE
Applications. It uses a CDI Container to resolve dependencies like EJBs or
Resources when running unit test in a standard environment.

The name "Bean Testing" is used, since it isn't about proper unit tests.
However, the feedback speed is very close to unit test and the tests look
undistinguishable too.

**Main advantages:**

-   Very fast test feedback (very close to unit test feedback speed).

-   Dependencies are solved automatically without the need of a JEE Application
     Server (or Embedded Server).

-   Everything is CDI so you can easliy extend the functionality.

-   You get basic transaction propagation support.

-   You can provide your own mocks to test external dependencies.

-   You use the usual stuff for configuration: persistence.xml, beans.xml,
     Junit, etc.

**Examples**

You can find the examples about how a "Bean" test looks like under
*src/test/java* (look for classes whose names begin with Test\*)

## How to use it

1.  Just clone the project and build it (mvn clean install)

2.  Add the dependency to your pom with *test* scope.

3.  Write a test similar to the ones in the examples using your production code.

4.  Depending on your project structure, you might get an
     *UnsatisfiedResolutionException* if some classes are not available in your
     classpath. You can solve this by providing a Mock (See the mock example for
     this).

## Why you should use it

First of all, this approach is neither a replacement for unit nor integration
tests. This approach is something in the middle.

You should always write unit tests for essential business logic.

You should always write integration tests to check that everything works as
expected.

So, why use this approach? Because you get the best of both worlds: You get the
speed of unit tests with almost the coverage of integration tests and all this
with minimal configuration and with standard and well known frameworks like JPA,
CDI, Mockito and Junit.

Since you don't need an application server for running your tests, you can
integrate them in your normal unit test build process. In this way, you get
almost integration test coverage in your normal builds.

### Requirements

-   JDK 6 and above.

-   Maven

### Contribute

Just fork.
