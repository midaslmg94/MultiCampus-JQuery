# MultiCampus-JQuery
- 서버에 캐시를 남기지 않으려면 `npx http-server -c-1` 명령어를 치면 된다.



#### JQuery 선택자

- 태그 선택자
  - $("태그명").css : 태그에 대한 css 속성 설정 --> 화면 제어 
  - $("태그명").text : 태그에 대한 값 설정 --> 값 제어
  - $("태그명").html :  --> 값 제어
  - $("태그명").attr : 태그에 대한 값 설정
  - $("태그명").val : 태그에 대한 값 가져오기
  - $("태그명").each(function(index, item))  

- 자식 선택자
  - $("parent>child")
  - $("parent child")
- 후손 선택자
  - 
- 속성 선택자
  - E[A=V] 속성값이 같은 문서 객체 선택       
  - E[A!=V] 속성값이 다른 문서 객체 선택        
  - E[A~=V] 속성값에 단어가 포함된 객체를 선택          
  - E[A^=V] 속성값이 글자로 시작하는 객체를 선택        
  - E[A$=V] 속성값이 글자로 끝나는 객체를 선택        E[A*=V] 속성값에 글자를 포함한 객체를 선택
- 아이디 선택자 
  - $(#id명)

- 클래스 선택자
  - $(.class명)





------

#### JQuery 필터





------

#### JQuery 이벤트

- .click : 

  - 콜백 함수

    ```javascript
    .click(function({	
    }))
    ```

  - 



------

#### Ajax

- .ajax 메소드를 이용하여 문서내에 있는 script 데이터를 서버와 통신
- 데이터의 형태는 JSON을 사용



------

#### JQuery UI plug-in

- toast.js
- 