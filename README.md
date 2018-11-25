# Spring Boot 2 + JUnit 5 Sample application

[Check step by step video on YouTube](https://www.youtube.com/watch?v=J9jQoFiP41A)

[![How to setup Spring Boot 2 with JUnit 5](https://img.youtube.com/vi/J9jQoFiP41A/0.jpg)](https://www.youtube.com/watch?v=J9jQoFiP41A)

## 1. Add JUnit 5 Dependencies to pom.xml

```xml
<dependency>
	<groupId>org.junit.jupiter</groupId>
	<artifactId>junit-jupiter-api</artifactId>
	<scope>test</scope>
</dependency>

<dependency>
	<groupId>org.junit.jupiter</groupId>
	<artifactId>junit-jupiter-engine</artifactId>
	<scope>test</scope>
</dependency>
```

## 2. Exclude JUnit 4 from Spring Boot Starter Test

```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-test</artifactId>
	<scope>test</scope>
	<exclusions>
		<exclusion>
			<groupId>junit</groupId>
			<artifactId>junit</artifactId>
		</exclusion>
	</exclusions>
</dependency>
```

## 3. Migrate existing test to JUnit 5

**NOTE:** No need for `@ExtendWith(SpringExtension.class)`

```java
package com.example.demo;

import org.junit.jupiter.api.Test;
import org.springframework.boot.test.context.SpringBootTest;

@SpringBootTest
public class DemoApplicationTests {

	@Test
	public void contextLoads() {
	}
}
```
