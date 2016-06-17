在路由配置中，如果有IndexRoute这个组件，会优先加载这个路由。

<br>

> src/App.js

<br>

	import React from 'react';
	import { Router, Route, Link, IndexRoute, hashHistory } from 'react-router';
	
	const Outer = (props) => <div><h1>Our site</h1><Links />{props.children}</div>;
	const About = () => <div><h1>About</h1></div>;
	const Contact = () => <div><h1>Contact</h1></div>;
	
	
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
	                <Route path="/" component={Outer}>
	                    <IndexRoute component={About}></IndexRoute>
	                    <Route path="contact" component={Contact}></Route>
	                </Route>
	            </Router>
	        );
	    }
	}
	
	export default App;



- 优先考虑IndexRoute,但其外层还有一个路由，首先加载Outer组件
- 虽然Outer组件和About组件在定义的时候没有嵌套关系，但由于路由有嵌套关系，此时，可以把Outer看做是About的父组件，所以必须有props.children
- IndexRoute是没有path属性的
- 被嵌套路由的path属性值不能有/

<br>

> localhost:3333

<br>


