# txt

#
AKKA ?  Playframework

# 
reative-streams
Reactor
Spring-MVC 5

#
자바 비동기 개발
서블릿 비동기 개발
	Spring 4 때 까지는 Servlet 에 존재하는 비동기 기능을 이용하여 구현하고 있다.
스프링 비동기 개발 

#
동기? 비동기?

- Singleton "1"
- DI "3"
- Synchronous/Asynchronous "2+"

무엇과 무엇이?
어떤 시간을?

A -> B
시작시간 또는 종료시간이 일치하면 동기
메소드 리턴시간과 결과를 전달받는 시간이 일치하면 동기

블록킹 / 논블록킹은 동기/비동기와 관점이 다르다
- 내가 직접 제어할 수없는 대상을 상대하는 방법
- IO / 멀티스레드 동기화

String res = es.submit(()-> "Hello Async").get(()
es.submit() -> ...) -> 비동기 & 블록/논블럭 논의가 되지 않음
get -> 동기 / 블럭킹 대상




# 스프링 ? @Async

Java 의 Future 는 interface 이지 이것이 동기 처리하도록 하기 위한 부분이 아니다!
Future<String> -> 1.5
ListenableFuture<String> -> Spring 4.0 때에 표준화가 되어있음 -> NIO
CompleteableFuture<String> -> 1.8 표준 -> NIO

비동기는 항상 예의가 문제이다.
-> 예외가 던져졌으면 Exception 오브젝트를 항상 받는다.

@Async가 사용하는 기본 TaskExecutor -> SimpleAsyncTaskExecutor
쓰레드 풀 아님.
@Async 를 본격적으로 사용함ㄴ다면 실전에서 사용하면 안됨.

Executor / ExecutorService / TaskExecutor
TreadPool 설정시 주의할점
-> CorePoolSize를 Core 10 / Max 100 / Queue 50 이면 동시에 50개 요청이 들어오면 10개의 스레드가 생성되고 40개는 queue



