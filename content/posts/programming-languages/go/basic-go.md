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





## 程序结构
1. 声明
    - 方法
        ```
        s := ""
        var s string
        var s = ""
        var s string = ""
        var a,b,c,s = 1,3.0,true,"string"
        a,b,c,s := 1,3.0,true,"string"(
                简短声明;
                其中至少要声明一个变量;
                只能用于在函数内部局部变量的声明;
                当其中有声明过的变量时执行赋值操作；
                只对同级词法域声明过的变量才和赋值操作等价，
                否则简短声明将重新创建一个新的变量而不是在原变量基础上赋值
                )
        ```
    - 说明
2. hh





## 其他
#### `_`
- blank identifier

#### fmt.Printf
- %d,%x-%o-%b,%f-%g-%e,%t,%c,%s,%q,%v(==fmt.Println),%T,%%

## 关键字
- 语法
    ```
    break,case,chan,const,continue,default,defer,else,fallthrough,for,func,go,goto,if,import,interface,map,package,range,return,select,struct,switch,type,var
    ```
- 内建常量
    ```
    true,false,iota,nil
    ```
- 内建类型
    ```
    int,int8,int16,int32,int64
    uint,uint8,uint16,uint32,uint64,uintptr
    float32,float64,complex128,complex64
    bool,byte,rune,string,error
    ```
- 内建函数
    ```
    make,len,cap,new,append,copy,close,delete
    complex,real,imag
    panic,recover
    ```
