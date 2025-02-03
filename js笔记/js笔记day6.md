开始WEBAPIs的学习。
### 前言. 变量声明
1. 在`var,let,const`之中，建议用const。
# 一、DOM和BOM
## 1）作用与分类
- 作用：就是用JS去操作html和浏览器
- 分类：DOM（文档对象模型）、BOM（浏览器对象模型）
## 2）什么是DOM
- DOM（Document Object Model——**文档对象模型**）是用来呈现以及与任意HTML或XML文档交互的API
- 是专门用来操作网页内容的
## 3）DOM对象
- DOM对象是集合操作html的所有方法的集合。
示例：
```js
	const div = document.querySelector("div");
	//たくさんのオブジェクトを見せられる
	console.dir(div);
```
- DOM的核心思想
	- 把网页内容当做**对象**处理
- document对象
	- 是DOM里提供的一个**对象**
	- 所以它提供的属性和方法都是**用来访问和操作网页内容的**
		- 例子：document.write()
	- 网页所有内容都在document里面
## 4）获取DOM元素
- 根据css选择器来和获取DOM元素（重点）
示例代码：
```js
	//cssを通じて、DOM要素を獲得する(""の中でcss選択器の文法を挿入する)
	const box = document.querySelector("div");
	console.log(box);
	const box2 = document.querySelector(".box");
	console.log(box2);
	const nav = document.querySelector("#nav");
	console.log(nav);
	ulの一つのliを獲得する
	const li = document.querySelector("ul li:first-child");
	console.log(li);
```
其中，返回值是字符串，包含一个或多个字符串。
返回值是css选择器匹配的第一个元素。
- 我们可以对选中的元素进行修改：
```js
	//ulの一つのliを獲得する
	const li = document.querySelector("ul li:first-child");
	console.log(li);
	//ピンク色に変わる
	li.style.color = "#ED7D95";
```
- 可以用`document.querySelectorAll()`选中所有元素。
```js
	//この場合は全ての要素を選択して、偽配列を作成する
	const liall = document.querySelectorAll("li");
	liall[1].style.color = "skyblue";
	liall[2].style.color = "red";
```
## 5）操作元素内容
1. **元素innerText属性**
- 将文本内容添加/更新到任意标签位置
- 显示纯文本，**不解析标签**
代码示例：
```js
    <div class="box">テスト内容です</div>
    <script>
        //1.要素を獲得する
        const box = document.querySelector(".box");
        //2.文字の内容を直す
        console.log(box.innerText);  //文字の内容を獲得する
        box.innerText = "直した文字です。";  //文字の内容を直す
    </script>
```
2. **元素innerHTML属性**
- 将文本内容添加/更新到任意标签位置
- 会解析标签，多标签建议使用模板字符
代码示例：
```js
	//タグを解析するようになる
	box.innerHTML  = "<strong>立派な文字です</strong>"; 
```
## 6）操作元素属性
### 1. 操作元素常用属性
- 最常见的属性比如：href，title，src等
- **语法：**
```js
オブジェクト名.属性 = データ;
```
代码示例：
```js
	//画像の要素を獲得する
	const pic = document.querySelector("img");
	//画像のリンクを直す
	pic.src = "../../1.html/resourse/nina sox.png";
	//画像のタイトルを直す
	pic.title = "仁菜がsoxを体験した";
```
### 2. 操作元素样式属性
- 还可以通过JS设置/修改标签元素的样式属性
- 不如通过轮播图小圆点自动更换颜色样式
- 点击按钮可以滚动图片，这是移动的图片的位置left等等
学习路径：
1. 通过style属性操作css
2. 操作类名（className）操作css
3. 通过classList操作类控制css
#### （1）通过style属性操作css
```js
	//1.要素を獲得する
	const box = document.querySelector(".box");
	//2.スタイル属性を直す　オブジェクト名.style.スタイル属性 = "データ"
	box.style.width = "300px";
	//3.cssの中でハイフンをつけている属性には、ローワーキャメルケースへ直す
	box.style.backgroundColor = "skyblue";
       box.style.borderTop = "3px dashed #EE7788";
```
#### （2）通过类名操作css
**语法：**
```js
	//activeはcssの一つのクラス名です
	要素.className = "active"
```
示例：
```js
<style>
	div {
		width: 200px;
		height: 200px;
		background-color: pink;
	}
	.box {
		width: 300px;
		height: 300px;
		background-color: skyblue;
		margin: 100px auto;
		padding: 10px;
		border: 1px solid #000;
	}
</style>
</head>
<body>
    <div></div>
    <script>
        const div = document.querySelector("div");
        //クラス名を追加する。classはキーワードです。ここでclassNameを使う
        //そうすると、新しいスタイルを使うようになる
        div.className = "box";
    </script>
</body>
```
还可以这样使用：`div.className = "nav box"`，代表了既有nav也有box。
#### （3）通过classList操作类控制css
代码示例：
```js
	const box = document.querySelector(".box");
	// 新しいクラス名を追加する add() クラス名に点を加えない
	// box.classList.add("active");
	// クラス名を削除する remove() クラス名に点を加えない
	// box.classList.remove("box");
	//クラスを切り替える toggle() あるなら削除、ないなら加える
	box.classList.toggle('active');
```
### 3. 随机轮播图案例
需求：每刷新一次随机展示一张轮播图。
```js
<style>
	* {
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		text-decoration: none;
		list-style-type: none;
	}
	.slider {
		width: 560px;
		height: 400px;
		overflow: hidden;
		margin: 10px auto;
		border-radius: 15px;
		box-shadow: 3px 3px 10px #888;
	}
	.slider-wrapper {
		width: 100%;
		height: 320px;
	}
	.slider-footer {
		position: relative;
		width: 100%;
		height: 100px;
		z-index: 100;
	}
	.slider-footer .toggle {
		position: absolute;
		right: 0;
		top: 12px;
		display: flex;
	}
	.slider-footer .toggle button {
		margin-right: 12px;
		width: 28px;
		height: 28px;
		appearance: none;
		border: none;
		background: rgba(255, 255, 255, 0.1);
		color: #fff;
		border-radius: 4px;
		cursor: pointer;
	}
	.slider-footer .toggle button:hover {
		background: rgba(255, 255, 255, 0.2);
	}
	.slider-footer p {
		color: #fff;
		font-size: 18px;
		margin-bottom: 10px;
		margin-left: 5px;
		padding: 5px;
	}
	.slider-indicator {
		position: relative;
		list-style: none;
		display: flex;
		align-items: center;
		left: 7px;
		top: 7px;
	}
	.slider-indicator li {
		width: 8px;
		height: 8px;
		margin: 4px;
		border-radius: 50%;
		background: #fff;
		opacity: 0.4;
		cursor: pointer;
	}
	.slider-indicator li.active {
		width: 12px;
		height: 12px;
		opacity: 1;
	}
</style>
</head>
<body>
<div class="slider">
	<div class="slider-wrapper">
		<img src="./画像/blue.png" alt="">
	</div>
	<div class="slider-footer">
		<p>测试文本测试文本测试文本测试文本</p>
		<ul class="active slider-indicator">
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
			<li></li>
		</ul>
		<div class="toggle">
			<button class="prev">&lt;</button>
			<button class="next">&gt;</button>
		</div>
	</div>
</div>
<script>
	const sliderData = [
		{url: "./画像/pink.png", title: 'title_test_is_so_beautifully_nice!', color: "rgb(114,51,4)"},
		{url: "./画像/gray.png", title: 'title_test_is_so!', color: "rgb(114,51,4)"},
		{url:" ./画像/red.png", title: 'title_test_is', color: "rgb(114,51,4)"},
		{url: "./画像/brown.png", title: 'title_test', color: "rgb(114,51,4)"},
		{url: "./画像/yellow.png", title: 'title_test_is_so_beautifully!', color: "rgb(114,51,4)"},
		{url: "./画像/blue.png", title: 'title_test_is_so_beauty!', color: "rgb(114,51,4)"},
		{url: "./画像/green.png", title: 'title_test_is_so_beautiful!', color: "rgb(114,51,4)"},
		{url: "./画像/purple.png", title: 'title!', color: "rgb(114,51,4)"}
	]
	const random = Math.floor(Math.random() * sliderData.length);
	console.log(sliderData[random]);
	const img = document.querySelector(".slider-wrapper img");
	img.src = sliderData[random].url;
	const p = document.querySelector(".slider-footer p");
	p.innerHTML = sliderData[random].title;
	const footer = document.querySelector(".slider-footer");
	footer.style.backgroundColor = sliderData[random].color;
	const li = document.querySelector(`.slider-indicator li:nth-child(${random + 1})`);
	li.classList.toggle('active');
</script>
</body>
```
### 4. 获取设置表单的值
代码如下：
```js
<body>
    <!-- <input type="text" value="computer"> -->
    <input type="checkbox">
    <button>click</button>
    <script>
        //要素を獲得する
        const uname = document.querySelector("input");
        //データを獲得する　フォームデータを獲得するため　フォーム.valueを使う
        console.log(uname.value);
        console.log(uname.innerHTML);   //innerHTMLは獲得できない
        // uname.value = "I want to buy PC"; //要素のデータが変える
        console.log(uname.type);
        // uname.type = "password"; //要素のタイプが変える
        
        //要素を獲得する
        const ipt = document.querySelector("input");
        console.log(ipt.checked);
        ipt.checked = true;

        //獲得する
        const button = document.querySelector("button");
        console.log(button.disabled);
        button.disabled = true;
    </script>
</body>
```
### 5.H5自定义属性
代码如下：
```js
<body>
    <div data-id="1" data-spm="unknown">1</div>
    <div data-id="2">2</div>
    <div data-id="3">3</div>
    <div data-id="4">4</div>
    <div data-id="5">5</div>
    <script>
        const one = document.querySelector("div");
        console.log(one.dataset.id);
        console.log(one.dataset.spm);
    </script>
</body>
```
## 7）定时器 - 间歇函数
### 1.开启定时器
代码示例：
```js
	//1
	setInterval(function(){
		console.log(`1s per time`);
	}, 1000);
	//2
	function fn() {
		console.log(`1s per time`);
	}
	setInterval(fn(),1000);
```
### 2.关闭定时器
代码示例：
```js
	//タイマーをクリアする
	const x = setInterval(fn(),2000);
	clearInterval(x);
```