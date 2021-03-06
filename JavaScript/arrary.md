# Array 方法
1. Array.from() 把类数组对象/可迭代对象浅拷贝创建一个新的数组
	> 类数组对象：有length属性的对象、arguments对象、nodeList对象
	> 可迭代对象：string、 set、map、Generator函数
2. Array.isArray()判断是否是数组
3. Array.of() 创建数组 和Array()区别：Array(5) 创建[,,,,]，Array.of(5) 创建[5]

# Array 实例方法
### 修改器方法
1. push 末尾添加数组，返回数组长度 （一个或多个）
2. pop 末尾删除数组，返回数组长度
3. shift 移除数组第一个元素，并返回该元素
4. unshift 在数组开头添加一个或者多个元素，返回数组新长度
5. splice 删除元素
6. reverse 颠倒数组的顺序slic
7. sort 数组排序，也可有回调函数，判断如何排序数组 省略回调函数会通过元素Unicode位点进行排序。

### 访问方法
1. concat 连接两个数组，并返回一个新数组。
2. indexOf/lastIndexOf 在数组中搜索，并返回索引(indexOf:第一次出现的位置、lastIndexOf最后一次出现的位置)
3. includes 判断数组是否有当前值
4. join 将数组元素连接成一个字符串。
5. slice 抽取当前数组中的一段元素组合成一个新数组。

### 迭代方法
1. forEach 在每个数组元素上执行callback
2. map 创建一个新数组，数组元素是元素组通过执行callback得来
3. filter 返回一个在回调函数上返回true的元素的新数组
4. every 当数组的每一个元素在回调函数上都返回true就返回true，否则返回false
5. some 只要一个数组中一个元素返回true就返回true，否则返回false
注：以上回调函数传入三个值，第一个为当前元素，第二个为当前元素索引，第三个为数组本身。
6. reduce 方法接收一个函数作为累加器，数组中的每个值（从左到右）开始缩减，最终计算为一个值。
    - [10,20,30].reduce( (first, second) => return first + second ) 返回 60；
	- arr.reduce(callback(accumulator（累计器）, currentValue(当前值),[, index（当前索引）[, array（原始数组）]])[, initialValue（初始值）])
	- redeceRight: 和reduce类似，从右至左开始
7. find 返回第一个符合的元素，找不到undefined
8. findIndex 返回第一个符合元素的下标，找不到undefined
9. keys 返回所有索引键的对象
10. values 返回包含所有值的对象
11. entries 返回键值对的对象
12. flat 指定深度递归数组并返回一个数组子数组的所有元素的新数组，用于展开多维数组
13. flatMap 使用映射函数映射每一个元素，将结果压缩成一个新数组。类似于 map连着深度值为1的flat  

		// Let's say we want to remove all the negative numbers and split the odd numbers into an even number and a 1
		let a = [5, 4, -3, 20, 17, -33, -4, 18]
		//       |\  \  x   |  | \   x   x   |
		//      [4,1, 4,   20, 16, 1,       18]

		a.flatMap( (n) =>
		(n < 0) ?      [] :
		(n % 2 == 0) ? [n] :
						[n-1, 1]
		)

		// expected output: [4, 1, 4, 20, 16, 1, 18]


# foreach 和 map 的区别
 - map分配内存空间存储新数组并返回，forEach()不会返回数据。
 - map和foreach都不改变原数组、都不可以中途停止

# 类数组对象
 - 外观和行为像数组，但是不共享他们所有的方法
    例如：函数内部可用的arguments对象
 -可以通过array的prototype（原生）方法可以处理类数组对象
 - 例如：
	1. Array.prototype.forEach.call(arguments, item => {
				console.log(item);
			});
	2. Array.prototype.reduce.call("astring", function(all,now) {
				return now+all
			},''); // 字符串倒叙

# 数组泛型方法


# 数组推导式

# 数组选取最大值
1. Math.max(...arr)
2. Math.max.apply(...arr)
3. sort()
4. reduce









