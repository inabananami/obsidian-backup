# 一、js简介与基本语法
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
# 3) js的注释
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
## 5) 变量
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
## 6) 数组
### 1.数组的基本使用
```js
	//配列の宣言
	let num = [];
	//配列の割り当て
	num = [1,2,3];
	//配列の出力
	for(let i = 0; i < 3; i++) {
		document.write(num[i]," ");
	}

        //文字があるなら、これで割り当てる
        let name = ["佐藤さん","戸山さん","上原さん"];
```
### 2.
