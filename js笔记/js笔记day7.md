接js笔记day6：[[js笔记day6]]
GitHub外部链接：[js笔记day6](https://github.com/inabananami/obsidian-backup/blob/main/js%E7%AC%94%E8%AE%B0/js%E7%AC%94%E8%AE%B0day6.md)
## 8）事件监听
### 1. 什么是事件？
事件是在编程时系统内发生的动作或者发生的事情
比如用户在网页上单击一个按钮
### 2. 事件监听
即监听某个元素发生了什么事情，并做什么反应。
示例代码：
```js
<body>
    <button>wowowow</button>
    <script>
        const btn = document.querySelector("button");
        btn.addEventListener("click",function() {
            document.write(`<strong style="color: #DD0000;font-size: 300px;">危</strong>`);
        })
        btn.addEventListener("mouseover",function(){
            btn.style.width = "300px";
        })
        btn.addEventListener("mouseout", function(){
            btn.style.width = "100px";
        })
    </script>
</body>
```
## 9）事件等级和事件类型
### 1. 事件等级
- DOM L0
	`事件源.on事件 = function() {}`
- DOM L2
	`事件源.addEventListener(事件，事件处理函数)`
- 区别：
	on方式会被覆盖，addEventLstener方式可绑定多次，拥有事件更多特性，推荐使用。
### 2. 事件类型
1. 鼠标事件
<table>
	<thead>
		<th>事件</th>
		<th>事件意义</th>
	</thead>
	<tbody>
		<tr>
			<td>click</td>
			<td>鼠标点击</td>
		 <tr>
		<tr>
			 <td>mouseenter</td>
			 <td>鼠标经过</td>
		<tr>
		<tr>
			<td>mouseleave</td>
			<td>鼠标离开</td>
		<tr>
	</tbody>
</table>
2. 焦点事件
<table>
	<thead>
		<th>事件</th>
		<th>事件意义</th>
	</thead>
	<tbody>
		<tr>
			<td>focus</td>
			<td>获得焦点</td>
		 <tr>
		<tr>
			 <td>blur</td>
			 <td>失去焦点</td>
		<tr>
	</tbody>
</table>
3. 键盘事件
<table>
	<thead>
		<th>事件</th>
		<th>事件意义</th>
	</thead>
	<tbody>
		<tr>
			<td>Keydown</td>
			<td>键盘按下触发</td>
		 <tr>
		<tr>
			 <td>Keyup</td>
			 <td>键盘抬起触发</td>
		<tr>
	</tbody>
</table>
4. 表单输入触发
<table>
	<thead>
		<th>事件</th>
		<th>事件意义</th>
	</thead>
	<tbody>
		<tr>
			<td>input</td>
			<td>用户输入事件</td>
		 <tr>
	</tbody>
</table>
### 3. 焦点事件
代码示例：
```js
	const input = document.querySelector("input");
	input.addEventListener("focus", function() {
		console.log("focusが触発された");
	})
	input.addEventListener("blur", function() {
		console.log("focusが失った");
	})
```
### 4. 键盘事件
代码示例：
```js
	const input = document.querySelector("input");
	input.addEventListener("keydown", function() {
		console.log(`keyboard push down.`);
	})
	input.addEventListener("keyup", function() {
		console.log(`keyboard triggers up`);
	})
```
## 10）事件对象
### 1. 事件对象
-  部分常用属性
- type
	- 获取当前的事件类型
- clientX/clientY
	- 获取光标相对于浏览器可见窗口左上角的位置
- offsetX/offsetY
	- 获取光标相对于当前DOM元素左上角的位置
- key
	- 用户按下的键盘键的值
	- 现在不提倡使用keyCode

代码示例：
```js
	const input = document.querySelector("input");
	input.addEventListener("keyup", function(e) {
		// console.log(e.key);
		if(e.key == "Enter") {
			console.log(11);
		}
	})
```
### 2. 环境对象
指的是this对象。
“谁调用，this就是谁”是判断this指向的粗略规则。
代码示例：
```js
	//それぞれの関数もthis　環境オブジェクトがある 普通の関数にはthisがwindowに指す
	// function fn() {
	//     console.log(this);
	// }
	// fn();
	const btn = document.querySelector("button");
	btn.addEventListener("click", function() {
		//buttonに指す
		console.log(this);
             //buttonに指して、文字色を変える
            this.style.color = "red";
	})
```
### 3. 回调函数
如果将函数A作为参数传递给函数B时，我们称函数A为回调函数
代码示例：
```js
	function fn() {
		console.log(`コールバック関数です。`);
	}
	setInterval(fn, 1000);
```
## 11）事件流
### 1. 什么是事件流
事件流指的是事件完整执行过程中的流动路径。
### 2. 事件捕获
代码：
```js
	DOM.addEventListener(エベントタイプ，エベント処理関数，掴み機能を使うかどうか);
```
### 3. 事件冒泡
代码：
```js
    // 为父元素绑定事件
    document.querySelector('.parent').addEventListener('click', function () {
        alert('父元素被点击了');
    });

    // 为子元素绑定事件
    document.querySelector('.child').addEventListener('click', function (event) {
        alert('子元素被点击了');
        // 阻止事件冒泡
        event.stopPropagation();  // 取消事件的冒泡，事件将不会继续传播
    });
```
### 4. 阻止冒泡
代码：
```js
	事件对象.stopPropagation();
```
这句代码既能阻止冒泡，也能阻止事件捕获。
### 5. 事件解绑
on事件方式，直接使用null覆盖就可以实现事件的解绑
```js
//エベントをリンクする
btn.onclick = function() {
	alert(`clicked`);
}
//エベントを解除する
btn.onclick = null;
```
## 12）事件委托
事件委托是利用事件流的特征解决一些开发需求的知识技巧
优点：减少注册次数，可以提高程序性能
原理：事件委托其实是利用事件冒泡的特点。
- 给父元素注册事件，当我们触发子元素的时候，会冒泡到父元素身上，从而触发父元素的事件
代码：
```js
<body>
	<ul class="list">
	    <li>Item 1</li>
	    <li>Item 2</li>
	    <li>Item 3</li>
	    <li>Item 4</li>
	</ul>
	<script>
	    // 为父元素（ul）添加事件监听器，委托事件给li
	    document.querySelector('.list').addEventListener('click', function(event) {
	        // 判断点击的目标是否是li元素
	        if (event.target.tagName === 'LI') {
	            alert('你点击了: ' + event.target.textContent);
	        }
	    });
	</script>
</body>
```
## 一、本地存储介绍
我们可以在本地浏览器存储大量的数据。
1. 数据可以存在用户浏览器中
2. 设置，读取方便，甚至页面刷新不丢失数据
3. 容量较大，sessionStorange和localStorange约5M左右
常见的使用场景：页面刷新数据不丢失