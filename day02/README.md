# JQuery



##### 200130 목요일

- jquery 실행

  ```powershell
  PS C:\Users\HPE\Work\MultiCampus-JQuery\day02> npm init -y
  .
  .
  .
  PS C:\Users\HPE\Work\MultiCampus-JQuery\day02> npm install jquery
  npm notice created a lockfile as package-lock.json. You should commit this file.
  npm WARN day02@1.0.0 No description
  npm WARN day02@1.0.0 No repository field.
  
  + jquery@3.4.1
  added 1 package from 1 contributor and audited 1 package in 0.589s
  found 0 vulnerabilities
  
  PS C:\Users\HPE\Work\MultiCampus-JQuery\day02> npx http-server
  Starting up http-server, serving ./
  Available on:
    http://10.0.75.1:8080
    http://59.29.224.24:8080
    http://192.168.56.1:8080
    http://192.168.44.1:8080
    http://10.0.0.1:8080
    http://127.0.0.1:8080
    http://172.17.100.145:8080
  Hit CTRL-C to stop the server
  [2020-01-30T00:21:48.468Z]  "GET /" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.130 Safari/537.36"
  ```

- jquery template

  ```javascript
  <script src="/node_modules/jquery/dist/jquery.js"></script>
      <script>
          $(function () {
  
          });
      </script>
  ```

- Selector

  - input type = "radio button" : 여러개의 라디오 버튼 중 1개만 선택해야 할 때 사용한다

    - name이 같은것으로 묶임

      ```javascript
      결혼여부:<input type="radio" name="is_married" value="Y">네
          <input type="radio" name="is_married" value="N">아니오<br>
      ```

    - 

  - input type = "check box" : 여러개를 선택할 때 

- URL 

  - GET Method : 요청 파라미터를 주소 맨 뒤(&연산자 뒤)에 포함시켜 전달하는 방법 

    ```txt 
    http://naver.com/abc/xyz/do.jsp?lastName=lee & firstName=minki
     스킴    호스트       경로          요청 파라미터     요청 파라미터
    ```

  - POST Method : 주소창에 요청 파라미터가 보이지 않음.

- 속성 선택자 

  - E[A!="V"] : 속성값이 다른 문자 선택

  - E[A~="V"] : A 속성에 "V"가 **포함**된 것을 검색 : 띄어쓰기는 구분 못함. 

  - E[A^="V"] : A 속성이 "V"로 **시작**하는 것을 검색

  - E[A$="V"] : A 속성이 "V"로 **끝나**는 것을 검색

  - E[A*="V"] : A 속성에 "V"가 들어가 있는 것을 삭제

    ```javascript
    <script>
            $(function () {
                // 성, 이름 입력창에 000을 입력하세요. 문장 추가
                // 성, 이름의 type이 text이므로 동일함 
                $('input[name="lastName"]').val("성을"); // .val에 들어가는게 밑에 있는 value임
                $('input[type="text"]').val("입력하세요");
    
                // 파일 선택창을 제외하고 나머지 입력창에 대해서(필수입력)을 표시
                // .prev()는 input 앞 부분을 의미
                $('input[type!="file"]').prev().append("(필수입력)").css('color', 'red');
    
                // name 속성에 pw가 포함된 것을 검색
                $('input[name~="pw"]').css('background','blue');
                
                // name 속성이 pw로 시작하는 것을 검색
                $('input[name^="pw"]').css('border','3px dotted red');
    
                // name 속성이 Name으로 끝나는 것을 검색
                $('input[name$="Name"]').css('border', '3px solid');
    
                // type 속성에 "o"라는 단어가 들어간 입력창을 삭제
                $('input[type*="o"]').hide();
            });
        </script>
    
    <body>
        <form action="#" method="get">
        <label>성</label>
        <input type="text" name="last Name" value=""> <br>
    
        <label>이름</label>
        <input type="text" name="first Name" value=""> <br>
    
        <label>패스워드</label>:<input type="password" name="pw"> <br>
        <label>패스워드(확인)</label>:<input type="password" name="pw2"> <br>
        결혼여부:<input type="radio" name="is_married" value="Y">네
        <input type="radio" name="is_married" value="N">아니오<br>
        좋아하는 색깔: <input type="checkbox" name="color" value="red">빨강<br>
        좋아하는 색깔: <input type="checkbox" name="color" value="blue"">파랑<br>
        좋아하는 색깔: <input type="checkbox" name="color" value="yellow">노랑<br>
        사진 : <input type="file" name="photo">
    </form>
    </body>
    
    </html>
    ```



- style 태그를 사용

  ```javascript
  <head>
      <script src="node_modules/jquery/dist/jquery.js"></script>
      <script>
          $(function () {
              //$("div").css('background','lightyellow');
          });
      </script>
      <style> /*css 스타일*/
          div {
              border: 1px solid black;
              padding: 50px;
              margin: 10px 20px 30px 40px;
              width: 10px;
              height: auto;
              font-size: 30px;
              float: left;
          }
  
          div.num {
              background: coral;
          }
  
          div.red {
              color: red;
          }
  
          div.char {
              color: greenyellow;
          }
  
          div.red {
              color: red;
          }
  
          div.blue {
              color: blue
          }
          div[class="char yellow"] {
              background: indigo;
          }
  
      </style>
  </head>
  <body>
      <div class="num red">1</div>
      <div class="num blue">2</div>
      <div class="num yellow">3</div>
      <div class="num green">4</div>
  
      <div class="char red">하나</div>
      <div class="char blue">둘</div>
      <div class="char yellow">셋</div>
      <div class="char green">넷</div>
  </body>
  
  ```

- 







- 이벤트 핸들링

- ```javascript
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
      <script src="node_modules/jquery/dist/jquery.js"></script>
      <script>
          $(function () {
              /*  jQuery로 짜보자
                  num:배경색을 회색
                  char:배경색을 노란색
                  red, yellow, green, blue -> 글자색
              */
              // 아래와 같이 하면 불편하다. 
              /*
              $('div.num').css('background', 'gray');
              $('div.char').css('background', 'coral');
              $('div.red').css('color', 'red');
              $('div.blue').css('color', 'blue');
              $('div.yellow').css('color', 'yellow');
              $('div.green').css('color', 'green');
              */
              // 태그를 가져와서 배열로 짜보자 
              $('div.num').each(function (index, item) {
                  // 전체 문자열에서 일부 문자만 뽑아오는 함수 : substring()
                  let color = $(item).attr('class').substring(4);
                  $(item).css('color', color);
  
              });
              $('div.char').each(function (index, item) {
                  let background = $(item).attr('class').substring(5);
                  $(item).css('background', background);
              });
              // 이벤트 핸들링
              $('div#input div').click(function () {
                  let value = $(this).text(); // div가 가지고 있는 값을 value에 저장
                  console.log(value);
                  let attr = $(this).attr('class');
                  console.log(value, attr);
                  // 클릭한 것을 화면에 출력
                  $('#disp').append(value, attr);
              });
          });
      </script>
  </head>
  
  <body>
      <div id="disp">
      </div>
      <div id="input">
          <div class="num red">1</div>
          <div class="num blue">2</div>
          <div class="num coral">3</div>
          <div class="num green">4</div>
  
          <div class="char red">하나</div>
          <div class="char blue">둘</div>
          <div class="char yellow">셋</div>
          <div class="char green">넷</div>
      </div>
  </body>
  
  </html>
  ```

  

  - 클릭 이벤트

  - ```javascript
    <!DOCTYPE html>
    <html>
    
    <head>
        <script src="/node_modules/jquery/dist/jquery.js"></script>
        <script>
            /* 
                div 박스를 클릭하면 동일한 data가 있으면, 
                다른 클래스의 data의 박스를 숨김(hide()), 없으면 다른 클래스의 박스를 보이게(show())
                (단, 추가시 num과 char 클래스는 다르게 설정)
                -- hide(), show()
                
            */
            $(function () {
                $('div').click(function(){
                    let cls = $(this).attr('class');
                    let val = $(this).attr('data');
                    // 현재 클릭된 div와 value가 같고 class가 다른 div를 선택 
                    // 속성을 제어해야 하므로 []를 열어줌
                    let el = $('div[data="'+val+'"][class!="'+cls+'"]');
                    /* 아래는 el.toggle(); 와 같은 기능
                    if(el.is(':visible')){
                        el.hide();
                    }else{
                        el.show();
                    }*/
    
                    el.toggle();
    
                })
            });
        </script>
        <style>
            div {
                border: 1px solid black;
                padding: 10px;
                margin: 10px 20px;
                width: auto;
                height: auto;
                font-size: 30px;
                float: left;
            }
        </style>
    </head>
    
    <body>
        <div class="no" data="1">1</div>
        <div class="no" data="2">2</div>
        <div class="no" data="3">3</div>
        <div class="no" data="4">4</div>
    
        <div class="ch" data="1">one</div>
        <div class="ch" data="2">two</div>
        <div class="ch" data="3">three</div>
        <div class="ch" data="4">four</div>
    
    </body>
    
    </html>
    ```

    

  - 마우스 오버 이벤트

    ```javascript
    <!DOCTYPE html>
    <html>
    
    <head>
        <script src="/node_modules/jquery/dist/jquery.js"></script>
        <script>
            $(function () {
                /*
                    홀수번째 : red
                    짝수번쨰 : blue
                    첫번째 : yellow
                    마지막 : green
                */
                $('div:odd').css('background','red');
                $('div:even').css('background','blue');
                $('div:first').css('background','yellow');
                $('div:last').css('background','green');
                let orgColor;
                $('div').mouseover(function(){
                    orgColor=$(this).css('background');
                    console.log($(this).text());
                    $(this).text('abcd'); 
    
                    $(this).attr('test', 'testvalue'); // 값을 설정하는 것, setter
                    console.log($(this).attr('test'));
    
                    $(this).css('background', 'black');
    
                }).mouseleave(function(){
                    $(this).css('background', orgColor);
                })
            });
        </script>
        <style>
            div {
                width: 100px;
                height: 100px;
                border: 1px solid blue;
                float: left;
                margin: 20px;
            }
        </style>
    </head>
    
    <body>
        <div>1</div>
        <div>2</div>
        <div>3</div>
        <div>4</div>
    
    </body>
    
    </html>
    ```

  

  

#### JQuery UI
 - 웹 사이트를 만들 때 UI를 쉽고 이쁘게 만들 수 있게 해줌

 - `npm i jquery-ui` 로 설치하자. 이때 `node_modules` 폴더가 하위 폴더에 있어야 한다

 - 위와 달리 css 관련 내용을 style에 묶어두었기 때문에 재사용 측면에서 좋다

   ```javascript
   <!DOCTYPE html>
   <html>
   
   <head>
       <script src="/node_modules/jquery/dist/jquery.js"></script>
       <script src="/node_modules/jquery-ui-css/jquery-ui.js"></script>
       <link rel="stylesheet" href="/node_modules/jquery-ui-css/jquery-ui.css">
       <script> // jQuery UI를 사용하여 이쁘게 만들자
           $(function() {
               $("button, a").button();
               $('div').mouseover(function(){
                   $(this).attr('class', 'mycolor1');
               }).mouseleave(function(){
                   $(this).attr('class', 'mycolor2');
               });
           });
       </script>
       <style>
           div{width: 100px; height: 100px; float: left; border: 1px solid red;}
           .mycolor1{background-color: greenyellow;}
           .mycolor2{background-color: blueviolet;}
       </style>
   </head>
   
   <body>
       <button>클릭하세요</button>
       <a href="#">클릭하세요</a>
       <div>1111</div>
       <div>2222</div>
   
   </body>
   
   </html>
   ```

    - jQuery UI Theme 적용
    - focus는 반드시 한군데만 입력받을 수 있다

- Toast.JS 적용

  - ```javascript
    <!DOCTYPE html>
    <html>
    <head>
        <link rel="stylesheet" href="/jquery-ui-1.12.1/jquery-ui.css">
        <link rel="stylesheet" href="/jquery-ui-1.12.1/jquery-ui.theme.css">
        <script src="/jquery-ui-1.12.1/external/jquery/jquery.js"></script>
        <script src="/jquery-ui-1.12.1/jquery-ui.js"></script> 
        <!--toast.js 사용-->
        <script src="node_modules/jquery-toast-plugin/dist/jquery.toast.min.js"></script>
        <link rel="stylesheet" href="node_modules/jquery-toast-plugin/dist/jquery.toast.min.css">
        <script>
            $(function () {
                $("#tabs").tabs();
                $('input[name="userid"]').focusout(function(){
                    if($(this).val()==""){
                        // alert("아이디를 입력하세요"); // 없어보임                   
                        //$("#dialog").dialog(); // jQuery UI 사용
                        $.toast({
                            text: "아이디를 입력하세요.",
                            showHideTransition: 'fade'
                        });
                    }
                });
            });
        </script>
        <style>
        </style>
    </head>
    
    <body>
        <div id="tabs">
            <ul>
                <li><a href="#matzip">맛집예약</a></li>
                <li><a href="#hospital">병원예약</a></li>
                <li><a href="#car">공유자동차예약</a></li>
            </ul>
            <div id="matzip">
                <p>맛집 예약과 관련한 컨텐츠</p>
            </div>
            <div id="hospital">
                <p>병원 예약과 관련한 컨텐츠</p>
            </div>
        </div>
        <input type="text" name="userid">
        </div>
    </body>
    </html>
    ```

  - color box : 

    - 설치 : `npm install jquery-colorbox`

    ```javascript
    
    ```





------

#### Ajax 통신 

- 자바스크립트를 이용한 비동기 통신방식

- JSON 형태의 데이터가 서버로부터 온다. 이 데이터를 DOM Script 방식으로 웹페이지에 넣어준다. -> Web 2.0

- 데이터 전송형식 

  - CSV(comma-separated values) : 콤마로 구분해서 데이터를 전송. 대용량 데이터를 전송할 때 활용하면 좋지만, 가독성이 좋지않고, 문자 중간에 콤마가 있으면 제대로 전송이 안된다.

  - XML(Extensible Markup Language) : 해당하는 데이터의 의미를 보다 보기쉬움

    ```xml
    <menu id="file" value="File">
      <popup>
        <menuitem value="New" onclick="CreateNewDoc()" />
        <menuitem value="Open" onclick="OpenDoc()" />
        <menuitem value="Close" onclick="CloseDoc()" />
      </popup>
    </menu>
    ```

    - 장점 : 순서와 무관하게 데이터의 처리가 가능하다.
    - 단점 : 복잡함. 태그간의 포함관계, 열고닫음 등등 

  - JSON(JavaScript Object Notation) : Key와 Value의 관계로 데이터를 작성

    ```json
    {"menu": {
      "id": "file",
      "value": "File",
      "popup": {
        "menuitem": [
          {"value": "New", "onclick": "CreateNewDoc()"},
          {"value": "Open", "onclick": "OpenDoc()"},
          {"value": "Close", "onclick": "CloseDoc()"}
        ]
      }
    }}
    ```

    - 현재는 이기종간의 데이터 교환을 할 때 대부분 JSON으로 쓴다. 

  

  

  