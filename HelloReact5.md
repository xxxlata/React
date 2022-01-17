# Destructuring Assignment (구조 파괴 할당 또는 구조 분해 할당)

즉 넘겨준 값을 props 로 받는 것이 아닌 단어 자체로 받아서 처리해주고싶을 때 사용

매게변수(props)를 사용하는것이 아닌 직접 입력한다.
```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "구조 파괴 할당";

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

        function BookCardOther(props) {
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

        function BookCard({title, description, price}) {
            return (
                <div className= "container mb-2">
                    <div className="row">
                        <div className="col-12">
                            {title}
                        </div>
                    </div>
                    <div className="row">
                        <div className="col-2">
                            {title}
                        </div>
                        <div className="col-10">
                            {description} 
                            <hr/>
                            {price + "원"}
                        </div>
                    </div>
                </div>
            );
        }

        function BookList() {
            return(
                <>
                    <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>
                    <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                    
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

