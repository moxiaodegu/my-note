### 变量提升
 - 变量的声明都将被提升到作用域顶端。
   ```javascript
		console.log(v1);
		var v1 = 100;
		function foo() {
			console.log(v1);
			var v1 = 200;
			console.log(v1);
		}
		foo();
		console.log(v1);
		// undefined  undefined 200  100
   ```

### let
1. 创建块级作用域。
2. 定义后不能重新定义。
3. 不存在变量提升。
5. 全局作用域下定义时不会被挂载到顶层对象上（window对象 / global 对象）

### let vs var
1. 作用域不同
2. var 存在变量提升
	> var 声明的变量和 let 或 const 声明的变量，在创建相应作用域的词法环境阶段，都会注册标识符，但仅通过 var 声明的变量存在会变量提升
3. var可重复定义
4. let存在暂时性死区。
	> 暂时性死区：在代码块内使用const命令和let命令声明变量之前，该变量都不可用

### const
1. 同let
2. 一旦初始化赋值，不可更改
3. 定义时必须初始化
4. 本质： 
 > const本质不是不能改变变量的值，是不能改变变量指向的内存地址，基本类型变量的值保存在这个变量指向的内存地址里，所以等同于一个常量，引用类型的变量指向的内存地址里保存的是一个指针，const只能保证这个指针不变，但是控制不了数据结构的改变


# 