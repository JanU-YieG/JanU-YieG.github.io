---
title: "Basic Go"
subtitle: ""
date: 2021-08-05T09:30:16+08:00
lastmod: 2021-08-05T09:30:16+08:00
draft: true
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description: Go 语言基础语法记录
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: "https://cdn5.maocdn.cn/img/2021/08/05/image002.jpg"
featuredImagePreview: "https://cdn5.maocdn.cn/img/2021/08/05/image002.jpg"
weight: 1
resources:
- name: ""
  src: "xx.jpg"
keywords: ["Golang", "Hunt", "programming-languages"]
tags: ["Golang", "Hunt", "programming-languages"]
categories: ["Hunt", "Golang", "programming-languages"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: "go 语言基础语法"
---

<!--more-->

## 控制语句

#### if...else


#### for
-
    ```
    for initialization; condition; post {
        //zero or more statements
    }
    ```
-
    ```
    for condition {
        //...
    }
    ```
-
    ```
    for {
        //...
        break  //or return
    }
    ```
-
    ```
    for _, arg := range os.Args[1:] {
        //...
    }
    ```





## 数据类型









## 其他
#### _
- blank identifier
#### 声明变量
-
    ```
    s := ""
    var s string
    var s = ""
    var s string = ""
    ```
#### fmt.Printf
- %d,%x-%o-%b,%f-%g-%e,%t,%c,%s,%q,%v(==fmt.Println),%T,%%
