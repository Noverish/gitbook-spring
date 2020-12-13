# 1.5. application.properties

src/main/resources 경로에 application.properties라는 빈 파일이 하나 있습니다. 이 파일에서는 Spring과 관련 Dependency에 관한 다양한 설정들을 적는 곳이고, 프로젝트 곳곳에서 쓰이는 커스텀 설정도 넣을 수 있습니다. 어떤 설정이 있는지는 [문서](https://docs.spring.io/spring-boot/docs/current/reference/html/appendix-application-properties.html)를 참고해 주세요.

```text
my.custom.property: Hello, World!
```

아래 내용을 하기 전에 application.properties에 위 내용을 추가해 주세요.

## 1\) @Value 어노테이션

```java
import org.springframework.beans.factory.annotation.Value;

public class DemoApplication {
	@Value("my.custom.properpty")
	private static String property;

	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
		System.out.println("property: " + property);
	}
}

```

## 2\) 환경 변수 사용하기

```text
server.port=${PORT}
```

