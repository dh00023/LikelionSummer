### 170725 Javascript ch6
---
#### 06-1 이벤트
---
##### 이벤트란?
브라우저에서 방문객이 취하는 모든 동작
##### 이벤트 핸들러?
이벤트가 발생했을 때 자바스크립트 실행문을 실행하는 것
- 이벤트의 종류
![KakaoTalk_20170725_093727230.jpg](.\KakaoTalk_20170725_093727230.jpg)




###### 직접 요소 이벤트
```<button id="btn" onclik="alert('Event')"버튼"</button>```
###### Dom을 이용한 이벤트 등록 방식
```<button id="btn">버튼</button>```
```erb
document.getElementByld("btn").onclick=function(){
alert('Event');
}
```
##### 키보드 접근성
마우스가 없어도 이벤트를 사용할 수 있어야 한다.

| 마우스 이벤트 | 키보드 대응 이벤트 |
|:-------------:|:-----------------:|
|onmouseover|onfocus|
|onmouseout|onblur|

##### 이벤트 중복 등록 해결법
###### 한 요소에 같은 이벤트를 중복으로 등록하는 방법

|브라우저 구분 | 브라우저 구분|
|---------|----------------|
|IE8이하 외의 브라우저| 요소선택.addEventListener("이벤트 종류", 함수명 또는 익명 함수, false(표준 캡처 방식));|
|IE8이하|요소선택.attachEvent("on이벤트 종류",함수명 또는 익명 함수);|

##### this 키워드
방문자가 이벤트를 발생한 요소를 가리킨다.

#### 06-2 이벤트객체
사이트에 방문자가 지정한 요소에서 이벤트가 발생한 경우, 이벤트 핸들러(익명 함수)에 이벤트 객체를 생성하여 실행문으로 사용할 수 있다. 이 이벤트 객체에 속성을 이용하면 해당 이벤트에 다양한 정보를 얻어 올 수 있다. 
##### 이벤트 객체 생성하기
```erb
//파이어폭스, 크롬, 사파리, 오페라, IE9 이상에서 이벤트 객체 생성하기
document.onkeydown=function(e){
	alert(e);
}
//그 외
document.onkeydown=function(e){
alert(window.event);
}
//모든 브라우저에서 이벤트 객체 생성하기
document.onkeydown=function(e){
var eventObj=e?e:window.event;
alert(eventObj);
}
```

##### 이벤트 객체의 속성 종류


![ww.jpg](.\ww.jpg)






