---
title: Java的HashTable集合
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
summary: HashTable与HashMap的区别 # 摘要内容
tags: # 标签
- Java
---

### Hashtable与HashMap的区别

1. Hashtable的key可以为null吗？
   1. Hashtable的key和value都是不能为null的。HashMap集合的key和value都是可以为null的。
2. Hashtable方法都带有synchronized：线程安全的。线程安全有其它的方案，这个Hashtable对线程的处理导致效率较低，使用较少了。
3. Hashtable和HashMap一样，底层都是哈希表数据结构。Hashtable的初始化容量是11，默认加载因子是：0.75f，Hashtable的扩容是：原容量 * 2 + 1
4. HashMap和Hashtable的区别。
   1. HashMap：
      1. 初始化容量16，扩容2倍。非线程安全，key和value可以为null。
   2. Hashtable：
      1. 初始化容量11，扩容2倍+1，线程安全，key和value都不能是null。

```java
import java.util.*;

public class Test {
    public static void main(String[] args) {
        Map map = new Hashtable();
        // map.put(null,123); // java.lang.NullPointerException异常
        map.put(100,null); // // java.lang.NullPointerException异常
    }
}
```

