This project is a minimal but functional OAuth2 Authorization Server
(token issuer) and Resource Server (protected API). (You could split
the two roles across two applications if you preferred.) It uses
[Spring Boot](https://github.com/spring-projects/spring-boot) to
provide an embedded servlet container and for defaulting a load of
configuration, so you should be up and running with it very
quickly. There are integration tests proving that it works and also
showing you how to access it with the Spring `RestTemplate` API.

## Building

You need Java (1.7 or better) and Maven (3.0.5 or better):

```
$ mvn clean install
$ mvn spring-boot:run
...
<app starts and listens on port 8080>
```

Here are some curl commands to use to get started:

```
$ curl -H "Accept: application/json" my-trusted-client@localhost:8080/oauth/token -d "grant_type=password&username=user&password=password"

$ curl -H "Authorization: Bearer $TOKEN" localhost:8080/
Hello World
```
