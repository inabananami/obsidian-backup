接day3内容: [js笔记day3 >](./js笔记day3.md)
## 14) 函数
### 1. 函数的使用
```js
	//九九表を出力コードを関数に含む
	function print_nine_table(){
		//逆三角形を印刷する
		for(let i = 1; i <= 9; i++) {
			for(let j = 1; j <= i;j++) {
				document.write(`<div>${i}×${j}=${i * j}</div>`);
			}
			document.write(`<br>`);
		}
	}
	print_nine_table();
```
函数命名注意事项：
- 和变量命名基本一致
- 尽量使用小驼峰式命名法
- 前缀应该为动词
- 命名建议：常用动词约定（见下表）
<table>
	<thead>
		<th>动词</th>
		<th>含义</th>
	</thead>
	<tbody>
		<tr>
			<td>can</td>
			<td>判断是否可执行某个动作</td>
		</tr>
		<tr>                
			<td>has</td>
			<td>判断是否含义某个值</td>
		</tr>
		<tr>
			<td>is</td>
			<td>判断是否为某个值</td>
		</tr>
		<tr>
			<td>get</td>
			<td>获取某个值</td>
		</tr>
		<tr>
			<td>set</td>
			<td>设置某个值</td>
		</tr>
		<tr>
			<td>load</td>
			<td>加载某些数据</td>
		</tr>
	</tbody>
</table>
### 2. 函数的参数
同c语言，只是在定义参数时，不需要数据类型名称。
```js
	function getSquare(num1) {
		document.write(num1 * num1);
		document.write("<br>");
	}
	function getSquare2(num1, num2) {
		document.write(num1 * num2);
	}
	getSquare(3);
	getSquare2(3, 5);
```
**默认参数为NaN（undefined）。**
同C++，我们可以设置默认参数：
```js
	function getSquare(num1 = 30) {
		document.write(num1 * num1);
		document.write("<br>");
	}
	getSquare();
	getSquare(3);
```
没有填参数时，则使用默认参数，否则使用用户填写的参数。
### 3.练习-求学生总分
需求：学生的分数是一个数组，计算每个学生的总分
分析：
1. 封装一个求和函数
2. 传递过去的参数是一个数组
3. 函数内部遍历数组求和
代码示例：
```js
	function getScore(arr) {
		let sum = 0;
		for(let i = 0;i<arr.length;i++) {
			sum += arr[i];
		}
		document.write(sum);
	}
	let arr = [45,50,70,90,100,99,80,76,92,82,77,40];
	getScore(arr);
```
### 4. 函数返回值
```js
	function getSum(a, b) {
		return a+b;
	}
	function getNum() {
		return 200;
	}
	document.write(getSum(1,2));
	document.write("<br>");
	document.write(getNum());
```
### *5.案例：求最大值和最小值*
需求：
1. 求任意2个数中的最大值，并返回
2. 求任意数组中的最大值并返回这个最大值
3. 求任意数组中的最小值并返回这个最小值

**1. 求任意2个数中的最大值，并返回：**
```js
	function getNumMax(a, b) {
	return a>b?a:b;
	}
```
**2. 求任意数组中的最大值并返回这个最大值：**
```js
	function getArrMax(arr) {
		let max = arr[0];
		for(let i = 0; i < arr.length - 1; i++) {
			if(max < arr[i + 1]) {
				max = arr[i + 1];
			}
		}
		return max;
	}
```
**3. 求任意数组中的最小值并返回这个最小值**
```js
	function getArrMin(arr) {
		let min = arr[0];
		for(let i = 0; i < arr.length - 1; i++) {
			if(min > arr[i + 1]) {
				min = arr[i + 1];
			}
		}
		return min;
	}
```
**4.“主函数”**
```js
	document.write(getNumMax(2,100));
	document.write("<br>");
	document.write(getArrMax([2,4,5,10,12,3,5,6]));
	document.write("<br>");
	document.write(getArrMin([2,4,5,10,12,3,5,6]));
```
### 6. 作用域
1. 函数变量作用域：
```js
	function getScore(arr) {
		let sum = 0;
		for(let i = 0;i<arr.length;i++) {
			sum += arr[i];
		}
		document.write(sum);
	}
	document.write(sum); //これではエラーが発生しようになる
```
2. for循环内变量作用域：
```js
	for(let i = 0; i < arr.length; i++) {
		document.write(arr[i]);
	}
	document.write(i); //これもエラーが発生しようになる
```
3. 全局有效的变量：
```js
<script>
	let i;
	for(i = 0; i < arr.length; i++) {
		document.write(arr[i]);
	}
	document.write(i); //これはエラーが発生しない
</script>
```
**特殊情况：函数内部的变量若没有赋值，则默认为全局变量。**
### 7. 匿名函数
1. 函数表达式：
```js
	//ここの関数は匿名関数です
	let fn = function(x, y) {
		document.write(x + y);
	}
	fn(1, 3);
```
匿名函数的调用只能在函数体的后面，不能在前面。
2. 具名函数可以在函数体后面和前面调用。
### 8.立即执行函数
使用场景：避免全局变量之间的污染。
**语法：**
```js
	//方法1
	(function() {console.log(11) })();
	//方法2
	(function() {console.log(11) }());
	//呼び出されなくて、まっすぐ実行
```
**使用例：**
```js
	//使用例
	//この場合は衝突（しょうとつ）がある
	// let num = 10;
	// let num = 20;
	//この問題を防ぐためにIIFEを使う
	(function(){let num = 10})();
	(function(){let num = 20})();

	//例2:
	(function(x, y) {
		console.log(x + y);
	})(1, 5);
```
### 9. 综合案例 - 时间计算函数
需求：用户输入秒数，可以自动转换为时分秒。
```js
	function setTime() {
		let time = 0;
		time = parseInt(prompt(`秒数を入力してください：`));
		let hour = parseInt(time / 3600);
		let minute = parseInt((time - hour * 3600) / 60); 
		let second = parseInt((time - hour * 3600 - minute * 60));
		document.write(`${time}秒を${hour}時間${minute}分${second}秒に転換する。`);
	}
	setTime();
```