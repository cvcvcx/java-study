---
날짜: 2024-01-05
주제: Spring Boot로 구현하는 REST API의 어노테이션
설명: 요청 본문 내용과 Bean객체를 연결시켜 값을 받는다
---
> [!NOTE] 사용 시기
> [!NOTE] 사용 시기
> REST API에서 POST요청을 통해 값을 받을 때, 바로 객체에 바인딩하고 싶을 때 사용한다

> [!tip] 사용방법
> ```java
> @PostMapping("/users")  
>  public void createUser(@RequestBody User user){  
 >   }
> ```
> 위와 같이, 
> 요청 본문에 있는 JSON과 바인딩하고 싶은 객체의 앞에 @RequestBody를 입력하여 사용한다

> [!warning] 주의 사항

