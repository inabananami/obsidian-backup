# 一、js简介与基本概念
js是在浏览器里的编程语言。
## 1）示例代码：
轮播图按钮：
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>1.体验js</title>
    <style>
        .pink {
            background-color: pink;
        }
    </style>
</head>
<body>
    <button class="pink">button1</button>
    <button>button2</button>
    <button>button3</button>
    <button>button4</button>
    <script>
        let bts = document.querySelectorAll('button')
        for(let i = 0; i < bts.length; i++) {
            bts[i].addEventListener('click', function(){
                document.querySelector('.pink').className = ''
                this.className = 'pink'
            })
        }
    </script>
</body>
</html>
```
## 2）js的书写位置
js的书写位置有：
1. 内部JS
2. 外部JS
3. 内联JS
 
**内部js**即在`<body>`内加入`<script>`，在script框内写js。通常放到html页面最下面
```html
<body>
	<!-- 上面是一串html代码 -->
    <script>
        alert('こんにちは、JS！')
    </script>
</body>
```
**外部js**即在`<script>`内，通过src引入外部js文件，引入到html页面中。
```js
alert('私は外部のjsファイル')
```
```html
<body>
    <script src="./js/my.js">
        //ここは内容を書くのはできない
    </script>
</body>
```
**内联js**直接写在标签内部。
```html
<body>
	 <button onclick="alert('`こんにちは')">こんにちは</button>
<body>
```
## 3) js的注释
### 1. js的注释有两种：
1. 单行注释
2. 块注释
**单行注释**如下：
```js
<script>
	//これは一行のコメントの例です
</script>
```
**块注释**如下：
```js
<script>
	/* これはブロックのコメント
	　の例です。*/
</script>
```
### 2.js的结束符
```js
    <script>
        //3.JS終了記号。終了記号を省略するかどうかどちらともいいです。具体的な要求はグループから告げるようになります。
        // alert('1');
        // alert('2');
        alert('3')
        alert('4')
    </script>
```
结束符可加可不加。
## 4）输入与输出语法
### 1. 输出
```js
	//出力文法
	document.write('アカウントを書いてください');
	document.write('<h1>タイトルです</h1>');
	//コマンダーで出力
	console.log('コマンダーでディスプレイする');
```
### 2.输入
```js
	//入力文法
	prompt('年齢を入力してください:  ');
```
## 5） 变量
### 1. 变量的声明（推荐）
```js
 //変数の宣言
	let x;
```
### 2. 变量的赋值
```js
	//変数の割り当て
	age = prompt('入力');
	//文字があるなら、''又は""を包むのか必要です
	name = "佐藤さん";
```
### 3. 变量的初始化
```js
	//変数を宣言ながら割り当て
	let age2 = 19;
	document.write(age2);
```
### 4. 变量的更新
```js
	let age = 18;
	//新たなデータを引き当てるなら、古いデーターが消えています
	age = 19;
```
**注：** let不可多次声明同一个变量。
### 5. 声明多个变量 （不推荐）
```js
	let age = 18, name = "佐藤さん";
```
### 6. 两个变量交换数据
```js
	//変数の宣言
	let num1 = 10;
	let num2 = 20;
	let temp;
	//出力
	document.write("num1=",num1,",num2=",num2);
	//データの交換    
	temp = num2;
	num2 = num1;
	num1 = temp;
	//出力
	document.write("<br>");
	document.write("num1=",num1,",num2=",num2);
```
### 7.变量声明规则与规范
**规则：**
1. 不能是关键字
2. 只能由"\_","字母","数字","$"组成，且数字不能开头
3. 字母<span style="color:#ff0000; font-weight: bold">严格区分大小写</span>，如Age和age是不同的变量
**规范：**
1. 起名要有意义
2. 遵守小驼峰命名法：
   - 第一个单词首字母小写，后面每个单词首字母大写。例：useNameSet。
### 8.var和let的区别
```js
	//一つ: 宣言しないでも使用できて、エラーを告げない
	num = 10;
	document.write(num);
	var num;
	
	//二つ: 宣言していた変数はもう一度宣言できる
	var num = 10;
	document.write(" , ",num);
	var num = 20;
	document.write(" , ",num);
```
## 6）数组简介
### 1.数组的基本使用
```js
	//配列の宣言
	let num = [];
	//配列の割り当て
	num = [1,2,3];
	//配列の出力1
	for(let i = 0; i < num.length; i++) {
		document.write(num[i]," ");
	}
	document.write("<br>");
	//配列の出力2
	document.write(num);
			document.write("<br>");

	//文字があるなら、これで割り当てる
	let name = ["佐藤さん","戸山さん","上原さん"];
	document.write(name);
	document.write("<br>");
	document.write(name.length);
```
## 7）常量
```js
	//定数を宣言する
	const G = 9.8;
	document.write(G);
```

```js
	//定数は更新されできない
	G = 9.9;
	document.write(G);
```

```js
	//定数を宣言するとき特定のデータをつけなければならない
	const PI;
```
## 8）数据类型
### 1.数据类型
js有以下数据类型：
**基本数据类型：**
1. number 数字型
2. string 字符串型
3. boolean 布尔型（true or false）
4. undefined 未定义型
5. null 空类型
**引用数据类型：**
1. object 对象
与Java不同，js属于**弱数据类型**语言。
```js
//弱いデータ種類の言語
let age =  18;  // 整数
let price = 88.99;  // 小数
let name = "wang";  // ストリング
```
```java
//強いデータ種類の言語
int age =18;
```
在js中，当变量被赋值了以后，我们才能确认是哪个类型。
**字符串类型：**
通过**单引号（**''**）、双引号(**""**)、或反引号(**\`\`**)**包裹的数据都叫字符串。
但是嵌套使用时必须遵循**外单内双，外双内单**的原则。
```js
	document.write("彼は'いい'人だね");
	document.write('私たちは"キラメク星"みたいなぁ');
```
可以使用**转义符(\\)** 输出引号。
```js
	document.write("彼は\"いい人\"だね");
```
**字符串拼接:**
使用**加号（+）** 拼接两个字符串：
```js
	document.write("舞台に立ってる私たちは"+"きらめく星みたいなぁ");
```
### 2.算数运算符
有"**\+**"、"**\-**"、"**\***"、"**\/**"、"**\%**"
```js
	document.write(1 + 1);
	document.write(1 - 1);
	document.write(1 / 1);
	document.write(4 % 2);
	document.write(1 + 1);
```
### 3.模板字符串
- \`\`(反引号)
- 在英文输入模式下按键盘的tab键上方那个键（1左边那个键）
- 内容拼接变量时，用${ }包住变量
```js
	let name = "香澄ちゃん";
	let age = 18;
	//外には``を使って、裏には${変数名}となる
	document.write(`キラキラドキドキの${name}はもう${age}歳になった。`);
	document.write("<br>");
```
### 4.布尔型、undefined和空类型
- 表示肯定与否定的时候，用boolean型。
```js
	let isTrue;
	isTrue = true;
	if(isTrue == true) {
		document.write("いいご飯を食べよう!");
	}
	else {
		document.write("今日はコンビニで晩ご飯を解決しよう");
	}
```
- 此状态下为undefined型。
```js
	let num;
	document.write(num);
```
- 此状态下为null型。
```js
	let obj = null;
	document.write(obj);
```
### 5. 检测数据类型
- 用typeof可以输出数据的类型
```js
	let num = 10;
	document.write(typeof(num));
```

## 9）类型转换
### 1. 隐式转换
此处1被悄悄地转换成了string型。
```js
	//これで1はstringへ転換した(暗黙の型変換)
	document.write("pink" + 1);
```
有**算数运算符（- \* \\ % ）** 的地方，所有数字被强制转换成**数字型**。
```js
	document.write(2 + "2");
	document.write("<br>");
	document.write(2 - 2);
	document.write("<br>");
	//算術演算子ある場合は、全ての数字はnumber型に転換する
	document.write(2 - "2");
```
同时，**单独的加号（+）** 也能将后面的数字转换为**数字型**。
```js
	//number型に転換するため、結果はnumberです
	document.write(typeof +"100");
```
### 2. 显式转换
直接表明要把某个数据转换为某个类型：
```js
	//明示的変換。前には一〇〇一ですが、後には101です
	document.write("100" + 1);
	document.write("<br>");
	document.write(Number("100") + 1);
```
还有**parseInt()** 与**parseFloat()** 。
```js
	//整数以外のデータを除く
	document.write(parseInt("100は整数です"));
	document.write("<br>");
	//浮動小数点数（ふどうしょうすうてんすう）以外のデータを除く
	document.write(parseFloat("0.111は小数です"));
```
## 10）day1总练习
输入商品价格，商品数量，收获地址，打印出表格。
**第一步：**
先写出完整的表格（样式不算）：
```html
	<h2>注文支払い確認ページ</h2>
	<table>
		<thead>
			<tr>
				<th>品物の名称</th>
				<th>品物の価格</th>
				<th>品物の数</th>
				<th>合計金額</th>
				<th>郵送先住所</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>iPhone 15 Pro Max</td>
				<td>${price}円</td>
				<td>${num}</td>
				<td>${price * num}円</td>
				<td>${add}</td>
			</tr>
		</tbody>
	</table>
```
**第二步：**
写出js输入代码：
```js
	let price = +prompt("品物の価格を入力してください：");
	let num = +prompt("品物の数を入力してください：");
	let add = prompt("郵送先住所を入力してください：");
```
**第三步：**
直接将整个表格用模板字符串输出：
```js
document.write(`
	<table>
		<thead>
			<tr>
				<th>品物の名称</th>
				<th>品物の価格</th>
				<th>品物の数</th>
				<th>合計金額</th>
				<th>郵送先住所</th>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td>iPhone 15 Pro Max</td>
				<td>${price}円</td>
				<td>${num}</td>
				<td>${price * num}円</td>
				<td>${add}</td>
			</tr>
		</tbody>
	</table>
`);
```
**第四步：**
删除原表格。