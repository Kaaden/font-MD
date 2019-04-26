# React 仅仅是 VIEW 层

## React  指令
    
	npm install dva-cli -g
	
	dva new project

## JSX优点 
  
	   <ul>
		  <li>实际上JSX是js（es6）的语法糖</li>
		  <li>使用jsx前需要在文件中导入 React:</li>
		  <li>可复用，html模块化，可以复制给js变量，自然可以复用</li>
		  <li>防止xss攻击</li>
		  <li>React DOM在渲染前会把内容转换为字符串，所以可以防止xss攻击</li>
		  <li>标签语义化</li>
	  </ul>
  
## JSX注意事项
		 <ul>
		  <li>使用 () 包裹html标签上面的例子，div外层用括号包裹，主要为了解决自动加分号可能引入的bug</li>
		  <li>jsx内写注释类似html的注释，但是需要放在{}里面</li>
		 </ul>
  
 ## jsx属性的规定 
		<ul>
		  <li>属性名：必需是驼峰式写法；</li>
		  <li>属性值：值可以是字符串或表达式{}值缺省时为true</li>
		</ul>

 ## jsx属性分类
    ### 分成三类：html属性、jsx属性、自定义属性。
		<ul>
		  <li>html的class在jsx里改为className</li>
		  <li>style属性值必须是个对象</li>
		  <li>jsx为了方便，添加了一些额外的属性，这些属性在后面的组件中用到，暂时只做了解，比如：ref 、key 、 children</li>
	  </ul>


 ## 设置属性的三种方式
   
		<ul>
		  <li>键值对形式</li>
		  <li>如前面所用到的都是这种方式</li>
		  <li>展开符形式(...)</li>
		  <li>用于一次性添加所有属性，展开符(...)用于展开所有属性</li>
		  <li>let myProps={
		　className:'class1 class2',
		　id:'cc'
		}
		const div=<div {...myProps}></div>
		//结果相当于
		const div=<div className='class1 class2' id='cc'></div></li>
	  </ul>
  
  
  
  
  
 ##组件的2种定义方式
	<ul>
		<li></li>
	</ul>
	1. 函数
	function Welcome(props){
		return <h1>Hello,{props.name}</h1>
	}
	props是使用组件时传递过来的属性，直接return一个jsx标签。
	2.类
	class Welcome extends React.Component{
		render(){
			return <h1>Hello,{this.props.name}</h1>
		}
	}
	属性props使用this获取，render方法需要return一个jsx标签。

组件的使用
	jsx创建后像一个普通标签一样使用，以 / 号封闭标签。属性会被传入组件的props对象里。
	const element=<Welcome name="cc"/>

组件的渲染
	react使用ReactDom.render方法渲染组件到浏览器，语法:
	ReactDOM.render(element,dom)
	ReactDOM.render(
		element,
		document.getElementById('root')
	)



什么是state？
	在类组件中，react使用state对象来存放组件的数据，state里的数据变化时，这个组件就会被重新渲染。
	使用state前必须在构造器中先初始化state。




生命周期
	组件从开始渲染到销毁是一个完整的生命周期，分三个阶段：

	1. Mounting组件挂载（渲染）
	componentWillMount：组件挂载之前调用
    componentDidMount：组件挂载之后调用(经常使用)

	2. Updating组件重新渲染
	componentWillReceiveProps：组件接收到一个新的prop时被调用。这个方法在初始化render时不会被调用。
	shouldComponentUpdate：在组件接收到新的props或者state时被调用，返回false不更新组件。
	componentWillUpdate
	componentDidUpdate

	3. Unmounting组件卸载（销毁）
	componentWillUnmount(经常使用)




绑定事件
	值是函数，在html事件的值是字符串，而react直接写成函数。
	//html写法
	<a onclick="infoTime()">21:00</a>
	//React写法
	<a onClick={this.infoTime}>21:00</a>

	阻止事件默认行为原生html在事件函数里return false来阻止事件，React中使用e.preventDefault方法阻止。比如上面的例子，点击a标签（需要加herf属性），默认会进行跳转，我们需要阻止跳转
	infoTime(e){
	　e.preventDefault()
	　alert("21:00")
	}

	实际运行发现弹出的是undefined，因为点击事件实际是window执行的，this.state.date中的this指向错误，我们期望this指向这个组件的实例，有2个方法，使用es5中的bind或者es6中的箭头函数(但箭头函数形式会在重新渲染时重新创建，可能造成性能问题，建议使用第一种方式)



redux是什么？
	redux是管理react state的工具（本文redux只用于react，不考虑其他框架）

	react中的state在简单的应用逻辑上还比较容易处理，但是对于过于复杂的应用，数据向下传递的次数多时就很费脑子了，容易出错，修改也不容易，尤其在react的【状态提升】问题比较大redux把state统一管理，你可以想象它把所有的state放在了一起，组成一个全局的普通对象（state），当你需要其中的值时，通过key获取即可，比较特别的是当需要更新值时，你必须通过返回一个新的state以覆盖原来的值。

redux三个部分
	reducer => 创建并更新state,reducer 是个返回state的函数，由它更新state

	action => 要更新的数据,action 是一个对象，里面存的是要更新的数据，当然你需要指定key去更新哪部分数据,它是更新store中的state数据唯一来源
	使用规则:
		1. 必须要使用type指定更新哪部分数据
		2. 使用 store.dispatch(action) 调用action去更新数据
		3.通常会把type定义为常量放在最上面
		4.action过多时，将actions放在一个单独的文件存放，便于维护
	store => 数据库，里面放着state，这部分是核心,store 是一个redux根据reducer生产的数据库对象，主要用来存放数据
	基本用法 Redux中存在几个概念：state, action, dispatch
	state: 依旧是组件的内部的状态 action: 组件动作，相应的改变组件内部的状态值 dispatch: 发出相应的动作



state vs props
	state的主要作用是用于组件保存、控制、修改自己的可变状态。state在组件内部初始化，可以被组件自身修改，而外部不能访问也不能修改。你可以认为state是一个局部的、只能被组件自身控制的数据源。state中状态可以通过 this.setState方法进行更新，setState会导致组件的重新渲染。

	props 的主要作用是让使用该组件的父组件可以传入参数来配置该组件。它是外部传进来的配置参数，组件内部无法控制也无法修改。除非外部组件主动传入新的props，否则组件的 props永远保持不变。

	state和 props有着千丝万缕的关系。它们都可以决定组件的行为和显示形态。一个组件的state中的数据可以通过props传给子组件，一个组件可以使用外部传入的props来初始化自己的 state。但是它们的职责其实非常明晰分明：state是让组件控制自己的状态，props 是让外部对组件自己进行配置。
