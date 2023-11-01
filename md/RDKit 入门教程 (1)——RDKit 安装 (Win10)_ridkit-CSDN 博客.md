> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [blog.csdn.net](https://blog.csdn.net/zkchen0420/article/details/97784388)

RDKit 简介
--------

RDKit 官网：[https://www.rdkit.org/](https://www.rdkit.org/)  
RDKit 是干啥的：[https://www.rdkit.org/docs/Overview.html#what-is-it](https://www.rdkit.org/docs/Overview.html#what-is-it)  
言简意赅的翻译一下：

1.  RDKit 是一个化学信息学的开源工具包
2.  主要用于操作化学分子（SMILES 和 SMARTS）
3.  可生成适合机器学习的化学分子特征
4.  拥有 Python 3.x API 和 C++ API

Win10 下 RDKit 安装使用（[Python](https://so.csdn.net/so/search?q=Python&spm=1001.2101.3001.7020) API）
------------------------------------------------------------------------------------------------

1.  下载 Anaconda 3.x 版本的 Python：  
    [https://repo.anaconda.com/archive/Anaconda3-2019.07-Windows-x86_64.exe](https://repo.anaconda.com/archive/Anaconda3-2019.07-Windows-x86_64.exe)
2.  安装完成后打开 Anaconda Prompt: 并在命令行输入以下命令：  
    `conda create -c rdkit -n my-rdkit-env rdkit`
3.  等上述命令完成后，接着激活 rdkit 的使用环境，进入 rdkit 模式  
    `conda activate my-rdkit-env`
4.  如果在 rdkit 环境中需要使用常见模块，请另行使用 pip install xxx 安装，如：  
    `pip install numpy`
5.  关闭命令行（Anaconda Prompt）窗口。
6.  利用 Spyder 打开 rdkit 的文本编辑环境，安装好 my-rdkit-env 之后，在菜单栏的 Anaconda3 (64-bit) 文件夹下，应该会出现 Spyder (my-rdkit-env) 图标，点击即进入有 rdkit 环境的 Spyder，否则会进入 base 状态的 Spyder。

如图所示:  
![](https://img-blog.csdnimg.cn/20190730151522928.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3prY2hlbjA0MjA=,size_16,color_FFFFFF,t_70)

参考资料：[https://www.rdkit.org/docs/Install.html](https://www.rdkit.org/docs/Install.html)