## 根据自检清单 每日一记

来自 [一名【合格】前端工程师的自检清单](https://mp.weixin.qq.com/s?__biz=MzAwNDcyNjI3OA==&mid=2650842922&idx=1&sn=9430980473c8b55de16f13ec47b6cba9&chksm=80d38c43b7a40555c2bc3ae5801d554145ec547a0a2cea34d4ecd60f11eed6f94c59a4a05d9f&scene=0&xtrack=1&key=f8a21a8df9909cbbceeacb33f9612d5cb45858249099c33a4ecfa99ad453c192c27a62acbd22a496f9949636e9778ff013d7e2555ad88e403a664bb3955a1584c157ee34db81e5d55b2c34de354551aa&ascene=1&uin=MjkwNDAwMTQzNw%3D%3D&devicetype=Windows+10&version=62060833&lang=zh_CN&pass_ticket=FzRfPh7EJrl07iw1IJdj%2BlRCbQd9zm6HJh8Nfwg4xmawW9Z27DcogAEmNcixiGwc##)

### 1.JavaScript基础
* JavaScript规定了几种语言类型

	<font color=#eea236>Boolean、Null、Undefined、Number、String、Object、Symbol (ES6 引入新的原始数据类型)</font>
	   
	   原始/值数据类型：变量是存放在栈区的（栈区指内存里的栈内存）
		    简单的数据段。按值访问，可以操作保存在变量中实际的值。（null、undefined特殊）
			* Boolean: 布尔
			* Null: 空值 空对象/对象不存在 
				表示尚未存在的对象，常用来表示函数企图返回一个不存在的对象。
			* Undefined: 缺失值
				所有已声明但是没有初始化的变量，默认值都为undefined。
				函数没有明确返回值的时候，会默认返回undefined。
				调用函数时应该提供的参数还没有提供，该参数就等于undefined
				对象没有赋值的属性，该属性的值就等于undefined
			* Number: 数字
			* String: 字符串
			* Symbol: Symbol值通过symbol函数生成,表示独一无二的值
		
		引用/对象数据类型：值是同时保存在栈内存和堆内存中的对象
			有多个值构成的对象。引用类型的值是按引用访问的。JavaScript不允许直接访问内存中的位置，也就是说不能直接操作对象的内存空间,只能操作对象在栈内存中的引用地址。
			* Object: 对象类型 例如：Object 、Array 、Function 、Data等
			
	思考1:  [js 基本类型与引用类型的区别一](https://www.cnblogs.com/focusxxxxy/p/6390536.html)
	
	以下总结摘自: [js 基本类型与引用类型的区别二](https://www.cnblogs.com/cxying93/p/6106469.html)   
	
		总结区别
		
		　　a 声明变量时不同的内存分配：　
		
		　　1）原始值：存储在栈（stack）中的简单数据段，也就是说，它们的值直接存储在变量访问的位置。
		
		　　　　这是因为这些原始类型占据的空间是固定的，所以可将他们存储在较小的内存区域 – 栈中。这样存储便于迅速查寻变量的值。
		
		　　2）引用值：存储在堆（heap）中的对象，也就是说，存储在变量处的值是一个指针（point），指向存储对象的内存地址。
		
		　　　  这是因为：引用值的大小会改变，所以不能把它放在栈中，否则会降低变量查寻的速度。相反，放在变量的栈空间中的值是该对象存储在堆中的地址。
		
		　　　  地址的大小是固定的，所以把它存储在栈中对变量性能无任何负面影响。
		
		　　b 不同的内存分配机制也带来了不同的访问机制
		　　　
		　　1）在javascript中是不允许直接访问保存在堆内存中的对象的，所以在访问一个对象时，
		　　　　首先得到的是这个对象在堆内存中的地址，然后再按照这个地址去获得这个对象中的值，这就是传说中的按引用访问。
		　　2）而原始类型的值则是可以直接访问到的。
		　　
		　　c 复制变量时的不同
		　　
		　　1）原始值：在将一个保存着原始值的变量复制给另一个变量时，会将原始值的副本赋值给新变量，此后这两个变量是完全独立的，他们只是拥有相同的value而已。
		　　2）引用值：在将一个保存着对象内存地址的变量复制给另一个变量时，会把这个内存地址赋值给新变量，
		　　　　也就是说这两个变量都指向了堆内存中的同一个对象，他们中任何一个作出的改变都会反映在另一个身上。
		　　　　（这里要理解的一点就是，复制对象时并不会在堆内存中新生成一个一模一样的对象，只是多了一个保存指向这个对象指针的变量罢了）。多了一个指针
		　
		　　d 参数传递的不同（把实参复制给形参的过程）
		　　
		　　首先我们应该明确一点：ECMAScript中所有函数的参数都是按值来传递的。
		　　但是为什么涉及到原始类型与引用类型的值时仍然有区别呢？还不就是因为内存分配时的差别。 　
		　　1）原始值：只是把变量里的值传递给参数，之后参数和这个变量互不影响。
		　　2）引用值：对象变量它里面的值是这个对象在堆内存中的内存地址，这一点你要时刻铭记在心！
		　　　　因此它传递的值也就是这个内存地址，这也就是为什么函数内部对这个参数的修改会体现在外部的原因了，因为它们都指向同一个对象。
	
	思考2: 如何判断数据类型 ？
	
	
* JavaScript对象的底层数据结构是什么

* Symbol类型在实际开发中的应用、可手动实现一个简单的 Symbol

* JavaScript中的变量在内存中的具体存储形式

* 基本类型对应的内置对象，以及他们之间的装箱拆箱操作

* 理解值类型和引用类型

* null和 undefined的区别

* 至少可以说出三种判断 JavaScript数据类型的方式，以及他们的优缺点，如何准确的判断数组类型

* 可能发生隐式类型转换的场景以及转换原则，应如何避免或巧妙应用

* 出现小数精度丢失的原因， JavaScript可以存储的最大数字、最大安全数字， JavaScript处理大数字的方法、避免精度丢失的方法