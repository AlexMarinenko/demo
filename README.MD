
1. Add dependencies:

```xml
<dependency>
    <groupId>com.gamingtec.services.auth</groupId>
    <artifactId>auth-core</artifactId>
    <version>1.0.1</version>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-oauth2-resource-server</artifactId>
</dependency>
```

2. Add annotation `@EnableIDMAuthentication`

```java
@EnableIDMAuthentication
@SpringBootApplication
public class Service1Application {

    public static void main(String[] args) {
        SpringApplication.run(Service1Application.class, args);
    }

}
```

3. Add configuration section into `application.yml`:

```yml
idm-auth:
  enabled: true
  base-url: https://auth-dev.gmntc.com

spring:
  security:
    oauth2:
      resourceserver:
        jwt:
          issuer-uri: https://auth-dev.gmntc.com
```

4. 