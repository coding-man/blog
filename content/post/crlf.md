---
title: "CRLF"
date: 2019-10-15T13:59:09+08:00
lastmod: 2019-10-15T13:59:09+08:00
draft: false
keywords: []
description: ""
tags: []
categories: []
author: ""

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: false
autoCollapseToc: false
postMetaInFooter: false
hiddenFromHomePage: false
# You can also define another contentCopyright. e.g. contentCopyright: "This is another copyright."
contentCopyright: false
reward: false
mathjax: false
mathjaxEnableSingleDollar: false
mathjaxEnableAutoNumber: false

# You unlisted posts you might want not want the header or footer to show
hideHeaderAndFooter: false

# You can enable or disable out-of-date content warning for individual post.
# Comment this out to use the global config.
#enableOutdatedInfoWarning: false

flowchartDiagrams:
  enable: false
  options: ""

sequenceDiagrams: 
  enable: false
  options: ""

---

> 回车符（CR）和换行符（LF）是文本文件用于标记换行的控制字符（control characters）或字节码（bytecode）。

* CR = Carriage Return，回车符号（\r，十六进制 ascii 码为0x0D，十进制 ascii 码为13），用于将光标移动到行首，并不前进至下一行。
* LF = Line Feed，换行符号（ \n, 十六进制 ascii 码为 0x0A，十进制 ascii 码为10）。

紧邻的 CR 和 LF（组成 CRLF，\r\n，或十六进制 0x0D0A）将光标移动到下一行行首。（Windows 操作系统默认的文本换行符为 CRLF；Linux 以及 macOS 系统默认使用 LF，早期的 mac os 系统使用 CR 换行。）
