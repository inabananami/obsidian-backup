通过[[HTML笔记]]的学习，我们掌握了基础的html语法，学习css则是为了添加更多样式，使网页样式更加丰富好看。
# 一、css基础
## 1）css的编写位置
### 1、位置1：行内样式
可以直接在行内添加`style`标签。
示例：`<h1 style="color: pink;font-size: 70px;">僕のサイトへようこそ！</h1>`
### 2、位置2：内部样式
可以在`<head>`标签块处添加`<style>`标签，并在里面写css样式。
示例：
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
	h1{
            color:#ED7D95;
            font-size:40px;
        }
    </style>
</head>
<body>
	<h1>地球のみんな、ただいま！</h1>
</body>
</html>
```
### 3、位置3：外部样式
可以单独创建css文件在外部，用`<link>`标签引入css文件。
代码示例：
```html
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>位置2.内部スタイル</title>
    <link rel="stylesheet" href="./ポジション3.css">
</head>
<body>
    <h1>地球のみんな、ただいま！</h1>
    <img src="../../1.html/ayumu1.jpg" alt="ayumu">
    <h2>ピンク</h2>
    <h3>レッド</h3>
    <p>三船栞子役の小泉萌香</p>
    <p>三船栞子役の小泉萌香</p>
    <p>三船栞子役の小泉萌香</p>
    <p>三船栞子役の小泉萌香</p>
    <p>三船栞子役の小泉萌香</p>
    <img src="../../1.html/path_test/shioriko.png" alt="shioriko">
</body>
</html>
```

css以单独的文件形式存储在独立的位置，其代码如下：
```css
h1 {
    color: #ED7D95;
    font-size:40px;
}
h2 {
    color: #ED7D95;
    font-size:40px;
}
h3 {
    color: #FF0000;
    font-size:30px;
}
p {
    color: #37B484;
    font-size:20px;
}
img {
    width:300px;
}
```
## 2）样式表优先级
代码示例：
```html
<!DOCTYPE html>
<html lang="ja">
    <head>
        <meta charset="UTF-8">
        <title>スタイルシートの優先級</title>
    </head>

    <!-- <style>は<link>の中の外部スタイルは優先順位があります-->
    <!-- どれが後ろにあるなら、スタイルはそれに従うべきです -->
    <!-- <link>と<style>部分の順位を換えてみると、変化を見えます -->
    <style>
        h1 {
            color:aqua;
        }
    </style>
    <link rel="stylesheet" href="../2.css/1.css的编写位置/ポジション3.css">
    
    <body>
        <h1 style="color:pink">地球のみんな、ただいま！</h1>
        <h1>小泉萌香役の三船栞子です</h1>
    </body>
</html>
```
如代码所述，css的样式表优先级为**后来者居上**。将`<style>`与`<link>`互换，可以看到样式的变化。
## 3）css的语法规范
代码示例：
```css
<style>
	/* すべてのh1にスタイルを足してあげます */

	/* 第一の書き方 */
	h1 {
		/* フォント色は青いです */
		color: aquamarine;
		font-size: 40px;
	}
	/* 第二の書き方 */
	h1 { color: red;font-size: 40px; }
</style>
```
 三大要点：
 1. 元素名和括号间有空格。
 2. 样式冒号后面有空格。
 3. 样式写完后以分号结尾。
# 二、选择器
选择器为css的**重点部分**。其为css能实现丰富样式的骨架。
## 1）基本选择器
### 1、通配选择器
css中全局选择器，选中全部元素。
代码示例：
css代码：
```css
<style>
	* {
		color: pink;
		font-size: 40px;
	}
</style>
```
html示例：
```html
<h1>私のサイトへようこそ！</h1>
<h2>サイトの内容</h2>
<h3>作者：私</h3>
```
此选择器能将所有文字变成粉色，文字大小为40像素。
### 2、元素选择器
元素选择器将选中的元素变为指定样式。
代码示例：
```css
<style>
	h1 {
		color: pink;
		font-size: 50px;
	}
</style>
```

```html
<h1>私のサイトへようこそ！</h1>
```
上述文本颜色为粉色，大小为50像素。
### 3、类选择器
类选择器选中元素标签中被添加`class`属性的标签，并变为指定样式。在对应类名前面加`.`即可选中对应类。**类可以出现多次**。一个标签可以添加两个类，用空格隔开。
代码示例：
```css
<style>
	.intro {
		color: orange;
		font-size: 20px;
	}
</style>
```

```html
<h3>作者：私</h3>
<p class="intro">一、本サイトはIT技術、アイドル、音ゲーなどに関します。</p>
<p class="intro">二：IT技術は主にhtml、cssがあります。</p>
```
这样第二，三行文本颜色为橙色，大小为20px。h3则为默认样式。
### 4、ID选择器
ID选择器选中元素标签中被添加`id`属性的标签，并变为指定样式。在对应ID名前面加`*`即可选中对应ID。**ID只能出现一次**。
代码示例：
```css
<style>
	#main-title {
	color:pink;
	font-size: 40px;
	}
</style>
```

```html
    <h1 id="main-title">私のサイトへようこそ！</h1>
    <h3>作者：私</h3>
```
这样第一行文本颜色为粉色，大小为40px。h3则为默认样式。
## 2）复合选择器
### 1、交集选择器
可以选中元素和类、元素和id，同时拥有两种特征的文本才会被选中。
代码示例：
```css
<style>
	.rich {
		color: gold;
	}
	p.beauty {
		color: rgb(63, 166, 255);
	}
</style>
```

```html
<h2 class="rich">金持ち張三</h2>
<p class="beauty">子犬ワンちゃん</p>
<p class="beauty">子豚ペッパ</p>
```
这样第二、三行文本会变成蓝色，第一行文本会变成金色。
### 2、交集选择器
可以选择多个元素、类、ID，凡是拥有这些特征的文本都会被选中。
代码示例：
```css
<style>
	.rich {
		color: gold;
	}
	#rana,
	.rich,
	.beauty,
	.dog,
	.pig {
		font-size: 40px;
		background-color: rgb(135, 135, 135);
		width: 280px;
	}
</style>
```

```html
    <h2 class="rich good">金持ち張三</h2>
    <h2 class="beauty good">声優佐藤さん</h2>
    <h2>倒産した大和さん（スタイルを足さない）</h2>
    <hr>
    <p class="dog good">子犬ワンちゃん</p>
    <p class="pig good">子豚ペッパ</p>
    <p id="rana">野良猫の楽奈　ちゃん</p>
```
这样，第一，二，五，六，七行文本背景色为灰色，宽度280像素，文本大小40像素。
### 3、父元素与子元素
代码示例：
```html
<body>
    <div>
        <!-- divはliの祖先要素です -->
        <!-- 同様に、diⅴはh1の親要素であり、h1はdiⅴの子要素です -->
        <h1>私のサイトへようこそ！</h1>
        <!-- ulはliの親要素であり、liはulの子要素です-->
        <ul>
            <li>IT技術</li>
            <li>アイドル</li>
            <li>音ゲー</li>
            <li>
                <span>連絡先</span>
            </li>
        </ul>
    </div>
</body>
```
其中，`<ul>`是`<li>`的父元素，`<div>`是`<li>`的祖先元素。反之，`<li>`是`<div>`的子元素，是`ul`的子元素。
### 4、后代选择器
后代选择器，既可以选择后代的css选择器。**不限定于儿子元素，而是所有后代元素**。
- 可以是元素下面的后代元素：
```css
 ul li {
	color: rgb(0, 176, 68);
}
```
- 也可以是元素下面带类的后代元素：
```css
ol .intro {
	color: chocolate;
}
```
- 也可以是带类的父元素下面的后代元素：
```css
 .it-tech li {
	color: rgb(5, 230, 200);
}
```

对应的文本如下：
#### （1）元素下面的后代元素
```html
 <ul>
	<li>歌う</li>
	<li>踊る</li>
	<li>
		<a href="https://www.youtube.com/watch?v=xvIbyz-dZA0" target="_blank">応援する</a>
	</li>
	<div>
		<li>音ゲーをプレイする</li>
	</div>
</ul>
```
全部的文本会变成绿色。
#### （2）元素下面带类的后代元素 / 带类的父元素下面的后代元素
```html
 <ol class="it-tech">
        <li>フロントエンド</li>
        <div class="intro">紹介：ウェブ界面などの開発技術</div>
        <li>バックエンド</li>
        <li>UI</li>
    </ol>
```
第三行文本会变成巧克力色。其余的文本全是青色。
### 5、子代选择器
子代选择器与子代选择器不同，**只会选择子元素**，不会选择孙子元素（如选择器1）。可以嵌套使用（如选择器3）。可以与交集选择器合用（如选择器2）。
代码示例：
```css
/* 选择器1 */
div>a {
	color: #ED7D95;
}
/* 选择器2 */
div.cp>a {
	color: #01B7ED;
}
/*  选择器3 */
div>p>a {
	color: #E7D600;
}
```

```html
<div>
	<a href="#">上原さん</a>
	<a href="#" id="koizumi">小泉さん</a>
	<a href="#">大西さん</a>
	<p>
		<a href="#">相良さん</a>
		<div class="cp">
			<a href="#">前田さん</a>
		</div>  
	</p>
</div>
```
选择器1使`<p>`标签外的`<a>`标签变成粉色，选择器2使cp类`<div>`中的`<a>`变成蓝色，选择器3使除了选择器2中涉及的部分以外的`<a>`变成黄色。
### 6、兄弟选择器
兄弟选择器，其主要语法如下：
1. **只**选中`<div>`后面的第一个`<p>`兄弟元素：
```css
 div+p {
	color: #EEEEEE;
} 
```
2. 选中`<h1>`后面的全部`<p>`兄弟元素：
```css
h1~p {
	color: #ED7D95;
}
```
3. 选中**除了第一个**`<li>`的全部`<li>`兄弟元素：
```css
li+li {
	color: orange;
}
```
对应代码：
```html
<h1>私のサイトへようこそ！</h1>
<div>テスト</div>
<p>フロントエンド</p>
<p>バックエンド</p>
<p>Java</p>
<p>UI</p>

<!-- 下記は応用です -->
<ul>
	<li>フロントエンド</li>
	<li>バックエンド</li>
	<li>Java</li>
	<li>UI</li>
</ul>
```
所以，禁用1中的选择器，上部分所有`<p>`标签文本全部变成粉色，禁用2选择器，`<div>`后面的第一个`<p>`元素变成灰色，除了第一个`<li>`的元素，后续所有`<li>`元素都变成橙色。
### 7、属性选择器
代码示例：
```html
<div title="CS">CS2</div>
<div title="valorant">VARORANT</div>
<div title="music-game">osu!</div>
<div title="band">バンドリ！</div>
<div title="idol-game">リンク！ライク！ラブライブ！</div>
```
1. 若我们要选择所有带title属性的元素，我们可以这么写：
```css
[title] {
	color: rgb(199, 0, 0);
} 
```
此选择器意思是：给所有带`title`属性的文本染上暗红色。

2. 若我们要选择标题属性为valorant的文本，可以这么写：
```css
[title="valorant"] {
	color: #FF4654;
}
```
此选择器意思是：给带`valorant`的文本染上红色。

3. 若我们要选择首字母为"m"的文本，可以这么写：
```css
[title^="m"] {
	color: #F663A4;
}
```
此选择器意思是：给首字母为m的文本染上粉色。

4. 若我们要选择最后一个字母为"d"的文本，可以这么写：
```css
[title*="d"] {
	color: orange;
}
```
此选择器意思是：给最后一个字幕为d的文本染上橘色。
## 3）复合选择器 —— 伪类选择器
### 1、概念
- 伪类选择器是什么——非常像类选择器，但是不是类，是元素的一种特殊状态。

- 代码示例：
```css
/* 选择器1 */
/* 選択したのはまだ訪れたことのないa要素です */
a:link {
	color: orange;
}
/* 选择器2 */
/* 選択したのはもう訪れていたa要素です */
a:visited {
	color: grey;
}
```
```html
<a href="https://zh.moegirl.org.cn"> 萌娘百科（萌え娘の百科）へ</a>
<a href="https://google.com" target="_blank">グーグルへ</a>
<a href="https://ciallo.cc">ciallo!</a>
<a href="https://zh.moegirl.org.cn/上原歩夢">私の嫁</a>
```
选择器1选择的是没有访问过的`<a>`元素，并染上橙色。
选择器2选择的是访问过的`<a>`元素，并染上灰色。
### 2、动态伪类选择器
接**1、概念**，有几个新的伪类选择器：
```css
 /* 选择的是鼠标悬浮状态下的a元素 */
a:hover {
	color: skyblue;
}
/* 选择的是活跃状态下的a元素 */
a:active {
	color: pink;
}
/* 选择的是鼠标悬浮状态下的span元素 */
span:hover {
	color: #ED7D95;
}
/* 选择的是活跃状态下的span元素 */
span:active {
	color: antiquewhite;
}
/* 选择的是获取到焦点的input元素 */
input:focus {
	color: pink;
	background-color: rgb(255, 166, 0);
}
/* 选择的是获取到焦点的select元素 */
select:focus {
	color: pink;
	background-color: rgb(212, 138, 0);
}
```

```html
<a href="https://youtube.com">ユーチューブへ</a>
<a href="https://google.com" target="_blank">グーグルへ</a>
<span>上原さん</span>\
<br>
<input type="text">
<br>
<input type="text">
<br>
<input type="text">
<hr>
<h2>こんにちは！</h2>
<select>
	<option value="tokyo">東京</option>
	<option value="shizuoka">静岡</option>
	<option value="hukuoka">福岡</option>
	<option value="sapporo">札幌</option>
</select>
```


























































































































































































































































































































































































































































































































































































































































































































