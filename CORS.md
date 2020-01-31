- #### [HTTP 접근제어 CORS](https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS)

  - SOP(Same Origin Policy) : 동일기원정책
    - 자바스크립트에서 다른 사이트에서 무엇인가를 가져와서 쓰는 것을 막는 정책 --> 보안 이슈.
    - Origin = 스킴+호스트+포트 
      - 스킴, 호스트, 포트가 모두 같으면 동일 출처(동일 Origin)
      - Origin(출처)이 다르면 막는다 --> SOP
    - XML HTTP Request : XHR 
    - open API가 많아지면서 클라이언트 쪽에서 리소스를 요청하는 경우가 많아지고 있다. 이때 SOP정책 때문에 리소스를 가져오지 못하는 경우가 많기 때문에 SOP를 완화 시키게 되었다. 
    - 이를 CORS(Cross Origin Resource Sharing)라고 한다. -- html5에서 풀어주었음. 브라우저에 적용되어있는 보안기술
    - 응답헤더에 Access Control Allow Origin : (*)
    - 문서를 보내주는 쪽(응답)에서  Access Control Allow Origin를 허용해주면 문서를 받는쪽(요청)에서 사용할 수 있다.
  - CORS는 SOP 정책을 완화시켜준다

