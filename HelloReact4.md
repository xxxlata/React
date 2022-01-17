# 함수형 컴포넌트 만들고 jsx표현식에 적용하기 

react는 함수를 하나의 완성된 컴포넌트로 인식한다. (하나의 구성요소)
어떠한 타입의 컴포넌트이건 이름의 첫 글자는 대문자로 시작되어야한다.
arrow function이용도 가능!

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
```
```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "JSX 표현식(Expression)";

        let seeSharp = {
            title: "c#",
            description: "내용들어오는 곳..."
        };

        function BookTitle(){
            return (
                <div className="row">
                    <h1>My book</h1>    
                </div>
            );
        }

        const BookFooter = () => <p>제가 집필한 책 목록 입니다</p>;

        const Copyright = () => {
            return (<p>Copyright &copy;</p>);
        }

        ReactDOM.render(
            (    
                <div className= "container mb-2">
                    <BookTitle/>
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
                    <BookFooter />
                    <Copyright />
                </div>
            ),
            document.getElementById("root")    
        );
   </script>
</body>
```
--------------------------------------
props 를 이용하여 값 전달하기

북카드의 속성의 속성값으로 . 으로 연결된 속성값이 다이나믹하게(동적으로) 전달이 된다.
```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "JSX 표현식(Expression)";

        let seeSharp = {
            title: "c#",
            description: "내용들어오는 곳..."
        };

        function BookTitle(){
            return (
                <div className="row">
                    <h1>My book</h1>    
                </div>
            );
        }

        const BookFooter = () => <p>제가 집필한 책 목록 입니다</p>;

        const Copyright = () => {
            return (<p>Copyright &copy;</p>);
        }

        function BookCard(props) {
            //console.log(props);
            //console.log(Object.keys(props));
            return (
                <div className= "container mb-2">
                    <div className="row">
                        <div className="col-12">
                            {props.title}
                        </div>
                    </div>
                    <div className="row">
                        <div className="col-2">
                            {props.title}
                        </div>
                        <div className="col-10">
                            {props.description}    
                        </div>
                    </div>
                </div>
            );
        }

        function BookList() {
            return(
                <>
                    <BookCard title={seeSharp.title} description={seeSharp.description}/>
                    <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다."/>
                    
                </>
            );
        }

        function BookApp() {
            return (
                <>
                    <BookTitle/>
                    <BookList/>
                    <BookFooter />
                    <Copyright />
                </>
            );
        }

        //최종 랜더링
        ReactDOM.render(
            <BookApp/>,
            document.getElementById("root")    
        );
   </script>
</body>
```
