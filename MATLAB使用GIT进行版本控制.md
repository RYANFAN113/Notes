# MATLAB使用GIT进行版本控制

建立 project from git
在 remote url 中要填写 http 地址

```url
http://192.168.3.55:8088/RYAN/CTPMAGHUS_Code
```

## 在 Git 中注册二进制文件

<https://ww2.mathworks.cn/help/matlab/matlab_prog/set-up-git-source-control.html>

如果您使用第三方源代码管理工具，则必须将 .mlx、.mat、.fig、.mlapp、.mdl、.slx、.mdlp、.slxp、.sldd 和 .p 等 MATLAB 和 Simulink® 文件扩展名注册为二进制格式。如果不注册这些扩展名，则当您通过更改行尾字符、扩展标记、替换关键字或尝试自动合并来提交文件时，这些工具可能会损坏您的文件。不论您是在 MATLAB 外部使用该源代码管理工具，还是在未先注册文件格式的前提下尝试从 MATLAB 提交文件，都可能发生损坏。
还要检查其他文件扩展名是否已注册为二进制文件，以避免在签入时损坏。检查并注册 MEX 文件、.xlsx、.jpg、.pdf、.docx 等文件。
通过在您的 .gitattributes 文件中注册二进制文件，可以防止 Git 损坏您的文件。