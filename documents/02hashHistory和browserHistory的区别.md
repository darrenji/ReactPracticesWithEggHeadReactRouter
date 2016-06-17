> src/App.js

<br>

目前，我们使用的是hasHistory

	import React from 'react';
	import { Router, Route, Link, hashHistory } from 'react-router';
	
	const Home = () => <div><h1>Home</h1><Links /></div>;
	const About = () => <div><h1>About</h1><Links /></div>;
	const Contact = () => <div><h1>Contact</h1><Links /></div>;
	
	
	const Links = () => 
	    <nav>
	        <Link to="/">Home</Link>
	        <Link to="/about">About</Link>
	        <Link to="/contact">Contact</Link>
	    </nav>
	
	
	class App extends React.Component {
	    render(){
	        return (
	            <Router history={ hashHistory }>
	                <Route path="/" component={Home}></Route>
	                <Route path="/about" component={About}></Route>
	                <Route path="/contact" component={Contact}></Route>
	            </Router>
	        );
	    }
	}
	
	export default App;

<br>

如果换成browserHistory呢？

	import React from 'react';
	import { Router, Route, Link, browserHistory } from 'react-router';
	
	const Home = () => <div><h1>Home</h1><Links /></div>;
	const About = () => <div><h1>About</h1><Links /></div>;
	const Contact = () => <div><h1>Contact</h1><Links /></div>;
	
	
	const Links = () => 
	    <nav>
	        <Link to="/">Home</Link>
	        <Link to="/about">About</Link>
	        <Link to="/contact">Contact</Link>
	    </nav>
	
	
	class App extends React.Component {
	    render(){
	        return (
	            <Router history={ browserHistory }>
	                <Route path="/" component={Home}></Route>
	                <Route path="/about" component={About}></Route>
	                <Route path="/contact" component={Contact}></Route>
	            </Router>
	        );
	    }
	}
	
	export default App;

可以看到，在url后面没有哪些字符串了。但是，点击链接后再刷新，会报错。

<br>
> 切换回hashHistory

<br>
可以使用后退前进按钮。

<br>