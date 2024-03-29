---
title: "Markdown常用语法"
subtitle: ""
date: 2021-07-14T11:12:06+08:00
lastmod: 2021-07-14T11:12:06+08:00
draft: false
author: "Borer"
authorLink: "https://github.com/JanU-YieG"
description: markdown常用语法
hiddenFromHomePage: false
hiddenFromSearch: false
featuredImage: "https://s3.jpg.cm/2021/08/05/IAPdmX.jpg"
featuredImagePreview: "https://s3.jpg.cm/2021/08/05/IAPdmX.jpg"
weight: 1
resources:
- name: ""
  src: "xx.jpg"
keywords: ["markdown"]
tags: ["markdown"]
categories: ["markdown"]
lightgallery: true
toc:
  enable: true
math:
  enable: false
showTags: true
license: ""
summary: "一个简单的常用的markdown教程，解决日常使用问题，不要求全面"
---

<!--more-->
## 斜体
- 语法：`*斜体*`
- 显示：*斜体*
- 说明：`*`或者`_`都可以，最好使用`*`

## 换行
- 语法：空白行

## 标题
- 语法：`#` `##` `###` `####` `#####` `######`
- 说明：生成`<h1>`---`<h6>`的标签

## 列表
- 语法：`-`，`*`，`+`;而有序列表数字加上英文句点`1.`
- 显示：
    - 第一
    - 第二
    * first
    * second
    + diyi
    + dier
    1. i
    2. ii

## 引用
- 语法：`>`
- 显示：
    > 这是引用
    >   > 这是引用中的引用

## 代码块
- 语法：\`\`\` 代码 \`\`\`
- 显示：
    ```
    int i=5;
    ```

## 链接
- 语法：`[链接名称](链接跳转url)`
- 显示：[borer的个人网站](https://janu-yieg.github.io/)

## 图片
- 语法：`![图片](图片url)`
- 显示：![图片](https://img.maocdn.cn/img/2021/06/07/728908.jpg)

## 分隔线
- 语法：三个以上的`*`或者`-`来建立分隔线
- 显示：
    > 上文
    > ****************
    > 下文

## 表格
- 语法：`|`和`-`和来绘制表格，`:`可控制左/右对齐或居中
- 显示：

| Title | Description |
| :------ | :--------------------------------: |
| Version | 0.0.1 |
| Editor | [Borer](https://janu-yieg.github.io) |

## 转义
- 语法：使用\\来转义

## 自动链接
- 语法：`<自动链接>`
- 显示：<https://google.com>

## 删除线
- 语法：`~~删除~~`
- 显示：~~删除~~
