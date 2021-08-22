# 基本概念
## 程序结构
*PHP程序*由一个或多个源文件组成，称之为*脚本*
<!-- GRAMMAR
script:
  script-section
  script script-section

script-section:
  text? start-tag statement-list? end-tag? text?

start-tag:
  '<?php'
  '<?='

end-tag:
  '?>'

text:
  "arbitrary text not containing any of" start-tag "sequences"
-->
<pre>
<i id="grammar-script">script:</i>
   <i><a href="#grammar-script-section">script-section</a></i>
   <i><a href="#grammar-script">script</a></i>   <i><a href="#grammar-script-section">script-section</a></i>

<i id="grammar-script-section">script-section:</i>
   <i><a href="#grammar-text">text</a></i><sub>opt</sub>   <i><a href="#grammar-start-tag">start-tag</a></i>   <i><a href="11-statements.md#grammar-statement-list">statement-list</a></i><sub>opt</sub>   <i><a href="#grammar-end-tag">end-tag</a></i><sub>opt</sub>   <i><a href="#grammar-text">text</a></i><sub>opt</sub>

<i id="grammar-start-tag">start-tag:</i>
   &lt;?php
   &lt;?=

<i id="grammar-end-tag">end-tag:</i>
   ?&gt;

<i id="grammar-text">text:</i>
   arbitrary text not containing any of   <i><a href="#grammar-start-tag">start-tag</a></i>   sequences
</pre>

脚本中的所有部分都被视为属于一个连续部分，但任何插入的文本都被视为[echo 语句](11-statements.md#the-echo-statement)的字符串文字

脚本可以通过[脚本包含操作符](10-expressions.md#script-inclusion-operators)导入另一个脚本

*语句列表*在[语句部分](11-statements.md#compound-statements)中定义

脚本的顶层简称顶层

如果 <?= 用作开始*标记*,则引擎将继续运行，就像*语句列表*以[echo](11-statements.md#the-echo-statement)语句开始一样

## 程序启动
程序以某种未指定方式指定的[脚本](#程序结构)从开始处执行。此脚本被称为*启动脚本*

程序一旦执行，就可以访问某些[环境信息](07-variables.md#predefined-variables)，这些信息包括:
- 通过预定义变量$argc的*命令行参数*数
- 通过预定义变量$argv让一系列一个或多个命令行作为字符串
- 定义一系列*环境变量*名称

可用的环境变量的确切集合是由实现定义的，并且可以根据引擎的类型和构建以及执行引擎的环境而有所不同

当[顶层](#程序结构)是脚步的主要入口时，它作为全局变量存在。当通过 [include/require](10-expressions.md#script-inclusion-operators)调用顶层时,它将继承调用者的变量[范围](#范围)。因此，当孤立地查看一个脚本的顶层时，不可能静态地判断它是具有全局变量作用域还是某些局部变量作用域。它取决于脚本的调用方式，也取决于程序被调用时的运行时的状态

程序可以接受多个启动脚本，在这种情况下，它们按照程序定义的顺序执行，并共享全局环境

## 程序终止
程序可以通过以下方式正常终止:
- 执行到达启动脚本的末尾。对于多个[启动脚本](#启动脚本)，执行将到达最后一个脚本的末尾
- 执行最后一个启动脚本顶层的[return语句](11-statements.md#the-return-statement)
- 显式调用内部[exit](10-expressions.md#exitdie)