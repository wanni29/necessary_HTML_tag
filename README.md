# form 태그 개념

## form 태그란? HTML문서에서 사용자로부터 정보를 입력받을 수 있는 요소를 생성하는 역할
- 주로 텍스트 입력, 체크박스 선택, 라디오 버튼 등 상호작용을 가능하게 해줍니다
- Spring boot 안에서는 회원가입, 로그인, 검색, 정보 제출 등과 같은 기능을 구현
```html
<form action="URL" method="HTTP_METHOD" enctype="application/x-www-form-urlencoded">
```
```text
        action : 폼 데이터를 서버로 제출할 때 데이터를 보낼 URL 지정
        이 URL은 웹서버측의 스크립트 또는 프로그램을 가리키는데, URL로 전송되어 서버에서 처리 됨


        mehtod 폼 데이터를 서버로 전송하는 방식을 지정, 대표적으로 2가지 방식이 있다.
        GET : 폼 데이터를 URL에 포함하여 전송, 간단한 데이터 또는 주로 검색에 이용
        읽어오는 요청은 GET!
        POST : 폼 데이터를 HTTP요청의 본문에 담아서 전송, 보안이 필요한 데이터 전송이나 대용량 데이터 전송에 이용
        정보를 보내는 요청은 POST!

        form 태그 안에는 다양한 입력 요소들이 들어갈수 있다. 가장 흔히 사용되는것들을 예로 보자
        <input> : 텍스트 입력, 체크박스, 라디오 버튼, 숨겨진(hidden) 입력등을 생성할 수 있음 
        <textarea> : 여러줄의 텍스트를 입력 받을 수 있는 입력 요소를 생성
        <select> : 드롭 다운 목록읓ㄹ 생성하고 그안에 <option 태그를 사용하여 선택항목 생성>
        <button> : 버튼 생성
        <label> : 다른 입력 요소와 연결하여 라벨을 지정

        enctype는 HTML 폼(form) 태그에서 사용되는 속성 중 하나 
        폼 데이터가 서버로 전송될 때 데이터를 인코딩하는 방식을 지정하는 역할
        method 속성이 "POST"인 경우에는 데이터가 HTTP 요청의 본문에 담겨 전송되므로, 데이터의 인코딩 방식을 명시
        name=value 형태로 인코딩되고, 필드 간에는 & 기호로 구분

```

# 코드활용
```HTML
   <!-- text: 일반적인 텍스트 입력받을수 있음-->
    <div>
        <label for="username">Username:</label>
        <input type="text" id="username" name="username" required>
    </div>

    <!-- password : 비밀번호를 입력받을수 있음, 가려짐-->
    <div>
        <label for="password">Password:</label>
        <input type="password" id="password" name="password" required>
    </div>

    <!-- number : 숫자를 입력받을수 있음, 단 숫자만 가능-->
    <div>
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" min="18" max="100" required>
    </div>

    <!-- tel :  전화 번호 입력받을수 있음-->
    <div>
        <label for="phone">Phone:</label>
        <input type="tel" id="phone" name="phone" required>
    </div>

    <!-- url : 웹주소 입력 받을수 있음-->
    <div>
        <label for="website">Website:</label>
        <input type="url" id="website" name="website" required>
    </div>

    <!-- checkbox : 하나 이상의 선택사항을 체크할수있음-->
    <div>
        <label for="option1">Option 1:</label>
        <input type="checkbox" id="option1" name="option1" value="1">
        <label for="option2">Option 2:</label>
        <input type="checkbox" id="option2" name="option2" value="2">
    </div>

    <!-- radio : 라디오 버튼-->
    <div>
        <label for="gender-male">Male:</label>
        <input type="radio" id="gender-male" name="gender" value="male" required>
        <label for="gender-female">Female:</label>
        <input type="radio" id="gender-female" name="gender" value="female" required>
    </div>


    <!-- file : 파일 선택할수있는 업로드 필드-->
    <div>
        <label for="file">Select a file:</label>
        <input type="file" id="file" name="file" accept=".jpg, .png, .pdf" required>
    </div>

    <!-- submit : 폼을 제출하는 버튼, 폼의 내용을 서버로 전송-->
    <div>
        <input type="submit" value="Submit">
    </div>

    <!-- reset : 폼의 내용을  초기화 하는 버튼, 입력된 내용을 초기화 시킴-->
    <div>
        <input type="reset" value="Reset">
    </div>

    <!-- button : 클릭이벤트를 처리하기 위한 버튼-->
    <div>
        <button type="button" onclick="alert('Button Clicked!')">Click Me</button>
    </div>

    <!-- date : 날짜를 선택할수있는 입력 필드-->
    <div>
        <label for="birthdate">Birthdate:</label>
        <input type="date" id="birthdate" name="birthdate" required>
    </div>

    <!-- time : 시간을 선택할수있는 입력 필드-->
    <div>
        <label for="meeting-time">Meeting Time:</label>
        <input type="time" id="meeting-time" name="meeting-time" required>
    </div>
    
    <!-- color :  색상을 선택할수있는 입력 필드-->
    <div>
        <label for="fav-color">Favorite Color:</label>
        <input type="color" id="fav-color" name="fav-color" value="#ff0000">
    </div>
    
    <!-- range : 숫자 범위를 선택할수있는 슬라이더 형태의 입력 필드-->
    <div>
        <label for="volume">Volume:</label>
        <input type="range" id="volume" name="volume" min="0" max="100" step="1">
    </div>
    
    <!-- hidden : 사용자에게 보이지 않고, 서버로 데이터를 전송할 목적으로 사용되는 숨겨진 필드-->
    <div>
        <input type="hidden" name="session-id" value="ABC123XYZ">
    </div>
```
    