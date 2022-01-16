# 설치과정

### create-react-app 을 이용하여 react 환경구축하기

1. visualstudio(개발도구) 와 visualstudio code(개발도구)를 최신버전으로 다운받는다.<br>
2. react환경 구축의 필수요인인 node 와 npm도 최신버전으로 다운받아준다.<br>
3. npm(Node Packaged Manager)은 node설치시 함께 설치된다.<br>
4. (npx)<br>
npx 는 npm의 5.2.0 버젼부터 새로 추가된 도구이다.<br>
npm을 통해 react app 을 생성하는 것이 가능하나, -g 를 통해 전역적으로 create-react-app 이 설치됨으로서 여러 문제점을 야기한다.
```
//npm을 이용한 create-react-app 설치
npm install -g create-react-app
```
(문제1. CRA의 무거운 의존성 라이브러리들이 컴퓨터에 남는다.)<br>
(문제2. CRA 버전 업데이트 시, 전역적으로 설치된 CRA를 재설치 해야 한다.)<br>

npx를 설치하기 위해서는 npm 을 통해서 설치 가능하다.
```
npm install npx -g
``` 
npx 를 설치했다면 npx 를 통해 react app 을 생성할 수 있다.<br>

최신 CPA 패키지가 다운로드가 되고 설정들을 세팅한 후에 CRA 패키지는 제거된다.
그렇기 때문에 무거운 의존성 라이브러리들도 남지 않고 함께 제거되는 이점이 있다.
```
//앱 생성 및 작동
npx create-react-app my-app
cd my-app
npm start
```
