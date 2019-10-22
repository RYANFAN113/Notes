- [References](#references)
- [基础知识](#%e5%9f%ba%e7%a1%80%e7%9f%a5%e8%af%86)
  - [LATEX控制序列的概念（类似于函数）](#latex%e6%8e%a7%e5%88%b6%e5%ba%8f%e5%88%97%e7%9a%84%e6%a6%82%e5%bf%b5%e7%b1%bb%e4%bc%bc%e4%ba%8e%e5%87%bd%e6%95%b0)
  - [环境概念](#%e7%8e%af%e5%a2%83%e6%a6%82%e5%bf%b5)
  - [LATEX可以排版公式与文字](#latex%e5%8f%af%e4%bb%a5%e6%8e%92%e7%89%88%e5%85%ac%e5%bc%8f%e4%b8%8e%e6%96%87%e5%ad%97)
    - [在数学模式中又分为两种](#%e5%9c%a8%e6%95%b0%e5%ad%a6%e6%a8%a1%e5%bc%8f%e4%b8%ad%e5%8f%88%e5%88%86%e4%b8%ba%e4%b8%a4%e7%a7%8d)
  - [排版](#%e6%8e%92%e7%89%88)
    - [支持中文](#%e6%94%af%e6%8c%81%e4%b8%ad%e6%96%87)
    - [支持空格](#%e6%94%af%e6%8c%81%e7%a9%ba%e6%a0%bc)
    - [设置纸张](#%e8%ae%be%e7%bd%ae%e7%ba%b8%e5%bc%a0)

---

# References
[LaTeX语法简介](https://www.jianshu.com/p/6fc0902f787d)
[LaTeX快速入门：一文浅谈TeX排版语法](https://blog.csdn.net/qingdujun/article/details/80805613)

---

# 基础知识

## LATEX控制序列的概念（类似于函数）

控制序列可以是作为命令：以“\”开头，参数：必须参数{}和可选参数[]。

## 环境概念

以“bengin 环境名”开始，并以“end 环境名”结束。

## LATEX可以排版公式与文字

故分为：数学模式和文本模式。如果你想要在公式中排版普通的文本（直立字体和普通字距），那么你必须要把这些文本放在\textrm{...} 命令中。

### 在数学模式中又分为两种

一种是公式排版在一个段落之中；另一种是公式独立形式排版。前一种，公式直接放在文字之间，公式高度一般受文本高度限制；后一种，公式另起一行，高度可调整。处于段内的数学文本要放在\( 与\) 之间， 与 之间，或者\begin{math} 与\end{math} 之间；处于段外的数学文本放在\[ 与\] 之间， 或者\begin{displaymath} 与\end{displaymath} 之间（为了网页显示，这里用双斜杠表示单斜杠）。

## 排版

```latex
\documentclass[11pt, a4paper]{article}
\usepackage[space]{ctex}
\title{LaTeX快速入门}
\author{ryan}
\date{\today}
\begin{document}
{
    \maketitle
    你\hspace{1cm}好！LaTeX\footnote{LaTeX是一个与Word比肩，甚至更好的工具}。
    %\includegraphics[scale=0.6]{latex.png}
    \part{part标题}
    \section{section标题}
    \subsection{subsection标题}
    \subsubsection{subsubsection标题}
    \paragraph{paragraph标题}
    \subparagraph{subparagraph标题}
    \begin{thebibliography}{99}
    {
        \bibitem{1} 参考文献1
        \bibitem{2} 参考文献2
    }
    \end{thebibliography}
    \begin{appendix}
    {
        \section{附录1}
        \section{附录2}
    }
    \end{appendix}
}
\end{document}
```

### 支持中文

\usepackage{ctex}

### 支持空格

\usepackage[space]

### 设置纸张

\documentclass[11pt,a4paper]

