---     
layout: post     
title:  "sublime_text使用总结"     
date:   2014-12-27 02:43:00     
categories: 其他     
---     

想要快速用好vim，那么删掉sublime可能是最迅速的方法了。王道培训时，大张旗鼓抛弃vim转投sublime，到现在其实也就没几个月的时间。但是sublime我已经用得挺熟悉，码字效率已经比较高了，毕竟也是认真花了一些精力去钻研的。所以感觉就此抛弃可惜了，还是把经验存在这里吧。（原本是存在电脑上的，但是由于spotligh）     

---     

####快捷键     
_       
#####Basic:     
`command + /` ---   注释       
`command + [`  or  `command + ]`   --- 向左、向右缩进       
`command + shift + p` --- 操作列表       
`command + d` --- 选择当前光标单词，多按记下多选     
**New!** `command + k` 再 `command + d` ---- 在多光标选择中跳过一项      
**New!** `command + shift + v`   ---   适配缩进的黏贴     


#####Extended:      
`command + j` ---  合并两行，副作用：把光标移到最右！（跳出括号）       
`command + p` --- Go to anywhere，加`@`可搜函数名，`#` 搜索单词       
`command + r` --- 快速搜索函授，相当于上面自动加了@       

`control + k` ---  删除至行尾     

**New!** `option + 方向`  ---  按单词移动     

`control + m` ---- 在一对匹配的括号间移动       
`control + shift + m` ----- 选中括号内所有的内容     

**New!** `alt + command + f` ---  替换     



#####Important:     
`control + command + 上下` ---  交换整行，移动     

`command + k 再按 u/l` ---  转换大小写     

`alt + command + v` ---  粘贴板记录。**!!!重要!!!**     

`command + shift + t` －－ 打开上次关闭的文件     

**new!!** `command + shift + l`  ---  在每行的末尾产生光标     

**niubi!** `command + alt + v`   ---   打开剪切板历史记录的黏贴    
**niubi!** `control + shift + w`  ---  给选区包裹一对html标签    
**niubi!** `option + shift + ~`  ---  给选区包裹一对反引号(``)     



####插件     
* **`SublimeAStyleFormatter`** 自动整理格式化代码     

	快捷键：`control + alt + f`     
	     
* **`ConvertToUTF8`**  中文支持     
	     
* **`JsFormat`**，格式化js代码     

* **`ctags` 函数定义处跳转        
	`brew install ctags` 需要安装ctags     
	`ctags -R -f .tags`在当前目录建立tag文件     

* `emmet` 前端插件   http://docs.emmet.io  （左下角有cheat sheet）     
    - `command + shift + k`  ---  选择父标签内容     
    - `control + d`  ----   选择整个标签区域     




###snippet scope     
```     
Here is a list of scopes to use in Sublime Text 2 snippets -      
 
ActionScript: source.actionscript.2     
AppleScript: source.applescript     
ASP: source.asp     
Batch FIle: source.dosbatch     
C#: source.cs     
C++: source.c++     
Clojure: source.clojure     
CoffeeScript: source.coffee     
CSS: source.css     
D: source.d     
Diff: source.diff     
Erlang: source.erlang     
Go: source.go     
GraphViz: source.dot     
Groovy: source.groovy     
Haskell: source.haskell     
HTML: text.html(.basic)     
JSP: text.html.jsp     
Java: source.java     
Java Properties: source.java-props     
Java Doc: text.html.javadoc     
JSON: source.json     
Javascript: source.js     
BibTex: source.bibtex     
Latex Log: text.log.latex     
Latex Memoir: text.tex.latex.memoir     
Latex: text.tex.latex     
LESS: source.css.less     
TeX: text.tex     
Lisp: source.lisp     
Lua: source.lua     
MakeFile: source.makefile     
Markdown: text.html.markdown     
Multi Markdown: text.html.markdown.multimarkdown     
Matlab: source.matlab     
Objective-C: source.objc     
Objective-C++: source.objc++     
OCaml campl4: source.camlp4.ocaml     
OCaml: source.ocaml     
OCamllex: source.ocamllex     
Perl: source.perl     
PHP: source.php     
Regular Expression(python): source.regexp.python     
Python: source.python     
R Console: source.r-console     
R: source.r     
Ruby on Rails: source.ruby.rails     
Ruby HAML: text.haml     
SQL(Ruby): source.sql.ruby     
Regular Expression: source.regexp     
RestructuredText: text.restructuredtext     
Ruby: source.ruby     
SASS: source.sass     
Scala: source.scala     
Shell Script: source.shell     
SQL: source.sql     
Stylus: source.stylus     
TCL: source.tcl     
HTML(TCL): text.html.tcl     
Plain text: text.plain     
Textile: text.html.textile     
XML: text.xml     
XSL: text.xml.xsl     
YAML: source.yaml     
```     




