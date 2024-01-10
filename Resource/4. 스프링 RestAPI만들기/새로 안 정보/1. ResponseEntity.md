---
날짜: 2024-01-05
주제: Spring Boot REST API
설명: 응답코드와 location값을 수정할 수 있다.
---
> [!NOTE] 사용 시기
> http의 응답코드를 원하는대로 설정하고, location을 설정할 때 사용한다.
> 

> [!tip] 사용방법
> ResponseEntity.원하는응답코드(응답으로 보여주고싶은 정보가 담긴 URI).build를 리턴값으로 넘긴다

# 🚀 구체적인 코드
```java
@PostMapping("/users")  
public ResponseEntity<User> createUser(@RequestBody User user){  
//지금 service에서는 반환값으로 생성된 User의 id가 담긴 User객체를 보내고 있다.
    User save = service.save(user);  
    // 생성된 유저의 정보가 담긴 URI를 전달하고자 아래와 같이 작성한다.
    URI location =  
    //ServletUriComponentsBuilder를 이용하면 현재 요청 URL에 원하는 id값을 추가해서 
    //URI를 만들 수 있다.
            ServletUriComponentsBuilder.fromCurrentRequest()  
                                         .path("/{id}")  
                                         .buildAndExpand(save.getId())  
                                         .toUri();  
    return ResponseEntity.created(location).build();  
}
```


> [!warning] 주의 사항

