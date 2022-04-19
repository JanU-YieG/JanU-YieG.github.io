---
title: "Javascript"
subtitle: "js注意之处"
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
keywords: ["JavaScript","Js"]
tags: ["JavaScript"]
categories: ["JavaScript"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: ""
---

## 对象
- `this`指代当前的对象。`this`没有使用点运算符则函数内的`this`指向全局对象。
- "名称-值"对===对象；（散列表）；js中的一切（除核心类型，core object）都是对象；
- 对象属性可以通过链式方法访问；
- 所有键名都是字符串，加不加引号都可。不是字符串的自动转为字符串
- eval('{foo:123}') eval('({foo:123})')

## 变量
- js中语句块是没有作用域的，只有函数有作用域，所以var声明的变量作用域是整个函数；而ES6开始将不同，let和const关键字允许创建块作用域的变量；

## 控制语句
- `for...in`:以任意顺序遍历一个对象的除`Symbol`以外的可枚举属性，包括继承的可枚举属性。
- `for...of`:在可迭代对象（Array,Map,Set,String,TypedArray,arguments对象等等）上创建一个迭代循环，调用自定义迭代钩子，并为每个属性的值执行语句。

## 函数
- 内部函数：允许在一个函数内部定义函数---->他们可以访问父函数作用域中的变量。

## 闭包
- 作用域对象组成了一个名为作用域链的（调用）链。
- 一个闭包就是一个函数与其被创建时所带有的作用域作用域对象的组合。
