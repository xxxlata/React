# 순수 html파일에 리액트 적용하기

react script소스를 인클루드시키면 html에서 react 라이브러리 이용이 가능해진다.
필요한 react 소스(변동이 있을 수 있으니 구글 서칭으로 직접찾아서 넣는것이 좋다.)
1. react.development.js
2.react-dom.development.js 


필요한 것은 root의 참조이다. (어떠한 결과를 출력해줄수있는 root엘리먼트)
모든 react 컴포넌트를 출력시켜주는 역할이기 때문이다.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello React 1</title>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
</head>
<body>
// react는 컴포넌트 출력을 위해 root엘리먼트를 반드시 참조해줘야한다.
   <div id="root"></div> 
   <script type="text/javascript">
       ReactDOM.render(React.createElement("h1",null,"안녕") ,document.getElementById("root"));
   </script>
</body>
</html>
```

# createElement를 이용하여 스타일 속성을 부여해보자.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello React 2</title>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
</head>
<body>
   <div id="root"></div> 
   <script type="text/javascript">
        ReactDOM.render(
            React.createElement("h1",{"style": {"color": "blue"}},"안녕") ,
            document.getElementById("root")
        );
   </script>
</body>
</html>
```
# element를 더 만들어보자.


```
<body>
   <div id="root"></div> 
   <script type="text/javascript">
        ReactDOM.render(
            React.createElement(
                "div",{"style": {"border":"1px solid red"}},
                React.createElement("h1",{"style": {"color": "blue"}},"안녕"),
                React.createElement("h1",{"style": {"color": "red"}},"안녕"),
                React.createElement("h1",{"style": {"color": "green"}},"안녕"),
            ),
            document.getElementById("root")
        );
   </script>
</body>
</html>
```
