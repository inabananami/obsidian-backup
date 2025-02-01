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
### 2.对象的增删改查
例子：
```js
	let obj = {
		name: "佐藤さん",
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
4. **查：**
```js
	document.write(obj.info_name);
```
