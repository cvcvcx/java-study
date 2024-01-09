---
일자: 📆 2024-01-04
스프링부트버전: 3.2.1
운영체제: mac Sonoma 14.2.1(23C71)
상황: "@PathVariable 적용중 오류 발생"
에러 로그: Name for argument of type [java.lang.Integer] not specified, and parameter name information not available via reflection. Ensure that the compiler uses the '-parameters' flag
에러로그 한글번역: "\"유형이 [java.lang.Integer]인 인수에 대한 이름이 지정되지 않았으며, >   리플렉션을 통한 매개변수 이름 정보를 사용할 수 없습니다. >   컴파일러가 '`-parameters' `플래그를 사용하는지 확인하십시오.\""
---
> [!warning] 문제상황 
> - `@PathVariable`을 사용하려던 중, 에러가 발생했다. 번역은 다음와 같다
> - 분명 생략 가능하게끔 코드를 짜 놓았는데 에러가 발생해서, 문제를 해결하기 위해 검색을 시도했다.

> [!info] 해결과정
> - 단순하게 일단 ChatGPT를 사용하여 해결하려고 시도했다.
> - 그러나, 해결에 실패하고, 구글링을 통해 해결방법을 찾았다

> [!important] 발생 원인
> - `Spring boot 3.2`버전으로 업데이트되면서, `@PathVariable`을 사용할 때, 
>   컴파일시 -parameters플래그를 추가하지 않으면, 이름을 생략할 수 없게 바뀌었다.

> [!success] 해결 방법
>  1. 가장 추천하는 방법은 항상 명시적으로 name을 @PathVariable에 적어주는 것이다.
>  2. name을 이전처럼 생략하고 싶으면, IntelliJ의 Build메뉴에 Compiler 안에 있는 Additional command line parameters라는 항목에 -parameters를 추가해야 한다.

