# HTML(Hyper Text Markuo Language)

웹페이지를 만들기 위한 언어로 웹브라우저 위에서 동작하는 언어다

HT-Hyper Text,문서와 문서가 링크로 연결되어 있다

M-Markup태그로 이루어져 있따

L-Language



### 1) HTML 태그의 형식

``` 
<태그명 속성명1="속성값1" 속성명2="속성값2"> 정보</태그명>
```



### 2)HTML 문서의 구조

```
<head>태그는 문서를 설명하는 태그. 제목이나 키워드 같은 정보 담는다
<body> 문서의 내용이 위치
```



### 3) HTML 태그

사진을 참고하시길

***



# CSS(Casticated Style Sheet)

HTML이 정보를 표현한다면 CSS는 HTML을 시각적으로 꾸며주는 역할을 한다.

HTML5에서는 HTML는 정보와 구조화, CSS 는 styling의 정의

```
<p style="background-color: red">안녕</p>
```



### 1) HTML에서 CSS 사용하기

**a. inline 방식**

비추

**b. style tag방식**

* 의미와 디자인의 분리라는 css 취지에 맞다.

<u>**c. 외부 파일 방식**</u>

* css를 별도릐 파일로 분리해서 링크하는 방식

* 유지보수가 편하다



### 2)CSS의 형식

```
선택하는 대상 + {꾸며주는 법;}
p {front-size :15px;}
```

**a.선택자**

* 요소 선택자(type)

  태그의 이름을 사용함

* 클래스 선택자(class)

  여러개 클래스를 표시할 수 있다(공백 사용해서)

  . 을 사용함

* 아이디 선택자(id)

  전체 문서에서 하나의 태그를 식별하기 위해 사용됨

  #을 사용함



**b.여러가지 CSS 속성**

...



***

## 사용해볼 프로그램



`HTML + CSS`

python 기반의 웹 프레임워크인 **Falsk**

* Flask -> Micro Webframe Work

* 확장성을 넓혀놔서 초보자도 쉽게 만들 수 있다.

  

`서버` : (요청과 응답) 요청을 받고 응답을 해주는 곳



### Rendering Template

HTML을 보여줌



### JINJA2

템플릿 엔진



### PINGPONG

request - 값이 있으면 하나씩 받아옴

requests(어제 했던) - 직접 요청해서 받아옴



* 통신하는 방법

  * GET : 서버에 정보를 조회할 때.

    주소에 요청하는 정보가 같이 넘어간다.

    특징 : 동일한 요청을 보내도 항상 동일한 값이 나온다. ex) 펭수 쳤는데 칠때마다 다른 사진 나오지 않는다.

  * POST : 서버에 리소스를 생성/수정할 때

    주소창에 노출되지 않음, 패킷을 전송할 때 패킷에 정보가 전달되어 넘어감(사용자가 겉으로는 확인 불가,구글에 F12눌러서 뜯어서 코드보지 않는 이상 못봄)

***

***

## Review

* html & CSS

* Css & Flask ->웹서버 만듬, Flask 공식 document quickstart부분에서 사용법 알아봄

* route =>decorator

* import datetime-오늘날짜 가져오기 등등-> D-day page만듬

* return에 html tag같이 보내기, '''사용 여러줄 보내기 실습

* variable routing 동적 라우팅. 변수하나를 동적으로 정해서 사용->Variable Rules 

  ```
  @app.route('/user/<int:id>')
  ```

* debug mode on 시키는 방법

* render_template이용 html로 화면 보여주기

  ```
   return render_template('pong.html', peng =value)
  ```

  

* render_template 안에 특정 값 넘겨주기

  ```
  name = request.args.get('me') 
  ```

* <u>pingpong 주고 받기!!!!!!!!!!!!!!!!</u>
* 신이 나를 만들 때 bongbong 만들어봄