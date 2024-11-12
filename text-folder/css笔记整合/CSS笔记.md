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
这样，
- 我们的`<a>`标签在未访问时为橙色，访问过为黑色，鼠标悬浮时为天蓝色，鼠标点击时为粉色。
- 我们的`<span>`标签鼠标悬浮时为粉色，鼠标点击时为黄白色。
- 我们的`<input>`和`<select>`标签获取到焦点时为橘色。
### 3、结构伪类选择器
#### （1）选择第一个子元素
```css
div > p:first-child { 
color: red;
}
```
此样式将 `div` 内的第一个 `p` 元素的文本颜色设置为红色。
#### （2）选择所有后代中的第一个子元素
```css

div p:first-child {
	color: red;
}
```
此样式将 `div` 内所有 `p` 元素的第一个子元素的文本颜色设置为红色。

以下为html结构示例：
```html
<body>
    <!-- 結構1 -->
    <div>
        <p>中川さん：95点</p>
        <p>桜坂さん：90点</p>
        <p>上原さん：85点</p>
        <p>中須さん：48点</p>
    </div>

    <!-- 結構2 -->
    <div>
        <span>中川さん：95点</span> 
        <p>桜坂さん：90点</p>
        <p>上原さん：85点</p>
        <p>中須さん：48点</p>
    </div>

    <!-- 結構3 -->
    <p>テスト1</p>
    <div>
        <p>テスト2</p>
        <marquee>
            <p>テスト3</p>
            <p>中川さん：95点</p>
        </marquee>
        <p>桜坂さん：90点</p>
        <p>上原さん：85点</p>
        <p>中須さん：48点</p>
    </div>
</body>
```
结构1为选中第一个`<p>`元素；结构2为谁都不选中（因为没有第一个p子元素）；结构3选中`<div>`下的第一个`<p>`元素。
### 4、结构伪类选择器2
代码示例：
- 例一：如果我们想选择`<div>`的最后一个子元素，我们可以：
```css
/* 選択したのはdivの最後の子要素です（すべての兄弟に基づいて計算します）ーー　結構1 */
div>p:last-child{
	color: red;
}
```
`<div>`的最后一个子元素被染成红色。

- 例二：如果我们想选择`<div>`的第n个子元素，我们可以：
```css
/* 選択したのはdivの第n個のp子要素です（すべての兄弟に基づいて計算します）ーー　結構1 */
div>p:nth-child(3) {
	color: red;
}
```
`<div>`的第3个子元素被染成红色。
扩展：
```css
/* nの値について　ーー　結構2：
	1、０又は書かない：何も選択しない　ーー　ほとんど使わない
	2、n：すべての子要素を選択します　ーー　ほとんど使わない
	3、1から＋∞までの整数は、対応番号の子要素を選択します。
	4、2n又はeven：番号は偶数の子要素を選択します。
	5、2n＋1又はodd：番号は奇数の子要素を選択します。
	6、‐n+3：最初の三つを選択します。
 */
```
通过以上操作，我们可以选择特定序列的子元素。

- 例三：如果我们想选择`<div>`的第一个同类子元素，我们可以：
```css
div>p:first-of-type {
	color: red;
}
```
第一个`<p>`子元素被染成红色。

- 例四：如果我们想选择`<div>`的第n个同类子元素，我们可以：
```css
div>p:nth-of-type(3) {
	color: red;
}
```
第三个`<p>`子元素被染成红色。

### 5、结构伪类选择器3
代码示例：
- 例一：如果我们想要选择最后几个子元素（基于所有的兄弟），我们可以：
```css
div>p:nth-last-child(3) {
	color: red;
}
```
倒数第三个**且是`<p>`的**子元素会被染成红色。

- 例二：如果我们想要选择最后几个p元素（基于所有同类兄弟），我们可以：
```css
div>p:nth-last-of-type(2) {
	color: red;
}
```
倒数第二个`<p>`**元素**被染成红色。

- 例三：选择没有兄弟的子元素，我们可以：
```css
span:only-child {
	color: red;
}
```
没有兄弟元素的`<span>`元素被染成红色。

- 例四：选择没有**同类**兄弟的子元素，我们可以：
```css
span:only-of-type {
	color: red;
}
```
没有**同类**兄弟元素的子元素被染成红色。

- 例五：html根元素：
```css
:root {
	background-color: rgb(219, 219, 219);
}
```
整个背景变为灰色。

- 例六：选择**没有任何内容**的`<div>`元素：
```css
div:empty {
	width: 100px;
	height: 100px;
	background-color: red;
}
```
空的`<div>`元素背景是宽度和高度都为100px的红色背景。
### 6、否定伪类选择器
- 例一：选择不含`fail`属性的`<div>`的`<p>`子要素：
```css
div>p:not(.fail) {
	color: red;
}
```
**扩展：not后面可以嵌入属性选择器：**
```css
div>p:not(title^="w") {
	color: red;
}
```
选择的是首字母不是w的`<div>`的`<p>`子要素。

- 例二：选择除了`<div>`的第一个`<p>`子要素以外的`<p>`子要素。
```css
div>p:not(:first-child) {
	color: red;
}
```
### 7、UI伪类选择器
- 例一：选择已经选定的单选栏和多选栏：
```css
input:checked {
	width: 100px;
	height:100px;
	background-color: green;
	color: red;
}
```
选定的单选栏和多选栏尺寸为100px\*100px，但是背景色和颜色不会发生变化。

- 例二：选择禁用的input框：
```css
input:disabled {
	background-color: #909090;
}
```
禁用的input框变成灰色。

- 例三：选择可用的input框：
```css
input:enabled {
	background-color: pink;
}
```
可用的input框变成粉色。
### 8、目标伪类选择器
代码示例：
- css样式：
```css
div {
	background-color: pink;
	height: 500px;
}
div:target {
	background-color: greenyellow;
}
```
- html结构：
```html
<a href="#one">一番目に行きます</a>
<a href="#two">二番目に行きます</a>
<a href="#three">三番目に行きます</a>
<a href="#four">四番目に行きます</a>
<a href="#five">五番目に行きます</a>
<a href="#six">六番目に行きます</a>

<div id="one">一番目</div>
<br>
<div id="two">二番目</div>
<br>
<div id="three">三番目</div>
<br>
<div id="four">四番目</div>
<br>
<div id="five">五番目</div>
<br>
<div id="six">六番目</div>
```
如果`<div>`不是目标，则这个`<div>`颜色为粉色，高度为500px。
如果点击`<a>`跳转到指定地方，`<div>`成为目标，则这个`<div>`颜色变为黄绿色。
### 9、语言伪类选择器
代码示例：
- css样式：
```css
div:lang(zh-CN){
	color: red;
}
:lang(ja) {
	color: green;
}
```
- html结构：
```html
<div>専門学校</div>
<div lang="zh-CN">专科学校</div>
<p>フロントエンド</p>
<span>こんにちは！</span>
```
则语言为中文的元素为红色，为日语的元素为绿色。
### 10、伪元素伪类选择器
#### （1）概念
伪元素是？ —— 非常像元素，但是不是元素，是元素的特殊的位置。
#### （2）示例
- 例一：选择元素中的第一个文字。
```css
div::first-letter {
	color: rgb(111, 233, 255);
	font-size: 40px;
}
```
这个文字为青色，字体大小为40px。

- 例二：选择被鼠标选中的文字。
```css
div::selection {
	background-color: green;
	color: rgb(111,233,255);
}
```
被选中的文字背景色为绿色，文字颜色为青色。

- 例三：选择input框中的提示文字。
```css
input::placeholder {
	color: #ED7D95;
}
```
提示文字为粉色。

- 例四：选择p元素最初位置，并创建伪元素。
```css
p::before {
	content: "￥";
}
```
在每一个p标签的前面创建"￥"的伪元素。

- 例五：选择p元素最后位置，并创建为伪元素。
```css
p::after {
	content: ".00";
}
```
在每一个p标签后面创建".00"的伪元素。
## 4）选择器优先级
### 1、简单说明
简单来说，选择器的优先级遵守以下规律：

> [!选择器优先级] 
> **同级情况下：** 后来者居上
> **非同级情况下：** 行内样式 > ID选择器 > 类选择器> 元素选择器> 通配选择器

代码示例：
```css
#idol-otaku {
	color: red;
}

/* .intro {
	color: #a5fd21;
} */

/* h2 {
	color: orange;
} */

* {
	color: purple;
}
```

```html
<h2 class="intro" id="idol-otaku">アイドルオタクと申します！（笑</h2>
```
依次调换上述选择器顺序，可以看出选择器优先级的规律。
### 2、详细说明
情况变得复杂一点：
```css
#idol-otaku {
	color: #ED7D95;
}
div>p>span:nth-child(1) {
	color: green;
}
.container span.intro {
	color: red;
}
```
我们如何确定优先级呢？

当出现复合选择器时，有这种形式的计数表：
 > [!复合选择器计数表]
 > **（ #ID选择器个数 ， #类、伪类选择器个数 ， #元素、伪元素选择器个数 ）。**
 > 

如上述复合选择器：
```css
div>p>span:nth-child(1) {
	color: green;
}
```
此复合选择器有0个ID选择器、1个伪类选择器、3个元素选择器，故计数表为 **(0,1,3)**。

```css
.container span.intro {
	color: red;
}
```
此复合选择器有0个ID选择器、2个类选择器、1个元素选择器，故计数表为 **(0,2,1)**。

```css
#idol-otaku {
	color: #ED7D95;
}
```
此选择器有1个ID选择器，故计数表为 **(1,0,0)**。

> [!规律]
> **若一个选择器的 #ID选择器个数 大于其他选择器的 #ID选择器个数 ,则这个选择器优先级最高。**
> **其他 #元素、伪元素选择器个数 与 #类、伪类选择器个数 同理。**

html结构：
```html
<div class="container" id="test">
	<p>
		<span class="intro" id="idol-otaku">アイドルオタクと申します！（笑</span>
		<br>
		<span>無言フォローでも大丈夫です</span>
	</p>
</div>
```
因为第三个选择器拥有最多的ID选择器，所以第三个优先级最高，所以此状态下`<p>`下的第一个`<span>`元素为粉色。

若注释掉ID选择器，则继续对比剩下的两个复合选择器：第二个选择器拥有最多的类和伪类选择器，则这种情况下第二个选择器优先级最高。而不看元素和伪元素选择器的个数。

**注：将光标悬浮在选择器上，可以直接看到选择器的优先级**。
# 三、css的三大特性
## text- font- line- color具有继承性。
代码示例：
### （1）css样式
```css
div {
	color: red;
	font-size: 40px;
	background-color: skyblue;
}

p {
	color: purple;
}

* {
	color: grey;
}
```
### （2）html结构
```html
<div>
	divの文字です
	<span>spanの文字1です</span>
	<span>spanの文字2です</span>
	<span>spanの文字3です</span>
	<p>
		<span>spanの文字4です</span>
	</p>
</div>
```
若通配选择器被注释，则`<div>`下面的`<span>`元素文字颜色为红色。`<p>`下面的`<span>`元素文字颜色为紫色。并且`<div>`的其他样式也被`<span>`与`<p>`后代元素继承。这就是样式的继承性。

但是样式的继承性优先级很弱，根据前文***选择器的优先级***所述，通配选择器优先级**最低**，但是继承样式优先级比统配选择器**更低**。说明如下：

若通配选择器取消注释，则`<div>`下面的`<span>`元素文字颜色变成灰色。`<p>`下面的`<span>`元素文字颜色也为灰色。因为通配选择器没有加`background-color`以及`font-size`样式，则`<div>`中的这些样式不变。可见继承样式优先级之低。
# 四、像素与颜色
## 1）像素
像素，为屏幕上最小的显示单元。在标准rgb排列的lcd屏幕上，用微距或者广角摄像头，与低ppi的屏幕拉开一定距离，即可看到一排排“红绿蓝”排列的像素。
下列是一些样式写法：
- 例一：用**cm**作单位。
```css
.site1 {
	width: 1cm;
	height: 1cm;
	background-color: pink;
}
```
此计量单位虽然为常用单位，但是在不同屏幕上的尺寸难以界定，所以不用这种单位。

- 例二：用**像素 （px)** 作单位。
```css
.site2 {
	width: 100px;
	height: 100px;
}
```
这样，无论在什么屏幕上，此元素的尺寸都占100\*100（个）像素格，尺寸易于界定。

**注意：由于近年来屏幕分辨率越来越高，所以像素点越来越小，同样尺寸的物件在高分辨率屏幕上太小，所以得在windows设置中调整缩放倍率。若是150%的缩放倍率，那么上述元素的实际尺寸为150\*150像素，比输入值大。**
## 2）颜色
### （1）第一种表示方法 ——— 颜色名称
代码示例：
```css
h1 {
	color: red;
}
```
可以直接用名称表示颜色。
### （2）第二种表示方法 —— rgb&rgba
代码示例：
```css
h1 {
	color: rgb(255,0,0);
}
h2 {
	color: rgb(255,0,0,0.5);
}
h3 {
	color: rgb(255,0,0,50%)
}
```
**每个颜色值范围为0-255，透明度值在0-100%或0-1之间。**

第一种为rgb表示方式，表示的是红色；
第二种和第三种为rgba表示方式，其中**a**表示透明度，可以用小数和百分数表示。
### （3）第三种表示方法 —— hex&hexa
代码示例：
```css
h1 {
	color: #ED7D95;
}
h2 {
	color: #ED7D9588;
}
h3 {
	color: #998;
}
h4 {
	color: #9988;
}
```
**每个颜色范围为00-FF，共256种值，透明度同理**

第一种为hex表示方式，表示的是粉色； 
第二种为hexa表示方式，其中'88'为50%透明度；
第三种和第四种为hex和hexa简写模式，完整版本分别是'#999988'和'#99998888'；
### （4）第四种表示方法 —— hsl&hsla
代码示例：
```css
.site1 {
	color: hsl(0 , 100% , 50%);
}    
.site2 {
	color: hsl(60 , 100% , 50%);
}
.site3 {
	color: hsl(120 , 100% , 50%);
}
.site4 {
	color: hsl(180 , 100% , 50%);
}
.site5 {
	color: hsl(240 , 100% , 50%);
}
.site6 {
	color: hsl(300 , 100% , 50%);
}
.site7 {
	color: hsl(360 , 100% , 50%);
}
```
色环图：
[!色环图.png](https://github.com/inabananami/obsidian-backup/blob/main/text-folder/css%E7%AC%94%E8%AE%B0%E6%95%B4%E5%90%88/%E8%89%B2%E7%8E%AF%E5%9B%BE.png)
跟据图可以确定上述颜色，其中第一个格子为色环图的角度，第二个格子为颜色的亮度，第三个格子为颜色的饱和度。
一般取亮度为100%，取饱和度为50%。
# 五、常用的文本属性
## 1）字体大小
在这里指字体框的大小。chrome中字体大小默认为16px（可以自己调），在旧版本中比16px小的大小均为16px，在firefox可以显示小于16px的文本。
- 代码示例：
```css
body {
	font-size: 30px;
}
```
## 2）字体族
指的是字体种类，可以自行调整想要的字体，并作用于网站的文本。
### （1）单个字体
比如说我们想要将网站的默认字体调为微软雅黑，有下列两种方法：
- 第一种方法（不推荐）：
```css
* {
	font-family: "微软雅黑";
}
```

- 第二种方法（推荐）：
```css
* {
	font-family: "Microsoft YaHei";
}
```
这样我们的网站默认字体为微软雅黑。
### （2）多个字体
如果我们想让网站有多个备选字体，我们可以：
```css
* {
	font-family: "Source Han Mono","Source Han Serif TW VF","Microsoft YaHei";
}
```
这样我们的网站第一字体为思源等宽，第二字体是思源黑体，第三字体为微软雅黑。如果用户电脑无第一字体，则切换为第二字体；若无第二字体，则切换为第三字体。
## 3）字体样式
### （1）字体自带斜体
如果想要字体自带斜体，我们可以：
```css
.game1 {
	font-family: "Microsoft YaHei";
	font-style: italic;
}
```
这样文本就为斜体。
### （2）人为斜体
如果人为地让字体倾斜，我们可以：
```css
.game3 {
	font-style: oblique;
}
.game4 {
	font-style: oblique 45deg;
}
```
通过第二个选择器，我们可以得知，oblique的倾斜角度是可以变换的，可以变为90°，可以为20°。
### （3）消除某些文本的默认样式
如果我们导入`<em>`标签，但是不想要斜体的样式，我们可以：
```css
em {
	font-style: normal;
}
```
这样`<em>`中的文本就不是斜体了。
## 4）字体粗细
字体的粗细可以用以下值来调整：

| 常用值        | 意思      |
| ---------- | ------- |
| `lighter`  | 细       |
| `normal`   | 常规      |
| `bold`     | 加粗      |
| 特定数字如`600` | 加粗、细、常规 |
具体的精细程度看字体的适配如何，一般只有前面三档。
## 5）字体的复合属性
代码示例：
```css
.quote1 {
	font: normal 60px "BIZ UDPゴシック";
}
em {
	font:italic bold 80px "ArenaCondensed Italic";
}
```
我们的字体属性就可以叠加在一个样式栏里，但是要确定后两个一定是字体大小和字体族，不能是其他属性。
# 六、常用的文本属性
## 1）文本颜色
```css
div {
	color: red;
}
```
略。
## 2）文本间隔
代码示例：
```css
.dang {
	color: #880000;
	font-weight: bold;
	font-size: 45px;
	letter-spacing: 50px;
}
.quote1 {
	color: #84C36E;
	/* 英語単語の間隔、日本語には適用しません、字ごとスペースを入力して効果があります */
	word-spacing: 10px;
}
```
`letter-spacing`，是单个字符间的间距。
`word-spacing`，是英语单词之间的间距，触发条件为空格，不适用于中文。
后者硬要应用于中文或者日文，只能采用这个方式：
```html
<div class="quote1">あ な た は 間 違 い な く、エ マ ち ゃ ん 推 し な ん で す ね</div>
```
## 3）文本修饰
代码示例：
- 例一：绿色的上波形线：
```css
.site1 {
	text-decoration: overline wavy green;
}
```
- 例二：灰色的点形下划线：
```css
.site2 {
	text-decoration: underline dotted #777777;
}
```
- 例三：删除线：
```css
.site3 {
	text-decoration: line-through;
}
```
- 例四：啥都没有（消除文本标签的默认样式用）：
```css
.site4 {
	text-decoration: none;
}
```
## 4）文本缩进
代码示例：
```css
div {
	font-size: 60px;
	text-indent: 120px;
}
```
代表文本缩进了两格。
## 5）文本对齐 —— 水平
代码示例：
```css

```
