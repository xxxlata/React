# jsx

자바스크립트를 이용하여 html요소를 만들어내는 jsx
babel 라이브러리를 이용하여 createElement 함수를 사용하지않고도 요소만들기가 가능하다. html태그만 사용하여 요소만들기가 가능하다는 뜻 


주의할 점은 jsx는 무조건 최상위 엘리먼트가 하나여야한다. 형제엘리먼트가 존재하면 안됨. 
div태그를 최상위 엘리먼트로 설정해놓고 그 안에 어떤 엘리먼트를 얼마나 넣던 상관없다.

```
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello React 4</title>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script crossorigin src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
</head>
<body>
   <div id="root"></div> 
   <script type="text/babel">
        //babel upk 소스를 추가해주고 script 타입을 text/babel로 바꿔준다.
        //JSX를 사용하여 HTML을 JavaScript 변환
        ReactDOM.render(
            <div><h1>babel을 이용하여 간편하게 만들어 보았습니다.</h1></div>,
            document.getElementById("root")    
        );
   </script>
</body>
</html>
```
--------------------------------------------------------
bootstrap을 이용하여 css를 꾸며보자
bootstrap cdn을 구글에 친 다음 css 링크를 따온다.


Jsx에서는 요소에 id를 주는 것은 상관없지만 class를 사용하는 것은 안된다. js 문법의 class로 인식하기 때문이다. class를 사용하고싶다면 아트리부트로 사용해야한다. 
className="container mb-2" 부트스트랩 css기본 기능을 구현한다.
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello React 5</title>
    <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script crossorigin src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
</head>
<body>
   <div id="root"></div> 
   <script type="text/babel">
        ReactDOM.render(
            (    
                <div className= "container mb-2">
                    <div className="row">
                        <div className="col-2">
                            c#
                        </div>
                        <div className="col-10">
                            내용    
                        </div>
                    </div>
                </div>
            ),
            document.getElementById("root")    
        );
   </script>
</body>
</html>
```
------------------------------------------
jsx expression( jsx 표현식)


변수에 값을 넣고 표현식을 삽입하여 사용한다. 
```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "JSX 표현식(Expression)";

        let seeSharp = {
            title: "c#",
            description: "내용들어오는 곳..."
        };

        ReactDOM.render(
            (    
                <div className= "container mb-2">
                    <div className="row">
                        <div className="col-12">
                            {title}
                        </div>
                    </div>
                    <div className="row">
                        <div className="col-2">
                            {seeSharp.title}
                        </div>
                        <div className="col-10">
                            {seeSharp.description}    
                        </div>
                    </div>
                </div>
            ),
            document.getElementById("root")    
        );
   </script>
</body>
</html>
```


