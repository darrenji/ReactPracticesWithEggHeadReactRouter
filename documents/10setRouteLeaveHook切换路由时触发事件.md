如何在切换路由时触发事件嗯？  
--reactRouter为我们准备了setRouteLeaveHook方法

<br>

react-router的路由存放在哪里呢？  
--存放在context.router中了

<br>

> src/App.js

<br>

	import React from 'react';
	import {
	  Router,
	  Route,
	  Link,
	  hashHistory
	} from 'react-router';
	
	
	class Home extends React.Component{
	    componentWillMount(){
	        this.context.router.setRouteLeaveHook(
	            this.props.route,
	            this.routerWillLeave
	        )
	    }
	    
	    routerWillLeave(nextLocation){
	        console.log(`leaving home for ${nextLocation.pathname}`)
	    }
	    
	    render(){
	        return <div><h1>Home</h1><Links /></div>
	    }
	}
	
	Home.contextTypes = {router: React.PropTypes.object.isRequired }
	
	const About = () => <div><h1>About</h1><Links /></div>;
	
	const Links = () => {
	    return (
	        <nav>
	            <Link to="/">Home</Link>
	            <Link to="about">About</Link>
	        </nav>
	    )
	};
	
	const App = () => {
	    return (
	        <Router history={ hashHistory }>
	            <Route path="/" component={Home}></Route>
	            <Route path="/about" component={About}></Route>
	        </Router>
	    )
	};
	
	export default App;

- 在组件的componentWillMount这个声明周期事件中定义了`this.context.router.setRouteLeaveHook`方法，第一个实参是代表当前的路由，第二个实参代表回调事件。
- 凡是用到react组件的context的时候，必须对contextTypes进行设置，否则报错。

<br>

