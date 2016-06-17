Link组件to的属性值和当前路由一致，我们希望设置当前链接的样式。

<br>

--可以通过**Link组件的activeStyle属性**设置。

<br>

> src/App.js

<br>

	const Links = () => 
	    <nav>
	        <Link activeStyle={{color:'green'}} to="/">Home</Link>
	        <Link activeStyle={{color:'green'}}  to="/about">About</Link>
	        <Link activeStyle={{color:'green'}}  to="/contact">Contact</Link>
	    </nav>

<br>

> localhost:3333

<br>

**Link组件的activeClassName属性**也同样可以做到。

<br>

> src/style.css

<br>

	nav a {
	  display: block;
	}
	
	.active {
	    color: green
	}

<br>

> src/App.js

<br>

	const Links = () => 
	    <nav>
	        <Link activeStyle={{color:'green'}} to="/">Home</Link>
	        <Link activeStyle={{color:'green'}}  to="/about">About</Link>
	        <Link activeClassName="active"  to="/contact">Contact</Link>
	    </nav>

<br>

> localhost:3333

<br>



