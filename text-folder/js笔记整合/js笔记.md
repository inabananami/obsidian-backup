# js简介
在浏览器里的编程语言。
### 示例代码：
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
