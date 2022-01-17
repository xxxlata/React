# class 형 컴포넌트 만들기

es6 의 클래스를 이용하여 클래스형 컴포넌트를 만드는것
그런데 추가적으로 react 컴포넌트형이기 때문에 상속을 해줘야한다.
class BookApp extends React.Component

render() 펑션이 반드시 있어야한다.
```
        //함수형 컴포넌트
        function BookAppOther() {
            return (
                <>
                    <BookTitle/>
                    <BookList sortOrder="ASC"/>
                    <BookFooter />
                    <Copyright />
                </>
            );
        }

        //클래스형 컴포넌트

        class BookApp extends React.Component {
            render() {
                return (
                    <>
                        <BookTitle/>
                        <BookList sortOrder="ASC"/>
                        <BookFooter />
                        <Copyright />
                    </>
                );
            }
        }
```
--------------------------------------------------------
# 상태와 이벤트
react 에서는 상태관리를 위해서 state라는 것을 설정할 수 있다.
람다식으로 코드를 써줄 수 있지만
펑션으로 만들어서 사용하는 것도 가능하다.
```
<body>
   <div id="root"></div> 
   <script type="text/babel">
        
        let title = "상태와 이벤트";

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

        class BookList extends React.Component {
            state = {
                theme: "white"
            }
            buleTheme = () => this.setState({theme: 'blue'}); 
            whiteTheme = () => this.setState({theme: 'white'}); 
            render(){
                return(
                    <>
                        <div>{this.state.theme === "white" ? "white theme" : "blue theme"}</div>
                        <div>
                                <button onClick = { () => {this.setState({theme: 'white'}); }}>White</button>
                                <button onClick = { this.whiteTheme }>White2</button>
                                <button onClick = { () => {this.setState({theme: 'blue'}); }}>blue 1</button>
                                <button onClick = { this.buleTheme }>blue 2</button>
                        </div>
                        <BookCard title="ASP.Net &amp; Core를 다루는 기술" description="ASP.Net &amp; Core를 다루는 기술입니다." price={55000}/>
                        <BookCard title={seeSharp.title} description={seeSharp.description} price={30000}/>
                    </>
                );
            }
        }
    
        //클래스형 컴포넌트
        class BookApp extends React.Component {
            render() {
                return (
                    <>
                        <BookTitle/>
                        <BookList sortOrder="ASC"/>
                        <BookFooter />
                        <Copyright />
                    </>
                );
            }
        }

        //최종 랜더링
        ReactDOM.render(
            <BookApp/>,
            document.getElementById("root")    
        );
   </script>
</body>
```
