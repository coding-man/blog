---
title: "go语言三个点的用法"
date: 2019-09-29T14:04:36+08:00
lastmod: 2019-09-29T14:04:36+08:00
draft: false
keywords: []
description: ""
tags: ["golang"]
categories: ["golang"]
author: ""

# You can also close(false) or open(true) something for this content.
# P.S. comment can only be closed
comment: false
toc: true
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

在Golang中，三个点一共会用在四个地方.

## 变长的函数参数
如果最后一个函数参数的类型的是...T，那么在调用这个函数的时候，我们可以在参数列表的最后使用若干个类型为T的参数。这里，...T在函数内部的类型实际是[]T.

```go 
func Sum(nums ...int) int {
	res := 0
	for _, n := range nums {
		res += n
	}
	return res
}

Sum(1,2,3) 
```

## 调用拥有变长参数列表的函数
上面调用Sum函数时，是将变长参数分开写的。如果我们有一个slice，那么我们调用时不必将slice拆开再调用，直接在slice后跟...即可： 
```go 
primes := []int{2, 3, 5, 7} 
fmt.Println(Sum(primes...))
```

## 标识数组元素个数
这里，...意味着数组的元素个数： 
```go 
stooges := [...]string{"Moe", "Larry", "Curly"} 
```

## Go命令行中的通配符
描述包文件的通配符。 在这个例子中，会单元测试当前目录和所有子目录的所有包： 
```bash
go test ./...
```



## 参考资料
* [3 dots in 4 places](https://yourbasic.org/golang/three-dots-ellipsis/)
