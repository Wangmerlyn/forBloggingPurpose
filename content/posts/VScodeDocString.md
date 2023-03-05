+++
title = "VScode Not Showing DocString LaTex"
date = "2023-03-05T22:00:22+08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["KaTeX", "VSCode"]
description = "This is the default description"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++


[https://github.com/microsoft/vscode/issues/168100](https://github.com/microsoft/vscode/issues/168100)

很明显，VSCode的悬浮提示无法渲染头文档里的$LaTeX$公式是因为LSP使用的markdown渲染器是*marked*，并没有支持$\LaTeX$公式的渲染。然而在编辑器里的Markdown Preview使用的是*markdown-it*，启用了*markdown-it-katex*插件。


