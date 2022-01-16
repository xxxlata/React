# Create-react-app 으로 만든 리액트 프로젝트의 구조 살펴보기

신경써야하는 폴더는 public 그리고 src 폴더가 있다.


react는 싱글페이지 어플리케이션이기 때문에 하나의 단일페이지로부터 실행이 된다.<br>
public폴더 안에 들어있는 index.html파일에서 가장 중요한 정보는 root라는 id값을 가지고있는 div 이다.<br>
모든 리액트 컴포넌트들, ui 구성요소들을 실행되게하는 것이 바로 ```<div id= "root"></div>```(루트엘리먼트)에 의해서 실행시키기 때문이다.



src폴더는 소스를 만들어 public파일로 올라가는 폴더이다. 
App.js 에서 작성한 것은 index.html 의 ```<div id="root"></div>```로 들어가게 된다.
이 역할을 해주는 것이 index.js 이다.
<App /> 에 있는 것을 document.getElementById('root') 으로 넣어주게 된다.

