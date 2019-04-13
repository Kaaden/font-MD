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