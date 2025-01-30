# 1、触发弹性盒子
给父元素添加display属性；取值flex
### 1）父元素触发弹性盒子之后，子元素默认横向显示
父元素触发弹性盒子之后，子元素会横向显示，类似于浮动，但不是浮动，与浮动没有关系
不会影响孙子辈分的元素
### 2）触发弹性盒子之后，会改变子元素的元素类型，会让子元素变成块级元素
### 3) 触发弹性盒子之后，如果只有一个子元素，给子元素添加margin: auto的时候，子元素会位于水平垂直居中位置显示。
# 2、修改主轴方向
如以下代码所示：
```css
	.bigbox {
		width: 500px;
		height: 500px;
		border: 10px solid gray;
		margin: 100px auto;
		display: flex;
		/* 横に順方向でディスプレイ （よく使う）*/
		flex-direction: row;
		/* 横にレバースでディスプレイ */
		/* flex-direction: row-reverse; */
		/* 縦に順方向でディスプレイ （よく使う）*/
		/* flex-direction: column; */
		/* 縦にレバースでディスプレイ */
		/* flex-direction: column-reverse; */
	}
```
## 3、主轴对齐方式
### 1）justify-content
