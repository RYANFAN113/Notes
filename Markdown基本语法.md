[TOC]

---

# References

[Markdown基本语法](https://www.jianshu.com/p/191d1e21f7ed)

[在 VSCode 下用 Markdown Preview Enhanced 愉快地写文档](http://get.ftqq.com/9126.get)

[Markdown Preview Enhanced](https://shd101wyy.github.io/markdown-preview-enhanced/#/zh-cn/)

[Markdown All in One 书写Markdown利器](https://segmentfault.com/a/1190000017461306?utm_source=tag-newest)

[流程图参考](https://www.iminho.me/wiki/docs/mindoc/flowchart.md)

[使用 Typora 画图(类图、流程图、时序图)](https://zhuanlan.zhihu.com/p/172635547)

[Typora 使用小技巧](https://mp.weixin.qq.com/s?__biz=MzIyNDQzMDAwNg==&mid=2247486183&idx=1&sn=abbf162c8094a3d1dc52ea5be6eab352&chksm=e80e583edf79d128b3da9c4d68de6a23b2f7662efef8d65064483e79477f24bea52fbbcf945a&token=1113980067&lang=zh_CN#rd)

---

# Markdown 基本语法

## 字体

示例：

```markdown
**这是加粗的文字**  
*这是倾斜的文字*  
***这是斜体加粗的文字***  
~~这是加删除线的文字~~  
==标记==   #MPE

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
>>
>>>>>>>>>>这是引用的内容3

---

## 缩写 ^MPE^

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

## 注脚 ^MPE^

示例：

```markdown
Content [^1]
[^1]: Hi! This is a footnot
```

效果：

Content [^1]
[^1]: Hi! This is a footnot

---

## 上下标 ^MPE^

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
<a href="超链接地址" target="_blank">超链接名<a>
```

示例:  

```markdown
<a href="<https://www.jianshu.com/u/1f5ac0cf6a8b>" target="_blank">简书<a>  
```

效果：

<a href="https://www.jianshu.com/u/1f5ac0cf6a8b" target="_blank">简书</a>

---

## 代码块

语法：

使用一对反引号即可包含一个行内代码使用一对三个反引号可以包括多行代码，另外多行Tab也可以用于代码段

示例：

```markdown
`print("hello");`
```

效果:

`print("hello");`

示例：

```markdown  
​```C++ {.line-numbers highlight=3-4}  
include<iostream>
int main()
{  
std::cout<<"hello world!""<<std::endl;  
return 0;  
}  
​```
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
| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |
```

效果：

| First Header                | Second Header                |
| --------------------------- | ---------------------------- |
| Content from cell 1         | Content from cell 2          |
| Content in the first column | Content in the second column |

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

---

## 流程图

主要的语法为**name=>type:describe**,其中type主要有以下几种：

1. 开始和结束：start、end
2. 输入输出：inputoutput
3. 操作：operation
4. 条件：condition
5. 子程序：subroutine

\- 代表实线 ， 主动发送消息，比如 request请求
\> 代表实心箭头 ， 同步消息，比如 AJAX 的同步请求
-- 代表虚线，表示返回消息，spring Controller return
\>\> 代表非实心箭头 ，异步消息，比如AJAX请求

示例：

```markdown
​```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
​```
```

效果：

```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```

### 使用 mermaid

```markdown
​```mermaid
graph 流程图的方向
流程图的内容
​```
```

流程图方向有下面几个值

- TB 从上到下
- BT 从下到上
- RL 从右到左
- LR 从左到右
- TD 同TB

基本图形

- id + [文字描述]矩形
- id + (文字描述)圆角矩形
- id + >文字描述]不对称的矩形
- id + {文字描述}菱形
- id + ((文字描述))圆形

节点之间的连接

- A --> B A带箭头指向B
- A --- B A不带箭头指向B
- A -.- B A用虚线指向B
- A -.-> B A用带箭头的虚线指向B
- A ==> B A用加粗的箭头指向B
- A -- 描述 --- B A不带箭头指向B并在中间加上文字描述
- A -- 描述 --> B A带箭头指向B并在中间加上文字描述
- A -. 描述 .-> B A用带箭头的虚线指向B并在中间加上文字描述
- A == 描述 ==> B A用加粗的箭头指向B并在中间加上文字描述

示例：

```markdown
​```mermaid
graph LR
    start[开始] --> input[输入A,B,C]
    input --> conditionA{A是否大于B}
    conditionA -- YES --> conditionC{A是否大于C}
    conditionA -- NO --> conditionB{B是否大于C}
    conditionC -- YES --> printA[输出A]
    conditionC -- NO --> printC[输出C]
    conditionB -- YES --> printB[输出B]
    conditionB -- NO --> printC[输出C]
    printA --> stop[结束]
    printC --> stop
    printB --> stop
​```
```

效果：

```mermaid
graph LR
    start[开始] --> input[输入A,B,C]
    input --> conditionA{A是否大于B}
    conditionA -- YES --> conditionC{A是否大于C}
    conditionA -- NO --> conditionB{B是否大于C}
    conditionC -- YES --> printA[输出A]
    conditionC -- NO --> printC[输出C]
    conditionB -- YES --> printB[输出B]
    conditionB -- NO --> printC[输出C]
    printA --> stop[结束]
    printC --> stop
    printB --> stop
```

子流程图

```markdown
subgraph title
    graph definition
end
```

示例：

```markdown
​```mermaid
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
​```
```

效果：

```mermaid
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```

自定义样式

```markdown
style id 具体样式
```

示例：

```markdown
​```mermaid
graph LR
    id1(Start)-->id2(Stop)
    style id1 fill:#f9f,stroke:#333,stroke-width:4px,fill-opacity:0.5
    style id2 fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray: 10,5
​```
```

效果：

```mermaid
graph LR
    id1(Start)-->id2(Stop)
    style id1 fill:#f9f,stroke:#333,stroke-width:4px,fill-opacity:0.5
    style id2 fill:#ccf,stroke:#f66,stroke-width:2px,stroke-dasharray: 10,5
```

