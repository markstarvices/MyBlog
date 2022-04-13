---
title: Java的HashSet集合
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
summary: HashSet集合 # 摘要内容
tags: # 标签
- Java
---

### HashSet集合

1. HashSet集合：
   1. 无序不可重复。
      1. 无序：存储时顺序和取出的顺序不同。
      2. 不可重复。
      3. 放到HashSet集合中的元素实际上是放到HashMap集合的key部分了。

###### 代码示例

```java
import java.util.*;

public class Test {
    public static void main(String[] args) {
        Set<String> stringSet = new HashSet<>();
        // 添加元素
        stringSet.add("Hello");
        stringSet.add("Word");
        stringSet.add("Hello");
        stringSet.add("def");
        stringSet.add("Hello");
        stringSet.add("Hello");
        for (String str:stringSet) {
            System.out.println(str);
            /*Word
            Hello
            def*/
        }
    }
}
```

