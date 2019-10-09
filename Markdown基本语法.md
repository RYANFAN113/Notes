# 目录

- [目录](#%e7%9b%ae%e5%bd%95)
- [References](#references)
- [Markdown 基本语法](#markdown-%e5%9f%ba%e6%9c%ac%e8%af%ad%e6%b3%95)
  - [字体](#%e5%ad%97%e4%bd%93)
  - [引用](#%e5%bc%95%e7%94%a8)
  - [缩写 MEP](#%e7%bc%a9%e5%86%99-mep)
  - [注脚 MEP](#%e6%b3%a8%e8%84%9a-mep)
  - [上下标 MEP](#%e4%b8%8a%e4%b8%8b%e6%a0%87-mep)
  - [分割线](#%e5%88%86%e5%89%b2%e7%ba%bf)
  - [图片](#%e5%9b%be%e7%89%87)
  - [超链接](#%e8%b6%85%e9%93%be%e6%8e%a5)
  - [代码块](#%e4%bb%a3%e7%a0%81%e5%9d%97)
  - [任务列表](#%e4%bb%bb%e5%8a%a1%e5%88%97%e8%a1%a8)
  - [表格](#%e8%a1%a8%e6%a0%bc)
  - [列表](#%e5%88%97%e8%a1%a8)
    - [无序列表](#%e6%97%a0%e5%ba%8f%e5%88%97%e8%a1%a8)
    - [有序列表](#%e6%9c%89%e5%ba%8f%e5%88%97%e8%a1%a8)
  - [标题](#%e6%a0%87%e9%a2%98)
- [这是一级标题](#%e8%bf%99%e6%98%af%e4%b8%80%e7%ba%a7%e6%a0%87%e9%a2%98)
  - [这是二级标题](#%e8%bf%99%e6%98%af%e4%ba%8c%e7%ba%a7%e6%a0%87%e9%a2%98)
    - [这是三级标题](#%e8%bf%99%e6%98%af%e4%b8%89%e7%ba%a7%e6%a0%87%e9%a2%98)
      - [这是四级标题](#%e8%bf%99%e6%98%af%e5%9b%9b%e7%ba%a7%e6%a0%87%e9%a2%98)
        - [这是五级标题](#%e8%bf%99%e6%98%af%e4%ba%94%e7%ba%a7%e6%a0%87%e9%a2%98)
          - [这是六级标题](#%e8%bf%99%e6%98%af%e5%85%ad%e7%ba%a7%e6%a0%87%e9%a2%98)

---

# References

[Markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed)

[在 VSCode 下用 Markdown Preview Enhanced 愉快地写文档](http://get.ftqq.com/9126.get)

[Markdown Preview Enhanced](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/)

[Markdown All in One 书写Markdown利器](https://segmentfault.com/a/1190000017461306?utm_source=tag-newest)

---

# Markdown 基本语法

## 字体

示例：

```markdown
**这是加粗的文字**  
*这是倾斜的文字*  
***这是斜体加粗的文字***  
~~这是加删除线的文字~~  
==标记==  #MEP

<font face="黑体">我是黑体字\</font>  
<font face="微软雅黑">我是微软雅黑\</font>  
<font face="STCAIYUN">我是华文彩云\</font>  
<font color=red>我是红色\</font>  
<font color=#008000>我是绿色\</font>  
<font color=Blue>我是蓝色\</font>  
<font size=5>我是尺寸\</font>  
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5\</font>  
```

效果：

**这是加粗的文字**  
*这是倾斜的文字*  
***这是斜体加粗的文字***  
~~这是加删除线的文字~~  
==标记==

<font face="黑体">我是黑体字</font>  
<font face="微软雅黑">我是微软雅黑</font>  
<font face="STCAIYUN">我是华文彩云</font>  
<font color=red>我是红色</font>  
<font color=#008000>我是绿色</font>  
<font color=Blue>我是蓝色</font>  
<font size=5>我是尺寸</font>  
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>  

---

## 引用

在引用的文字前加>即可。引用也可以嵌套，如加两个>>三个>>>
n个...  
貌似可以一直加下去，但没神马卵用

示例：

```markdown
>这是引用的内容
>>这是引用的内容
>>>>>>>>>>这是引用的内容
```

效果：

>这是引用的内容1
>>这是引用的内容2
>>>>>>>>>>这是引用的内容3

---

## 缩写 MEP

示例：

```markdown
*[HTML]: Hyper Text Markup Language  
*[W3C]:  World Wide Web Consortium  
The HTML specification is maintained by the W3C.
```

效果：

*[HTML]: Hyper Text Markup Language  
*[W3C]:  World Wide Web Consortium  
The HTML specification is maintained by the W3C.

---

## 注脚 MEP

示例：

```markdown
Content [^1]
[^1]: Hi! This is a footnot
```

效果：

Content [^1]
[^1]: Hi! This is a footnot

---

## 上下标 MEP

示例：

```markdown
30^th^  
H~2~O
```

效果：

30^th^
H~2~O

---

## 分割线

三个或者三个以上的 - 或者 * 都可以。

示例：

```markdown
---
```

效果：

---

```markdown
----
```

效果：

----

```markdown
***
```

效果：

***

```markdown
*****
```

效果：

*****

---

## 图片

语法：

```markdown
![图片alt](图片地址 ''图片title'')

# 图片alt就是显示在图片下面的文字，相当于对图片内容的解释。  
# 图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加
```

示例：

```markdown
![blockchain](<https://upload-images.jianshu.io/upload_images/6860761-fd2f51090a890873.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/550/format/webp> "区块链")
```

效果：

![blockchain](https://upload-images.jianshu.io/upload_images/6860761-fd2f51090a890873.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/550/format/webp "区块链")  

上传本地图片直接点击导航栏的图片标志，选择图片即可

---

## 超链接

语法：

```markdown
[超链接名](超链接地址 "超链接title")  
# title可加可不加
```

示例：

```markdown
[百度](http://baidu.com "baidu")  
```

效果：

[百度](http://baidu.com "baidu")

注：Markdown本身语法不支持链接在新页面中打开，如果想要在新页面中打开的话可以用html语言的a标签代替。

```markdown
<a href="超链接地址" target="_blank">超链接名</a>
```

示例:  

```markdown
<a href="<https://www.jianshu.com/u/1f5ac0cf6a8b>" target="_blank">简书\</a>  
```

效果：

<a href="https://www.jianshu.com/u/1f5ac0cf6a8b" target="_blank">简书</a>

---

## 代码块

语法：

使用一对反引号即可包含一个行内代码使用一对三个反引号可以包括多行代码，另外多行Tab也可以用于代码段

示例：

```c++
`print("hello");`
```

效果:

`print("hello");`

示例：

```markdown  
#```C++ {.line-numbers highlight=3-4}  
include<iostream>
int main()
{  
std::cout<<"hello world!""<<std::endl;  
return 0;  
}  
#```
# 把井号删除
```

效果：

```C++ {.line-numbers highlight=3-4}
include<iostream>
int main()  
{  
std::cout<<"hello world!""<<std::endl;  
return 0;  
}  
```  

---

## 任务列表

示例：

```markdown
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags<del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
```

效果：

- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item

---

## 表格

示例：

```markdown
First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column
```

效果：

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

---

## 列表

### 无序列表

示例：

```markdown
- Item 1
- Item 2
  - Item 2a
  - Item 2b
```

效果：

- Item 1
- Item 2
  - Item 2a
  - Item 2b

### 有序列表

示例：

```markdown
1. Item 1
2. Item 2
3. Item 3
   1. Item 3a
   2. Item 3b
```

效果：

1. Item 1
2. Item 2
3. Item 3
   1. Item 3a
   2. Item 3b

---

## 标题

在想要设置为标题的文字前面加#来表示
一个#是一级标题，二个#是二级标题，以此类推。支持六级标题。  

注：标准语法一般在#后跟个空格再写文字，貌似简书不加空格也行。  

示例：

```markdown
# 这是一级标题
## 这是二级标题
### 这是三级标题
##### 这是五级标题
###### 这是六级标题
```

效果：

# 这是一级标题

## 这是二级标题

### 这是三级标题

#### 这是四级标题

##### 这是五级标题

###### 这是六级标题
