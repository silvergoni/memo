---
title: "java async 사용하기"
date: 2019-04-18 14:55:28 -0400
categories: java
---
## 소개
@Async
- 새로운 thread를 생성하고 실행, 기다리지 않고 종료한다는게 특징
- https://docs.spring.io/spring/docs/current/javadoc-api/org/springframework/scheduling/annotation/Async.html
  - void, Future(ListenableFuture, CompletableFuture) 리턴타입 지원
  - A Future handle returned from the proxy will be an actual asynchronous Future that can be used to track the result of the asynchronous method execution. However, since the target method needs to implement the same signature, it will have to return a temporary Future handle that just passes a value through
  - 특정 Executor 또는 TaskExecutor Bean 정의의 한정자 값 (또는 Bean 이름)과 일치하여이 메소드를 실행할 때 사용할 대상 executor를 결정하는 데 사용할 수 있습니다.
  
## 사용방법
@EnableAsync
- @Async를 감지
- EJB 3.1javax.ejb.Asynchronous; 이 옵션으로 사용자 정의된 다른 어노테이션 또한 감지

## 규칙
- Element.TYPE, Element.METHOD에서 사용가능
- method일경우, public이어야함.
- self invocation 불가
  - 프록시을 타지않고 바로 호출하기 때문이다.
  
  
  
# reference
https://docs.spring.io/spring/docs/current/spring-framework-reference/core.html#aop-understanding-aop-proxies
https://www.baeldung.com/spring-async
