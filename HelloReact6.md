# jsx에서 조건(3항) 연산자 사용하기

어센딩과 디센딩? 
js 문법에서 if else 문과 같은 연산자이다. 
jsx에선 if else 문을 사용할  수 없기 때문에 대신 3항 연산자를 이용한다.


랜더 프래그먼트 <></> 시작과 끝을 잡아주는 역할 

```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "조건(3항) 연산자";

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

        function BookListOther(props) {
            if(props.sortOrder === "ASC"){
                return(
                    <>                    
                        <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                        <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>      
                    </>
                );
            }
            else { 
                return(
                    <>
                        <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>
                        <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                    </>
                );
            }    
        }

        function BookList(props) {
            return(
                <>
                    {
                        (props.sortOrder === "ASC")
                    ?   
                        <>
                            <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                            <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>
                        </>
                    :
                        <>
                            <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>
                            <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                        </>
                    }
                </>
            );
        }

        function BookApp() {
            return (
                <>
                    <BookTitle/>
                    <BookList sortOrder="ASC"/>
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
