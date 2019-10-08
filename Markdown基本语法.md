# Markdown 基本语法

## References

[Markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed)

## 标题

在想要设置为标题的文字前面加#来表示
一个#是一级标题，二个#是二级标题，以此类推。支持六级标题。  

注：标准语法一般在#后跟个空格再写文字，貌似简书不加空格也行。  

示例：

\# 这是一级标题

# 这是一级标题

\## 这是二级标题

## 这是二级标题

\### 这是三级标题

### 这是三级标题

\#### 这是四级标题

#### 这是四级标题

\##### 这是五级标题

##### 这是五级标题

\###### 这是六级标题

###### 这是六级标题

## 字体

加粗  
要加粗的文字左右分别用两个*号包起来  
斜体  
要倾斜的文字左右分别用一个*号包起来  
斜体加粗  
要倾斜和加粗的文字左右分别用三个*号包起来  
删除线  
要加删除线的文字左右分别用两个~~号包起来  
\<font face="黑体">我是黑体字</font>  
\<font face="微软雅黑">我是微软雅黑</font>  
\<font face="STCAIYUN">我是华文彩云</font>  
\<font color=red>我是红色</font>  
\<font color=#008000>我是绿色</font>  
\<font color=Blue>我是蓝色</font>  
\<font size=5>我是尺寸</font>  
\<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>  

示例：

**这是加粗的文字**  
*这是倾斜的文字*  
***这是斜体加粗的文字***  
~~这是加删除线的文字~~  

<font face="黑体">我是黑体字</font>  
<font face="微软雅黑">我是微软雅黑</font>  
<font face="STCAIYUN">我是华文彩云</font>  
<font color=red>我是红色</font>  
<font color=#008000>我是绿色</font>  
<font color=Blue>我是蓝色</font>  
<font size=5>我是尺寸</font>  
<font face="黑体" color=green size=5>我是黑体，绿色，尺寸为5</font>  

## 引用

在引用的文字前加>即可。引用也可以嵌套，如加两个>>三个>>>
n个...  
貌似可以一直加下去，但没神马卵用

示例：

>这是引用的内容
>>这是引用的内容
>>>>>>>>>>这是引用的内容

## 分割线

三个或者三个以上的 - 或者 * 都可以。

示例：

\---

---

\----

----

\***

***

\*****

*****

## 图片

语法：

![图片alt](图片地址 ''图片title'')

图片alt就是显示在图片下面的文字，相当于对图片内容的解释。  
图片title是图片的标题，当鼠标移到图片上时显示的内容。title可加可不加

示例：
!\[blockchain](`https://upload-images.jianshu.io/upload_images/6860761-fd2f51090a890873.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/550/format/webp~` "区块链")

![blockchain](https://upload-images.jianshu.io/upload_images/6860761-fd2f51090a890873.jpg?imageMogr2/auto-orient/strip|imageView2/2/w/550/format/webp "区块链")  

上传本地图片直接点击导航栏的图片标志，选择图片即可

## 超链接

语法：

\[超链接名](超链接地址 "超链接title")  
title可加可不加

示例：

\[百度](`http://baidu.com`)  
[百度](http://baidu.com)

注：Markdown本身语法不支持链接在新页面中打开，如果想要在新页面中打开的话可以用html语言的a标签代替。

\<a href="超链接地址" target="_blank">超链接名</a>

示例:  
\<a href="`https://www.jianshu.com/u/1f5ac0cf6a8b`" target="_blank">简书\</a>  
<a href="https://www.jianshu.com/u/1f5ac0cf6a8b" target="_blank">简书</a>

## 代码块

语法：

使用一对反引号即可包含一个行内代码使用一对三个反引号可以包括多行代码，另外多行Tab也可以用于代码段

'code'

'''  
code blocks  
'''

效果：

'print("hello");'  

'''  
\#include　\<iostream>  
int main()  
{  
std::cout<<"hello world!""<<std::endl;  
return 0;  
}  
'''  
