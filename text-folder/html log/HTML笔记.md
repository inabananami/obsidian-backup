# 一、HTML是什么？
`超文本标记语言`，通过标签控制文本类型，图片导入，是现代网页开发的骨架。与CSS和JS结合，构成现代前端基础开发的基石。
# 二、HTML初体验
## 1、 示例：
以下是部分html代码：
```
<marquee>

    <input>

</marquee>

账号：<input>

密码：<input>
```
其中，`<marquee>`已经被弃用，`<input>`是标签。
## 2、 属性
`<input>`是一个标签，html标签的属性是这么加的：`<input type="password">`,输入时就会隐藏输入内容，因为这是密码输入框。
# 三、HTML基础
## 1、html标准结构
==二.1==中代码之所以是部分html代码，是因为它不具备html的基本结构。之所以能运行，是因为浏览器帮我们补齐了。
一个html标准结构如下：
```
<!DOCTYPE html>
<html lang="zh-CN">
	<head>
		<meta charset="UTF-8">
		<title>我的网站</title>
	</head>
	<body>
		<input type="text">
		<input type="password">
	</body>
</html>
```
### 1) 文档声明
`<!DOCTYPE html>`是html5的文档声明，其比html先前的版本更加简洁，且向下兼容。
### 2）语言设置
`<html lang="zh-CN">`中`lang="zh-CN"`意思为“网站的默认语言是简体中文”。若想切换为其他默认语言，例如日语，则为`<html lang="ja">`。
### 3）字符编码方式
`<meta charset="UTF-8">`为网站字符编码方式，现在一般为UTF-8。`<meta>`中也可以添加更多属性。
### 4）标签页标题
`<titile>我的网站</title>`在标签页上显示网页标题。
### 5）骨架
`<head>`中除了以上基础部分，也会放css样式以及其他元数据。
`<body>`则为网页主体部分，网页开发代码在这里出现。
## 2、html排版标签
### 1）文本标签
下面为示例代码：
```
<!DOCTYPE html>

<html lang="zh-CN">

    <head>

        <meta charset="UTF-8">

        <title>HTML排版标签</title>

    </head>

    <body>
	    <!-- <body>中最重要的，不能有第二个h1 -->
	
	        <h1>把个人信息“安全堤”筑牢</h1>
	
	        <h2>2022-06-21 07:34    •1347条评论</h2>
	
	        <h3>
	
	                  置身移动互联时代，
	
	                 人们在享受智能设备带来便利的同时，
	
	                 也在一些场景中面临个人信息泄露风险。随着时间推移，
	
	                 这样的风险日益呈现出新的表现形式。
	
	        </h3>
	
	        <h3>
	
	            一些APP声称看
	
	            视频、玩游戏甚至走路都能赚钱，但用户想提现却难上
	
	            加难，还容易泄露个人信息；新型不法软件图标透明、
	
	            没有名称，在手机屏幕上十分隐蔽，不仅不停推送广告
	
	            ，还会收集并转卖用户隐私信息；个人信息安全和隐私
	
	            保护话题引发关注，正说明其涉及群众切身利益，问题
	
	            不容小视。
	
	        </h3>
	
	        <h4>著作权</h4>                  
	
	        <h5>2015-06-18</h5>         <!-- 使用很少 -->
	
	        <h6>moegirl</h6>
	
	  
	  
	  
	
	        <h1>把个人信息“安全堤”筑牢</h1>
	
	        <div>
	
	        <p>2022-06-21 07:34    •1347条评论</p>
	
	        <p>
	
	                置身移动互联时代，
	
	                 人们在享受智能设备带来便利的同时，
	
	                 也在一些场景中面临个人信息泄露风险。随着时间推移，
	
	                 这样的风险日益呈现出新的表现形式。
	
	        </p>
	
	        <p>
	
	            一些APP声称看
	
	            视频、玩游戏甚至走路都能赚钱，但用户想提现却难上
	
	            加难，还容易泄露个人信息；新型不法软件图标透明、
	
	            没有名称，在手机屏幕上十分隐蔽，不仅不停推送广告
	
	            ，还会收集并转卖用户隐私信息；个人信息安全和隐私
	
	            保护话题引发关注，正说明其涉及群众切身利益，问题
	
	            不容小视。
	
	        </p>
	
	        </div>

    </body>

</html>
```
#### （1）标题标签
`<h1><h2><h3>…<h6>`为标题标签，其中`<h4>~<h6>`不常用，**`<h1>`只能出现一个**， 其中加粗样式为默认样式，后期可以通过css来调整。
#### （2）文字块标签
`<div>、<span>` 文字块标签，两者都无特别的意思，前者常用于css样式编辑，后者常用于行内，选中文本，并用css添加样式。
#### （3）p标签
`<p>`标签为段落标签，用于区分不同的段落。
### 2) 行内元素与块元素

```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

        <meta charset="UTF-8">

        <title>块级元素与行内元素</title>

</head>

<body>

        <!-- 块级元素，特点：独占一行-->

        <!-- <marquee>尚硅谷</marquee>

        <h1>尚硅谷</h1>

        <p>尚硅谷</p>                    

        <div>尚硅谷</div> -->

        <!-- 行内元素，特点：不独占一行-->

        <!-- <input type="text">

        <span>ss</span>

        <span>ss</span> -->

  

        <!-- 规则1：块级元素中能写：行内元素，块级元素（几乎都能写） -->

        <!-- <div>

            <span>sssss</span>

            <input type="text">

            <div>ssssss</div>

         </div> -->    

         <!-- 规则2：行内元素中能写：行内元素，但不能写：块级元素 -->

          <!-- <span>

            <span>sssss</span>

            <input type="text">

            <span>ss</span>

            <div>sss<div>   xx

          </span>

          <span>ssss</span> -->

  

        <!-- 特殊规则：h1-h6不能互相嵌套 -->

         <!-- <h1>

                sgg

                <h2>sgg2</h2>

         </h1> -->

         <!-- 特殊规则：p标签中不能写块元素 -->

          <p>

            <h1>sgg</h1>

          </p>

          <ul>sgg</ul>

</body>

</html>
```
如实例代码所示，块级元素内可以出现块级元素与行内元素，但是行内元素中不得出现块级元素，`<h1>`~`<h6>`不能相互嵌套，`<p>`标签中不能出现块级元素。
### 3）HTML主要的文本标签
下列为实例代码：
```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

    <meta charset="UTF-8">

    <title>html常用的文本标签</title>

    <style>

            span{

                color:#735e02;

            }

    </style>

</head>

<body>

    <p>

            不是哥们，不是哥们，不是哥们，<strong>不是哥们</strong>，<em>不是哥们</em>。

    </p>

    <p>

            <strong>以前</strong>是<strong>以前</strong>，

            <strong>现在</strong>是<strong>现在</strong>

    </p>

    <p>

        人有三大欲望：<span>食欲、性欲、睡眠欲</span>。

    </p>

    <p>

        人間は三大欲求だ：<span>食欲、性欲、睡眠欲</span>。

    </p>
</body>

</html>
```

#### （1） `<strong>`标签
`<strong>`标签为标记内容的重要性。虽然默认样式是加粗，但是我们可以通过css来改变其样式。
#### （2）`<em>`标签
`<em>`标签也为强调文本，但比起`<strong>`标签，更加富有感情。
## 3、图片标签
以下是实例代码：
```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

        <meta charset="UTF-8">

        <title>html图片标签</title>

</head>

<body>

        <img width="500px" src="ayumu1.jpg" alt="ayumu">
        <img src="data:image/jpeg;base64,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b25zAAAAFwAAAABDcHRuYm9vbAAAAAAAQ2xicmJvb2wAAAAAAFJnc01ib29sAAAAAABDcm5DYm9vbAAAAAAAQ250Q2Jvb2wAAAAAAExibHNib29sAAAAAABOZ3R2Ym9vbAAAAAAARW1sRGJvb2wAAAAAAEludHJib29sAAAAAABCY2tnT2JqYwAAAAEAAAAAAABSR0JDAAAAAwAAAABSZCAgZG91YkBv4AAAAAAAAAAAAEdybiBkb3ViQG/gAAAAAAAAAAAAQmwgIGRvdWJAb+AAAAAAAAAAAABCcmRUVW50RiNSbHQAAAAAAAAAAAAAAABCbGQgVW50RiNSbHQAAAAAAAAAAAAAAABSc2x0VW50RiNQeGxAJAAAAAAAAAAAAAp2ZWN0b3JEYXRhYm9vbAEAAAAAUGdQc2VudW0AAAAAUGdQcwAAAABQZ1BDAAAAAExlZnRVbnRGI1JsdAAAAAAAAAAAAAAAAFRvcCBVbnRGI1JsdAAAAAAAAAAAAAAAAFNjbCBVbnRGI1ByY0BZAAAAAAAAAAAAEGNyb3BXaGVuUHJpbnRpbmdib29sAAAAAA5jcm9wUmVjdEJvdHRvbWxvbmcAAAAAAAAADGNyb3BSZWN0TGVmdGxvbmcAAAAAAAAADWNyb3BSZWN0UmlnaHRsb25nAAAAAAAAAAtjcm9wUmVjdFRvcGxvbmcAAAAAADhCSU0D7QAAAAAAEAAKAAAAAQABAAoAAAABAAE4QklNBCYAAAAAAA4AAAAAAAAAAAAAP4AAADhCSU0EDQAAAAAABAAAAFo4QklNBBkAAAAAAAQAAAAeOEJJTQPzAAAAAAAJAAAAAAAAAAABADhCSU0nEAAAAAAACgABAAAAAAAAAAE4QklNA/UAAAAAAEgAL2ZmAAEAbGZmAAYAAAAAAAEAL2ZmAAEAoZmaAAYAAAAAAAEAMgAAAAEAWgAAAAYAAAAAAAEANQAAAAEALQAAAAYAAAAAAAE4QklNA/gAAAAAAHAAAP////////////////////////////8D6AAAAAD/////////////////////////////A+gAAAAA/////////////////////////////wPoAAAAAP////////////////////////////8D6AAAOEJJTQQAAAAAAAACAAI4QklNBAIAAAAAAAYAAAAAAAA4QklNBDAAAAAAAAMBAQEAOEJJTQQtAAAAAAAGAAEAAAAEOEJJTQQIAAAAAAAQAAAAAQAAAkAAAAJAAAAAADhCSU0EHgAAAAAABAAAAAA4QklNBBoAAAAAAz8AAAAGAAAAAAAAAAAAAAAyAAAAMgAAAAVnKmgHmJgALQAyAAAAAQAAAAAAAAAAAAAAAAAAAAAAAAABAAAAAAAAAAAAAAAyAAAAMgAAAAAAAAAAAAAAAAAAAAABAAAAAAAAAAAAAAAAAAAAAAAAABAAAAABAAAAAAAAbnVsbAAAAAIAAAAGYm91bmRzT2JqYwAAAAEAAAAAAABSY3QxAAAABAAAAABUb3AgbG9uZwAAAAAAAAAATGVmdGxvbmcAAAAAAAAAAEJ0b21sb25nAAAAMgAAAABSZ2h0bG9uZwAAADIAAAAGc2xpY2VzVmxMcwAAAAFPYmpjAAAAAQAAAAAABXNsaWNlAAAAEgAAAAdzbGljZUlEbG9uZwAAAAAAAAAHZ3JvdXBJRGxvbmcAAAAAAAAABm9yaWdpbmVudW0AAAAMRVNsaWNlT3JpZ2luAAAADWF1dG9HZW5lcmF0ZWQAAAAAVHlwZWVudW0AAAAKRVNsaWNlVHlwZQAAAABJbWcgAAAABmJvdW5kc09iamMAAAABAAAAAAAAUmN0MQAAAAQAAAAAVG9wIGxvbmcAAAAAAAAAAExlZnRsb25nAAAAAAAAAABCdG9tbG9uZwAAADIAAAAAUmdodGxvbmcAAAAyAAAAA3VybFRFWFQAAAABAAAAAAAAbnVsbFRFWFQAAAABAAAAAAAATXNnZVRFWFQAAAABAAAAAAAGYWx0VGFnVEVYVAAAAAEAAAAAAA5jZWxsVGV4dElzSFRNTGJvb2wBAAAACGNlbGxUZXh0VEVYVAAAAAEAAAAAAAlob3J6QWxpZ25lbnVtAAAAD0VTbGljZUhvcnpBbGlnbgAAAAdkZWZhdWx0AAAACXZlcnRBbGlnbmVudW0AAAAPRVNsaWNlVmVydEFsaWduAAAAB2RlZmF1bHQAAAALYmdDb2xvclR5cGVlbnVtAAAAEUVTbGljZUJHQ29sb3JUeXBlAAAAAE5vbmUAAAAJdG9wT3V0c2V0bG9uZwAAAAAAAAAKbGVmdE91dHNldGxvbmcAAAAAAAAADGJvdHRvbU91dHNldGxvbmcAAAAAAAAAC3JpZ2h0T3V0c2V0bG9uZwAAAAAAOEJJTQQoAAAAAAAMAAAAAj/wAAAAAAAAOEJJTQQUAAAAAAAEAAAABDhCSU0EDAAAAAAEqwAAAAEAAAAyAAAAMgAAAJgAAB2wAAAEjwAYAAH/2P/tAAxBZG9iZV9DTQAB/+4ADkFkb2JlAGSAAAAAAf/bAIQADAgICAkIDAkJDBELCgsRFQ8MDA8VGBMTFRMTGBEMDAwMDAwRDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAENCwsNDg0QDg4QFA4ODhQUDg4ODhQRDAwMDAwREQwMDAwMDBEMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwM/8AAEQgAMgAyAwEiAAIRAQMRAf/dAAQABP/EAT8AAAEFAQEBAQEBAAAAAAAAAAMAAQIEBQYHCAkKCwEAAQUBAQEBAQEAAAAAAAAAAQACAwQFBgcICQoLEAABBAEDAgQCBQcGCAUDDDMBAAIRAwQhEjEFQVFhEyJxgTIGFJGhsUIjJBVSwWIzNHKC0UMHJZJT8OHxY3M1FqKygyZEk1RkRcKjdDYX0lXiZfKzhMPTdePzRieUpIW0lcTU5PSltcXV5fVWZnaGlqa2xtbm9jdHV2d3h5ent8fX5/cRAAICAQIEBAMEBQYHBwYFNQEAAhEDITESBEFRYXEiEwUygZEUobFCI8FS0fAzJGLhcoKSQ1MVY3M08SUGFqKygwcmNcLSRJNUoxdkRVU2dGXi8rOEw9N14/NGlKSFtJXE1OT0pbXF1eX1VmZ2hpamtsbW5vYnN0dXZ3eHl6e3x//aAAwDAQACEQMRAD8A9VWP1L6wU4zjTjAW2jQuP0Af+/pfWDqTsaoY1Ji20S4jkM4/6a5hNJb/ACnKCY9zJ8v6Me/iW7d1nqVpk3uaPBnt/wCpUGdV6jWZbkWH+s7d/wBXuVVJNst/2sdVwRryDvYP1lduDM1oIP8AhWDUf1mf+RW+x7LGB7CHMcJa4aghcEtj6v8AUXU3jFsM02mGz+a88f56cJd2nzXJx4TPGKI1Meh8np0kkk5zX//Q6PrNxt6leTw12wf2fahOx6WEMstLLIBI2y0SN0Fwdu/8DUuq1mvqOS097HO/zjv/AO/Jn24lrzdZvDzq6sAQT/xk+1v/AFtRu5DSEOG+HhHy/wDNYDGsN76SQ01zvceAG8u0Uba6WAbHl5/q7RHkSf8AvqkL92Q65znVlxLt1fIJ8NWqd+UH0mrfZaSQ7faeIn6DZft5/fSXXKx9L/awdj7bq69384GHdHG8Nd/0dyKGOo+11TrSQQ7j3MeK5/6Sbfi2elZa5wdW0NfWB9LbxtfP5zU2TaXXZT2FpZc4knvBd6g2pIuRoH62Ook9R+0fIf0X7Skq/wBhs8P+0Hof2kk/VzODE//R7T6y4Ltzc1glpAZb5H8x3/fVgrvXsZYxzHgOY4Q5p4IK5rqX1fvpcbMQG2rnYPpN/wDJpsh1dLk+ajwjHM0R8pPUdnHSTlpaSHAgjkHlMmt9SvdGwXZmY0EfoqyH2HtA4b/bSwej5mY4ENNdXex4gR/JH566nCwqMKgU0jTlzjyT+85EBqc1zUYRMYm5nTT9BsJJJJ7kv//S9VSXyqkkp+nOo9v6L/6Eqvhfzg/oH/WPpL5rSQ6tmH80/VSS+VUkWs/VSS+VUklP/9kAOEJJTQQhAAAAAABXAAAAAQEAAAAPAEEAZABvAGIAZQAgAFAAaABvAHQAbwBzAGgAbwBwAAAAFABBAGQAbwBiAGUAIABQAGgAbwB0AG8AcwBoAG8AcAAgADIAMAAyADAAAAABADhCSU0EBgAAAAAABwAIAAAAAQEA/+EN+2h0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8APD94cGFja2V0IGJlZ2luPSLvu78iIGlkPSJXNU0wTXBDZWhpSHpyZVN6TlRjemtjOWQiPz4gPHg6eG1wbWV0YSB4bWxuczp4PSJhZG9iZTpuczptZXRhLyIgeDp4bXB0az0iQWRvYmUgWE1QIENvcmUgNS42LWMxNDggNzkuMTY0MDM2LCAyMDE5LzA4LzEzLTAxOjA2OjU3ICAgICAgICAiPiA8cmRmOlJERiB4bWxuczpyZGY9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkvMDIvMjItcmRmLXN5bnRheC1ucyMiPiA8cmRmOkRlc2NyaXB0aW9uIHJkZjphYm91dD0iIiB4bWxuczp4bXA9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC8iIHhtbG5zOnhtcE1NPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvbW0vIiB4bWxuczpzdEV2dD0iaHR0cDovL25zLmFkb2JlLmNvbS94YXAvMS4wL3NUeXBlL1Jlc291cmNlRXZlbnQjIiB4bWxuczpkYz0iaHR0cDovL3B1cmwub3JnL2RjL2VsZW1lbnRzLzEuMS8iIHhtbG5zOnBob3Rvc2hvcD0iaHR0cDovL25zLmFkb2JlLmNvbS9waG90b3Nob3AvMS4wLyIgeG1wOkNyZWF0b3JUb29sPSJBZG9iZSBQaG90b3Nob3AgMjEuMCAoV2luZG93cykiIHhtcDpDcmVhdGVEYXRlPSIyMDI0LTEwLTIyVDE5OjAxOjM0KzA4OjAwIiB4bXA6TWV0YWRhdGFEYXRlPSIyMDI0LTEwLTIyVDE5OjAxOjM0KzA4OjAwIiB4bXA6TW9kaWZ5RGF0ZT0iMjAyNC0xMC0yMlQxOTowMTozNCswODowMCIgeG1wTU06SW5zdGFuY2VJRD0ieG1wLmlpZDozYzQ1NmViMi02NjBlLTMzNDQtYTdjZS1kZDkxY2YxMzE3NDQiIHhtcE1NOkRvY3VtZW50SUQ9ImFkb2JlOmRvY2lkOnBob3Rvc2hvcDplNzc0MWM4Zi0xM2I1LTJhNDUtOTY1My1lMjBlMDk0ZThlZTQiIHhtcE1NOk9yaWdpbmFsRG9jdW1lbnRJRD0ieG1wLmRpZDo5ODM3NWU3ZS00MTFhLWI5NDEtODQ3My0zOTQ0NWFkMGYzYTAiIGRjOmZvcm1hdD0iaW1hZ2UvanBlZyIgcGhvdG9zaG9wOkNvbG9yTW9kZT0iMyIgcGhvdG9zaG9wOklDQ1Byb2ZpbGU9InNSR0IgSUVDNjE5NjYtMi4xIj4gPHhtcE1NOkhpc3Rvcnk+IDxyZGY6U2VxPiA8cmRmOmxpIHN0RXZ0OmFjdGlvbj0iY3JlYXRlZCIgc3RFdnQ6aW5zdGFuY2VJRD0ieG1wLmlpZDo5ODM3NWU3ZS00MTFhLWI5NDEtODQ3My0zOTQ0NWFkMGYzYTAiIHN0RXZ0OndoZW49IjIwMjQtMTAtMjJUMTk6MDE6MzQrMDg6MDAiIHN0RXZ0OnNvZnR3YXJlQWdlbnQ9IkFkb2JlIFBob3Rvc2hvcCAyMS4wIChXaW5kb3dzKSIvPiA8cmRmOmxpIHN0RXZ0OmFjdGlvbj0ic2F2ZWQiIHN0RXZ0Omluc3RhbmNlSUQ9InhtcC5paWQ6M2M0NTZlYjItNjYwZS0zMzQ0LWE3Y2UtZGQ5MWNmMTMxNzQ0IiBzdEV2dDp3aGVuPSIyMDI0LTEwLTIyVDE5OjAxOjM0KzA4OjAwIiBzdEV2dDpzb2Z0d2FyZUFnZW50PSJBZG9iZSBQaG90b3Nob3AgMjEuMCAoV2luZG93cykiIHN0RXZ0OmNoYW5nZWQ9Ii8iLz4gPC9yZGY6U2VxPiA8L3htcE1NOkhpc3Rvcnk+IDwvcmRmOkRlc2NyaXB0aW9uPiA8L3JkZjpSREY+IDwveDp4bXBtZXRhPiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIDw/eHBhY2tldCBlbmQ9InciPz7/4gxYSUNDX1BST0ZJTEUAAQEAAAxITGlubwIQAABtbnRyUkdCIFhZWiAHzgACAAkABgAxAABhY3NwTVNGVAAAAABJRUMgc1JHQgAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLUhQICAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAABFjcHJ0AAABUAAAADNkZXNjAAABhAAAAGx3dHB0AAAB8AAAABRia3B0AAACBAAAABRyWFlaAAACGAAAABRnWFlaAAACLAAAABRiWFlaAAACQAAAABRkbW5kAAACVAAAAHBkbWRkAAACxAAAAIh2dWVkAAADTAAAAIZ2aWV3AAAD1AAAACRsdW1pAAAD+AAAABRtZWFzAAAEDAAAACR0ZWNoAAAEMAAAAAxyVFJDAAAEPAAACAxnVFJDAAAEPAAACAxiVFJDAAAEPAAACAx0ZXh0AAAAAENvcHlyaWdodCAoYykgMTk5OCBIZXdsZXR0LVBhY2thcmQgQ29tcGFueQAAZGVzYwAAAAAAAAASc1JHQiBJRUM2MTk2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">
        <img src="https://img.moegirl.org.cn/common/thumb/f/f8/%C5%8Cnishi_Aguri_23.jpg/250px-%C5%8Cnishi_Aguri_23.jpg" alt="agupon">
</body>

</html>
```
其中`<img>`为图片标签，`width`为宽度，与`height`配合使用，只用一个标签时，图片等比例放大缩小。
`alt`为图片信息，供爬虫读取。
`src`为导入图片，其中导入方式有：
1、**相对路径**，如`./resourse/ayumu3.jpg`。
2、**绝对路径**，如`C:\Windows\System32\MTFserver.dll`
3、**base64**，如第二个img标签导入的内容。
4、**链接**，如第三个img标签所示。
## 4、超链接
### 1）介绍
超链接的标签：`<a>`，是一个行内元素。
一般的形式为`<a href=" "></a>`，用于跳转指定的网站。

还可以用`target`属性指定跳转网站打开方式，如`target="_self"`是在**当前页面**打开网站，`target="_blank"`是在**新的页面**打开网站。

也可以在一个网页中跳转到不同的页面，如 `<a href="./9.html排版标签"> 快开始学html！</a>`是跳转到我的另一个html实例。
### 2）跳转文件
以下是实例：
```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

    <meta charset="UTF-8">

    <title>超链接_跳转文件</title>

</head>

<body>

    <!-- 下列文件chrome可以全部打开，firefox无法打开mp4 -->

    <a href="./resourse/ayumu3.jpg" target="_blank">看ayumu</a>

    <br></br>

    <a id="gbc1" href="./resourse/gbc1.mp4" target="_blank">gbc，启动！</a>

    <br></br>

    <a href="./resourse/红宝书大全集 (许小明 Reika) (z-lib.org).pdf">背日语词</a>

  

    <!-- 浏览器不可以直接打开的文件 -->

     <a href="./resourse/汉仪正圆.rar">嵌字基础字体（ </a>

  

     <!-- 浏览器可以打开，但要强制触发下载 -->

     <a href="./resourse/ayumu3.jpg" download="ayumu1" target="_self">看ayumu</a>

</body>

</html>
```
如代码中所示，我们可以利用`<a>`标签打开图片，视频，pdf等浏览器可以直接打开的文件，对于不能直接打开的文件，则会直接下载。

如果要强制触发下载，则只需要加入`download`属性，浏览器会自动以属性后的名字命名并下载。
### 3）锚点
代码示例：
```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

    <meta charset="UTF-8">

    <title>超链接跳转锚点</title>

</head>

<body>

    <a href="#ninamakemoney">看nina make money</a>

    <a href="#gyudon">看nina吃牛丼</a>

  

    <div>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

    </div>

    <p id="gyudon">nina吃牛丼</p>   <!--推荐这种方式写锚点-->

    <img width="600px" src="./resourse/nina 牛丼.png" alt="nina 牛丼">

  

    <div>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

        <br></br>

    </div>

    <p>nina make money</p>

    <img width="600px" src="./resourse/nina sox.png" alt="nina sox">

    <a name="ninamakemoney"></a>  <!-- 这种锚点不建议使用 -->

  

    <p>nina还债中...</p>

    <a href="#">回到川崎站</a>

    <a href="">刷新页面</a>

    <!-- 还可跳转到其他网页的指定位置 -->

    <a href="./17.超链接_跳转文件.html#gbc1" target="_blank">跳转原片</a>

</body>

</html>
```
 第一种锚点为在文本标签中加入`id`属性，如上述代码中的`<p id="gyudon">`。若想跳转至此位置，则可以用如下代码实现：`<a href="#gyudon">`。**推荐使用这个方式写锚点**。

第二种锚点为单独创建一个`<a>`标签，并使用`name`属性标注。这种锚点会造成尺寸方面的问题，**故不推荐使用。**
### 4）唤起指定应用
代码示例：
```
<!DOCTYPE html>

<html lang="zh-CN">

    <head>

        <meta charset="UTF-8">

        <title>超链接唤起指定应用</title>

    </head>

    <body>

        <a href="tel:10086">电话联系10086</a>

        <a href="mailto:123@gmal.com">邮件联系</a>

        <a href="sms:10086">短信联系10086</a>

    </body>

</html>
```
其中电话联系是`tel`属性，邮件联系是`mailto`，短信联系是`sms`。
## 5、列表
### 1）基础
代码示例：
```
<!DOCTYPE html>

<html lang="zh-CN">

    <head>

        <meta charset="UTF-8">

        <title>列表</title>

    </head>

    <body>

        <h2>挽回momoka分几步？</h2>

        <ol>

            <li>找到momoka</li>

            <li>共进晚餐</li>

            <li>竖中指</li>

            <li>一起竖中指</li>

        </ol>

  

        <h2>我想去的几个城市</h2>

        <ul>

            <li>福冈</li>

            <li>沼津</li>

            <li>札幌</li>

        </ul>

  

        <h2>如何更好地学习</h2>

        <dl>

            <dt>重复练习</dt>

            <dd>只有敲出来地代码才是自己的</dd>

            <dt>不怕错误</dt>

        </dl>

    </body>

</html>
```
其中`<ol>`标签接`<li>`标签为数字序号列表，`<ul>`标签接`<li>`标签为点列表，`<dl>`接`<dt>`是顶格的列表，`<dd>`则为缩进一格的列表项。都可以使用css更换样式，比如删除数字，删除点。、
### 2）注意事项
代码示例：
```
<!DOCTYPE html>

<html lang="zh-CN">

<head>

    <meta charset="UTF-8">

    <title>列表_注意事项</title>

</head>

<body>

    <h2>挽回momoka分几步？</h2>

    <ol>

        <li>找到momoka</li>

        <li>共进晚餐</li>

        <li>竖中指</li>

        <li>一起竖中指</li>

        <!-- 若要在列表内写超链接，则必须在列表内包裹一个超链接 -->

        <li>

            <a href="https://www.baidu.com">去百度</a>

        </li>

    </ol>

  

    <h2>我想去的几个城市</h2>

    <ul>

        <li>福冈</li>

        <li>

            <span>沼津</span>

            <ul>

                <li>

                    <span>交通</span>

                    <ul>

                        <li>公交车班次少，建议自驾</li>

                    </ul>

                </li>

                <li>滨江酒店</li>

                <li>海水浴场</li>

                <li>水族馆</li>

            </ul>

        </li>

        <li>札幌</li>

    </ul>

  

    <h2>如何更好地学习</h2>

    <dl>

        <dt>重复练习</dt>

        <dd>只有敲出来地代码才是自己的</dd>

        <dd>多敲效果更好</dd>

        <dt>不怕错误</dt>

    </dl>

</body>

</html>
```
#### （1）嵌入超链接
如第一个列表所示，我们可以在列表中导入超链接。不过要用`<li>`标签将其包裹起来。
#### （2）列表内嵌套
如第二个列表所示，我们可以在列表中嵌套一个或多个列表。但不建议超过三层。上一层列表的第一个成员用`<span>`包裹，然后在`<li>`标签块内写下一层列表。
## 6、表格
### 1）基础
表格由标题、头部、主体、脚注构成。表尾脚注可以视情况省略。
#### （1）表格标题和头部
代码示例：
```
        <!-- 表格标题 -->

        <caption>乐队信息</caption>

        <!-- 表格头部 -->

        <thead>

            <tr>

                <th>姓名</th>

                <th>性别</th>

                <th>年龄</th>

            </tr>

        </thead>
```
`<caption>`为**表格标题标签**，`<thead>`为**表格头部标签**。`<tr>`标签代表表格的一行，头部成员由`<th>`包裹，成员序号为多少，代表它在第几列。
#### （2）表格主体
代码示例：
```
<tbody>

            <tr>

                <td>井芹仁菜</td>

                <td>女</td>

                <td>17</td>

            </tr>

            <tr>

                <td>河原木桃香</td>

                <td>女</td>

                <td>20</td>

            </tr>

            <tr>

                <td>RUPA</td>

                <td>女</td>

                <td>22</td>

            </tr>

            <tr>

                <td>安和すばる</td>

                <td>女</td>

                <td>17</td>

            </tr>

            <tr>

                <td>海老塚智</td>

                <td>女</td>

                <td>16</td>

            </tr>

        </tbody>
```
 `<tbody>`为**表格主体标签**，仍用`<tr>`确定表格行数，但是主体元素用`<td>`包裹，同样地，成员序号为多少，代表它在第几列。
#### （3）表格脚注
代码示例：
```
        <tfoot>

            <td></td>

            <td></td>

            <td>共计5人</td>

        </tfoot>
```
`<tfoot>`为表格主体标签，脚注元素用`<td>`包裹，同样的，成员序号为多少，代表它在第几列。
### 2）常用属性
#### （1）表格尺寸控制属性
html中，主要的表格尺寸控制属性有`border`、`width`、`height`、`cellspacing`。

`border`为0则没有边框，数值>1时，能控制外部边框像素，不能控制内部边框像素。

`width`和`height`分别控制表格的宽度和高度，如`<table width="990px" height="300px">`意思是表格宽度为990像素，高度为300px。不但`<table>`中可以设置，`<thead>`、`<tbody>`、`<tfoot>`中也可以使用。
**注意：宽度类属性不是平均分配的，而是根据内容分配。**

`cellspacing`是单元格间的距离，为0只是合并单元格。
#### （2）表格对齐控制属性
html中，对齐控制属性为`align`和`valign`。分别为水平方向对齐方式，垂直方向对齐方式。

其中`align`对齐方式分别为：`left、center、right`，对应左对齐，居中，右对齐。
`valign`对齐方式分别为：`top、center、bottom`，对应向上对齐，居中，向下对齐。
#### （3）表格的跨行与跨列
如图的表格：
![[html_表格的跨行与跨列.png]]
其中的跨行跨列效果是怎么来的呢？
首先我们拆解这个表格，具体如下：

| 项目  | 上课  | 1-3 | 1-4 | 1-5 | 1-6 | 活动与休息 | 1-8 |
| --- | --- | --- | --- | --- | --- | ----- | --- |
| 星期  | 星期一 | 星期二 | 星期三 | 星期四 | 星期五 | 星期六   | 星期日 |
| 上午  | 3-2 | 3-3 | 3-4 | 3-5 | 3-6 | 3-7   | 休息  |
| 4-1 | 4-2 | 4-3 | 4-4 | 4-5 | 4-6 | 4-7   | 4-8 |
| 5-1 | 5-2 | 5-3 | 5-4 | 5-5 | 5-6 | 5-7   | 5-8 |
| 6-1 | 6-2 | 6-3 | 6-4 | 6-5 | 6-6 | 6-7   | 6-8 |
| 上午  | 7-2 | 7-3 | 7-4 | 7-5 | 7-6 | 7-7   | 休息  |
| 8-1 | 8-2 | 8-3 | 8-4 | 8-5 | 8-6 | 8-7   | 8-8 |
这下我们清楚：
**上课**要独占后面四格，**活动与休息**要独占后面一格，**上午**占下面三格，**下午**占下面两格，两个**休息**同**上午**和**下午**。
故**上课**和**活动与休息**的代码则要引入`colspan`，即为跨列标签，代码分别为：`<th colspan="5">`和
`<th colspan="2">`
**上午**、**下午**和**休息**则要引入`rowspan`，即为跨行标签，代码分别为：`<th rowspan="4">`和`<th rowspan="2">`
## 7、表单 
### 1）基本结构
代码示例：
```
    <form action="https://www.baidu.com/s">

        <input type="text" name="wd">

        <button>百度一下</button>

    </form>
```
其中`<form>`标签是跳转到指定网站搜索指定内容，与`<input>`标签中的`name`属性配合，可以将用户输入的内容提交到对应网站并直接搜索内容。
### 2）文本框和密码框
代码示例：
```
    <form action="https://search.jd.com/search">

        <!-- 控件1：value，表示input框内的默认信息 -->

        <!-- 控件2：maxlength，表示input框内最多可输入的字符-->

        账户：<input type="text" name="account">

        密码：<input type="password" name="pwd">

        <button>确认</button>
        </form>
```
 如注释所示。
### 3）单选框与多选框
代码示例：
```
        性别：

        <input type="radio" name="gender" value="male">男

        <input type="radio" name="gender" value="female" checked>女

        <br>

        爱好：

        <!-- type为设置表单属性 -->

        <!-- name为选项种类 -->

        <!-- value为选项名称 -->

        <input type="checkbox" name="hobby" value="watchlive" checked>看live

        <input type="checkbox" name="hobby" value="watchseiyuu">看女声优

        <input type="checkbox" name="hobby" value="watchsyoujyoband"checked>看少女乐队
```
其中，`radio`属性为设置单选框，`value` 为选项名称，`name`为选项种类。其中，`checked`能预选一个或多个选项。
### 4）隐藏域
代码示例：`<input type="hidden" name="from" value="bilibili">`
如果要使用隐藏域，则`type`属性栏中填入`hidden`即可，目的是防爬虫。
### 5）提交与重置
确认的第一种写法：`<button>确认</button>`
第二种写法：`<input type="submit" value="确认">`

重置的第一种写法：`<input type="reset" value="重置">`
第二种写法：`<button type="reset">重置</button>`
### 6）普通按钮
第一种写法：`<button>检测账户是否被注册</button>`
第二种写法：`<input type="button" value="检测账户是否被注册">`
### 7）文本域与下拉框
#### （1）文本域
文本域的标签是`<textarea>`用于输入比input框更多的文本。其中`cols`和`rows`可以设置初始列数和行数。
#### （2）下拉框
代码示例：
```
        籍贯：

        <select name="place">

            <option value="冀" >河北省</option>

            <option value="晋">山西省</option>

            <option value="鲁">山东省</option>

            <option value="粤" selected>广东省</option>

        </select>
```
`<select>`为下拉框，`<option>`为选项标签，其中`selected`可以默认选中一个选项。
### 8）禁用表单控件
`disabled`可以禁用某个表单控件。
### 9）label标签
示例代码：
```
        <input id="nan" type="radio" name="gender" value="male">

        <label for="nan">男</label>
```
`<label>`标签可以创建锚点，使得我们点击文本的时候可以直接获取到表单控件的焦点。
基本结构如上代码。
