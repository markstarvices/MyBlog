---
title: Java的执行原理
date: 2022-04-09 20:26:07
type: "Java"
layout: "Java"
categories: Java基础 # 分类
mathjax: false # 开启数学公式
toc: true # 是否有目录
top: false # 文章是否置顶，置顶1以上
hide: false # 隐藏文章
cover: false # 该文章是否需要加入到首页轮播封面中
img: /medias/featureimages/25.jpg # 文章特征图
author: MarkStarVices # 作者
summary: Java的执行原理之内存变化 # 摘要内容
tags: # 标签
- Java
---


### java方法执行过程中的内存变化

#### 代码

```java
public class JavaTest{
	public static void main(String[] args) {
		System.out.println("main begin");
		int x =100;
		m1(x);
		System.out.println("main end");
	}
	public static void m1(int i) {
		System.out.println("m1 begin");
		m2(i);
		System.out.println("m1 end");
	}
	public static void m2(int i) {
		System.out.println("m2 begin");
		m3(i);
		System.out.println("m2 end");
	}
	public static void m3(int i) {
		System.out.println("m3 begin");
		System.out.println(i);
		System.out.println("m3 end");
	}
}
```

#### 内存图

![003-方法执行过程中的内存变化](方法执行过程中的内存变化.png)