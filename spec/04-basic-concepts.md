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