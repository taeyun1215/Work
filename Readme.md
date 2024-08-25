# Spring Lambda MVP

## 개요

`spring-lambda-mvp` 레포지토리는 Spring Boot 애플리케이션을 AWS Lambda 함수로 배포하기 위한 최소 기능 제품(MVP)을 시연하기 위해 설계되었습니다. 이 프로젝트는 사용자 등록, 로그인 및 사용자 정보를 가져오는 기본적인 기능을 포함하고 있으며, 서버리스 실행을 위해 AWS Lambda와 통합되었습니다. 또한, HTTP 인터페이스 노출을 위해 AWS API Gateway를 사용하고, OpenAPI 사양 및 기타 아티팩트를 저장하기 위해 S3를 활용합니다.

## 레포지토리 구조
```css
spring-lambda-mvp/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── example/
│   │   │           └── demo/
│   │   │               ├── handler/
│   │   │               │   └── StreamLambdaHandler.java
│   │   │               └── user/
│   │   │                   ├── User.java
│   │   │                   ├── UserController.java
│   │   │                   ├── UserRepository.java
│   │   │                   └── UserService.java
│   │   └── resources/
│   │       └── application.yml
├── build.gradle
└── gradlew
```

## 주요 파일 설명

- **`StreamLambdaHandler.java`**: AWS Lambda와의 통합을 처리하는 핸들러 클래스입니다.
- **`UserController.java`**: 사용자 등록, 로그인, 사용자 정보 조회 등의 API 엔드포인트를 제공하는 컨트롤러입니다.
- **`UserService.java`**: 사용자 관련 로직을 처리하는 서비스 클래스입니다.
- **`UserRepository.java`**: 사용자 데이터를 관리하는 리포지토리 인터페이스입니다.
- **`User.java`**: 사용자 정보를 담고 있는 데이터 모델 클래스입니다.
- **`application.yml`**: 애플리케이션 설정을 담고 있는 파일로, 데이터베이스 연결 정보 등이 포함되어 있습니다.

## StreamLambdaHandler 클래스

`StreamLambdaHandler` 클래스는 AWS Lambda에서 Spring 애플리케이션을 실행하기 위한 핸들러입니다. 이 핸들러는 AWS의 요청을 받아 Spring 컨텍스트로 전달하고, 응답을 처리하는 역할을 합니다.

### 코드 예시

```java
public class StreamLambdaHandler implements RequestStreamHandler {
    private static final SpringLambdaContainerHandler<AwsProxyRequest, AwsProxyResponse> handler;

    static {
        try {
            handler = SpringLambdaContainerHandler.getAwsProxyHandler(PetStoreSpringAppConfig.class);
        } catch (ContainerInitializationException e) {
            // If we fail here, re-throw the exception to force another cold start
            e.printStackTrace();
            throw new RuntimeException("Could not initialize Spring framework", e);
        }
    }

    @Override
    public void handleRequest(InputStream inputStream, OutputStream outputStream, Context context)
            throws IOException {
        handler.proxyStream(inputStream, outputStream, context);
    }
}
```

### 설명

- **SpringLambdaContainerHandler**: AWS Lambda에서 Spring 애플리케이션을 실행하기 위한 핸들러입니다.
- **PetStoreSpringAppConfig**: Spring 애플리케이션의 설정 클래스를 지정합니다.
- **handleRequest 메서드**: AWS Lambda가 호출될 때마다 실행되어, 입력 스트림을 받아 Spring 컨텍스트로 전달하고 결과를 출력 스트림으로 반환합니다.
- **ContainerInitializationException**: 초기화 중 문제가 발생하면 예외를 발생시켜 Lambda를 다시 시작하도록 합니다.

### 참고 자료

이 코드는 [AWS Serverless Java Container 프로젝트](https://github.com/aws/serverless-java-container/tree/ad70c3dc22586d72dc019db8fdb6b118bad5dd07)에서 제공된 예제를 기반으로 하고 있습니다. 이 예제 코드는 Spring 애플리케이션을 AWS Lambda 환경에서 원활하게 실행할 수 있도록 설정하는 방법을 보여줍니다.

## GitHub Actions 연동

이 레포지토리는 `lambda-trigger-pipeline` 레포지토리와 연동되어 있으며, 코드가 푸시되면 자동으로 해당 레포지토리의 워크플로우가 트리거 됩니다. 이를 통해 서버리스 환경에서 Spring Boot 애플리케이션을 손쉽게 배포할 수 있습니다. GitHub Actions는 전체 파이프라인을 자동화하여 개발자가 코드 변경 시 빠르고 효율적으로 배포를 진행할 수 있도록 지원합니다.
