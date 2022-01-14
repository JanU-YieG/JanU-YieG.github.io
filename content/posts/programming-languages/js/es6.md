---
title: "Es6"
subtitle: "es6中值得注意的地方"
date: 2022-01-07T10:00:33+08:00
lastmod: 2022-01-07T10:00:33+08:00
draft: true
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description:
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: ""
featuredImagePreview: ""
weight: 1
resources:
- name: ""
  src: "xx.jpg"
keywords: ["Es6"]
tags: ["Es6"]
categories: ["Js","Es6"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: ""
---
### 变量的解构赋值(Destructuring)
- 等号右边的值需要具有Iterator接口或转为对象后具有改接口(数组，对象，Set,Map等)
#### 数组的解构赋值
- `let [a,b,c=i(),d='z',e='y',[f,g],...h]=[1,2,undefined,null,,[3,4]]`
#### 对象的解构赋值
- 变量必须与属性同名
- 先找到同名属性((匹配)模式)，再赋值给对应变量(赋值)
- 数组本质是特殊的对象
- `let { a, b: B, nothing, de = "default", something: som = "no show", m, m: { line: li }, m: { arr: [x] } } = { a: "a", b: "b", something: "something", m: { line: 1, arr: [2, 3], }, }; `
- `let {log,sin,cos}=Math;`
- `let {0:first,[arr.length-1]:last}=[1,2,3]`
- `({x}={x:1})`
#### 字符串解构赋值
- 字符串被转换成一个类似数组的对象
#### Others
- 只要等号右边不是对象或数组就先将其转为对象
- 函数参数解构赋值
- 不要在模式中放置圆括号
- 赋值语句的非模式部分可以使用圆括号

### 字符串扩展
#### 函数
- `for...of;at;normalizeincludes;startsWith;endsWith;repeat;padStart;padEnd;`
- 反引号```，`${}`:嵌入变量
