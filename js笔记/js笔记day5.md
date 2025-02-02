## 15）对象
### 1. 对象声明语法
```js
	//一つの方法
	let obj = {}
	//二つの方法
	let obj = new Object();
```
例：
```js
	let obj = {
		name: "wang",
		age: 18,
		gender: "female"
	}
	document.write(obj.name);
```
**注意：对象成员最后一个成员，不能加分号（;）**

**一次定义多个对象：**
可以将其包裹进数组里，但是对象头尾用中括号(\[ \])括起来。
```js
	let students = [
		{name: "andy", age: 18, gender: "male", hometown: "US"},
		{name: "eddie", age: 17, gender: "male", hometown: "UK"},
		{name: "mike", age: 19, gender: "feme", hometown: "AR"},
		{name: "morgan", age: 22, gender: "maalle", hometown: "NZ"}
	]
```
### 2.对象的增删改查
例子：
```js
	let obj = {
		name: "上原さん",
		"person-name": "前田さん",
		genter: "male",
		age: 50
	}
```
1. **增：**
```js
	//追加
	obj.hobby = "アイドル";
```
2. **删：**
```js
	//削除
	delete obj.age;
	document.write(obj.age);
```
3. **改：**
```js
	obj.name = "上原さん";
	document.write(obj.name);
```
1. **查：**
第一种方法：
```js
	document.write(obj.info_name);
```
第二种方法：
```js
	document.write(obj["person-name"]);
```
### 3. 对象的方法
基本结构如下：
```js
	sayHi: function() {
		document.write("hi~~");
	}
```
使用方法如下：
```js
	person.sayHi();
```
### 4. 对象的遍历
我们可以用`for(k...in obj) {}`的方法遍历对象。
例子：
```js
	let obj = {
		uname: "andy",
		age: 18,
		sex: "male"
	}
	for(let k in obj) {
		document.write(k);
		document.write(" ");
		//kを大カッコに包まれなければならない
		document.write(obj[k]);
		document.write("<br>");
	}
```
### *5.例 - 输出学生信息表*
需求：请将下列数据打印下来：
```js
	let students = [
		{name: "andy", age: 18, gender: "male", hometown: "US"},
		{name: "eddie", age: 17, gender: "male", hometown: "UK"},
		{name: "mike", age: 19, gender: "feme", hometown: "AR"},
		{name: "morgan", age: 22, gender: "maalle", hometown: "NZ"}
	]
```
输出代码：
```js
	for(let i = 0; i< students.length; i++) {
		for(let k in students[i]) {
			document.write(k);
			document.write(" ");
			document.write(students[i][k]);
			document.write("<br>");
		}
		document.write("<br>");
	}
```
输出表格的详细代码：
```js
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>5.例-学生の情報表を出力</title>
    <style>
        table {
            width: 700px;
            height: 250px;
            border: 2px solid #aaa;
            border-collapse: collapse;
            text-align: center;
            margin: 0 auto;
            margin-top: 20px;
        }
        th {
            border: 1px solid #aaa;
            background-color: #eee;
        }
        td {
            border: 1px solid #aaa;
        }
    </style>
</head>
<body>
    <script>
        let students = [
            {name: "andy", age: 18, gender: "male", hometown: "US"},
            {name: "eddie", age: 17, gender: "male", hometown: "UK"},
            {name: "mike", age: 19, gender: "female", hometown: "AR"},
            {name: "morgan", age: 22, gender: "female", hometown: "NZ"}
        ]
        document.write("<table>");
        document.write(`
                <thead>
                    <th>番号</th>
                    <th>氏名</th>
                    <th>年齢</th>
                    <th>性別</th>
                    <th>故郷</th>
                </thead>
        `);
            document.write(`<tbody>`)
            for(let i = 0; i< students.length; i++) {
                document.write(`<tr>`);
                document.write(`<td>${i + 1}</td>`);
                for(let k in students[i]) {
                    document.write(`<td>${students[i][k]}</td>`);
                }
                document.write(`</tr>`);
            }
            document.write(`</tbody>`);
        document.write("</table>");
    </script>
</body>
</html>
```
效果如下：
![[输出学生信息表.png]](https://github.com/inabananami/obsidian-backup/blob/main/js%E7%AC%94%E8%AE%B0/%E8%BE%93%E5%87%BA%E5%AD%A6%E7%94%9F%E4%BF%A1%E6%81%AF%E8%A1%A8.png)