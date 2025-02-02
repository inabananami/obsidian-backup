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
1. **元素innerHTML属性**
- 将文本内容添加/更新到任意标签位置
- 会解析标签，多标签建议使用模板字符
代码示例：
```js
	box.innerHTML  = "<strong>立派な文字です</strong>"; //タグを解析するようになる
```
