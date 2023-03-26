

<정적컨텐츠>
웹브라우저에서 내장 서버에 전송.
스프링으로 넘김
스프링에선 먼저 컨트롤러쪽에 물어봄(hello-static이 있나?) = 컨트롤러가 우선순위를 가짐
없으면 => 내부의 hello-static찾아서 반환. 

=>요약: 별다른 변형 없이 그대로 반환. 


<MVC> 
마찬가지로 웹브라우저에서 내장 서버에 전송. + 스프링으로 넘김
컨트롤러에 전에 사용했기 때문에 맵핑이 되어있음. -> 호출해줌
이걸 다시 스프링(viewResolver)으로 넘겨줌. 
넘겨받은애랑 같은 것을 찾음.
Thymeleaf 템플릿 엔진에 넘김.  
Thymeleaf 엔진이 랜더링 후 변환하여 웹브라우저에 전송.(정적일때는 변환하지 않음.)

=>요약: 템플릿엔진을 모델로 컨트롤러 방식으로 쪼갬. viewResolver에서 랜더링이 된 것으로 반환함. 


<ResponseBody를 사용한 API방식>
=> HTTP의 BODY에 문자 내용 직접 반환 == 객체 -> 객체를 문자로 바꿔서 반환해야 함. 
그러면 viewResolver대신 HttpMessageConverter가 동작

=>요약: 객체를 반환. Json으로 바꿔서 반환하는것. 랜더링이나 변환 없이 값만 넣어서 바로 반환.

<RESTFful>
- REST라는 아키텍셔를 구현하는 웹서비스를 나타내기 위해 사용되는 용어(ex. REST API 제공 웹서비스)
-목적: 이해와 사용이 쉬운 API 만들기
- REST = representational satate transfer