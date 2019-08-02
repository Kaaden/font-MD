## JS 原生基础

  ### 基本数据类型
      
	  1.undefined null boolean number string  symbol(es6新增) 6种
	  
	  2.typeof null 虽返回object,但是null不是对象,而是基本数据类型的一种
	  
	  3.基本数据类型存储在栈内存，存储的是值
	  
	  4.复杂数据类型存储在堆内存，存储的是地址。当我们把对象赋值给另外一个变量的时候，复制的是地址，指向同一块内存空间，当其中一个对象改变时，另一个对象也会变化。
	  
  ### 检测类型问题
      
	  1.typeof 能够正确的判断基本数据类型，但是除了 null, typeof null输出的是对象 (typeof操作符返回一个字符串，表示未经计算的操作数的类型。)
	  
	  2.typeof 存在问题 typeof 不能正确的判断其类型， typeof 一个函数可以输出 'function',而除此之外，输出的全是 object,这种情况下，我们无法准确的知道对象的类型。
	  
	  3.instanceof (instanceof运算符用于测试构造函数的prototype属性是否出现在对象的原型链中的任何位置)可以准确的判断复杂数据类型，但是不能正确判断基本数据类型。(会报语法错误 Uncaught SyntaxError: Unexpected token instanceof)
	  
	  4.instanceof 是通过原型链判断的，A instanceof B, 在A的原型链中层层查找，是否有原型等于B.prototype，如果一直找到A的原型链的顶端(null;即Object.prototype.__proto__),仍然不等于B.prototype，那么返回false，否则返回true.
  
  ### 循环问题
  
      1.for...of循环：具有 iterator 接口，就可以用for...of循环遍历它的成员(属性值)。for...of循环可以使用的范围包括数组、Set 和 Map 结构、某些类似数组的对象、Generator 对象，以及字符串。for...of循环调用遍历器接口，数组的遍历器接口只返回具有数字索引的属性。对于普通的对象，for...of结构不能直接使用，会报错，必须部署了 Iterator 接口后才能使用。可以中断循环。
      
	  2.for...in循环：遍历对象自身的和继承的可枚举的属性, 不能直接获取属性值。可以中断循环。
	  
	  3.forEach: 只能遍历数组，不能中断，没有返回值(或认为返回值是undefined)。
	  
	  4.map: 只能遍历数组，不能中断，返回值是修改后的数组。
	  
  ### 判断数组问题
  
      let array=[1,2,3,4]
	  
	  1.使用 Array.isArray(array) 判断，如果返回 true, 说明是数组
	  
	  2.使用 array instanceof Array 判断，如果返回true, 说明是数组
	  
	  3.使用 Object.prototype.toString.call(array) 判断，如果值是 [object Array], 说明是数组
	  
	  4.通过 constructor 来判断，如果是数组，那么 arr.constructor === Array. (不准确，因为我们可以指定 obj.constructor = Array) 
	  
  ### 类数组和数组的区别
  
      1.类数组拥有length属性，其它属性（索引）为非负整数（对象中的索引会被当做字符串来处理）;
	  
	  2.不具有数组所具有的方法；
	  
	  3.类数组是一个普通对象，而真实的数组是Array类型。
	  
	  4.常见的类数组有: 函数的参数 arugments, DOM 对象列表(比如通过 document.querySelectorAll 得到的列表), jQuery 对象 (比如 $("div")).
	  
	  5.类数组可以转换为数组:Array.prototype.slice.call(arrayLike, start);  [...arrayLike];  Array.from(arrayLike);
	  
  ###  = = 和 = = = 区别
  
      1. = = = 只有类型以及值相同才返回true
	
	  2. = = 如果两者类型不同，首先需要进行类型转换
	  
  ### ES6中的class和ES5的类的区别
  
      1.es6 class内部所定义的方法是不可枚举的
	  
	  2.es6 class必须使用new调用
	  
	  3.es6 class不存在变量提升
	  
	  4.es6 class默认使用严格模式
	  
	  5.es6 class子类必须在父类的构造函数中调用super(),这样才有this对象,es5中类继承的关系是相反的,先有子类this,然后用父类的方法应用到this上
	  
  ### 数组哪些API会改变原数组
  
      1.splice/reverse/fill/copyWithin/sort/push/pop/unshift/shift  修改原数组
	  
	  2.slice/map/forEach/every/filter/reduce/entries/find 不修改原数组
	  
	  
  ### let、const 以及 var 的区别
  
      1.let 和 const 定义的变量不会出现变量提升，而 var 定义的变量会提升
	  
	  2.let 和 const 是JS中的块级作用域
	  
	  3.let 和 const 不允许重复声明(会抛出错误)
	  
	  4.let 和 const 定义的变量在定义语句之前，如果使用会抛出错误(形成了暂时性死区)，而 var 不会
	  
	  5.const 声明一个只读的常量。一旦声明，常量的值就不能改变(如果声明是一个对象，那么不能改变的是对象的引用地址)
	  
	  
	  
	  
	  
	  
  ### js监听事件以及移除事件

      window.addEventListener("scroll", this.onScroll)  
	  
	  window.removeEventListener("scroll", this.onScroll)
  
  ### 正则表达式
  
      1.手机号码：!/^1[3456789]\d{9}$/.test(phone)
	  
	  2.邮箱：!/^([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+@([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+\.[a-zA-Z]{2,3}$/.test(email)
	   
	 const regx = {
		"telPhone": /^(([0\+]\d{2,3}-)?(0\d{2,3})-)(\d{7,8})(-(\d{3,}))?$/,
		"mobilePhone": /^1[3456789]\d{9}$/,
		"email": /^([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+@([a-zA-Z0-9]+[_|\_|\.]?)*[a-zA-Z0-9]+\.[a-zA-Z]{2,3}$/,
		"idCard": /^[1-9]\d{7}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])\d{3}$|^[1-9]\d{5}[1-9]\d{3}((0\d)|(1[0-2]))(([0|1|2]\d)|3[0-1])\d{3}([0-9]|X)$/,
		"url": /(http|ftp|https):\/\/[\w\-_]+(\.[\w\-_]+)+([\w\-\.,@?^=%&:/~\+#]*[\w\-\@?^=%&/~\+#])?/,
	}
	  
	  
  ### 原型链检测类型
  
	  return Object.prototype.toString.call(val).slice(8, -1)
	  
	  (String,Boolean,Function,Number,Null,Undefined,Object,Array,Date,Symbol,Promise,Error，ReExp，Set)
	  
  ### 字符串长度问题
     javascript（utf-16编码）中，字符占多少字节,只需要求出字符串的长度然后乘以2便可
	 字节：const b =string.length*2
	 kb：const k=b/1024
	 mb:const mb=k/1024

	  
	  
	  
	  
	  
	  
	  