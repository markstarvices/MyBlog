---
title: Java的Vector集合
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
summary: Vector底层也是一个数组。 # 摘要内容
tags: # 标签
- Java
---

### Vector

1. Vector底层也是一个数组。初始化容量：10

2. 怎么扩容的？

   1. 扩容之后是原容量的2倍。10--> 20 --> 40 --> 80	

3. ArrayList集合扩容特点：ArrayList集合扩容是原容量1.5倍。

4. Vector中所有的方法都是线程同步的，都带有synchronized关键字，是线程安全的。效率比较低，使用较少了。

5. 怎么将一个线程不安全的ArrayList集合转换成线程安全的呢？

   1. 使用集合工具类：

      ```java
      java.util.Collections;
      java.util.Collection // 是集合接口。
      java.util.Collections // 是集合工具类。
      ```

###### 代码示例

```java
import java.util.*;

public class Test {
    public static void main(String[] args) {
        // 创建一个Vector集合
        List list = new Vector();
        // 添加元素
        // 默认容量10个。
        for (int i = 1; i <= 10; i++) {
            list.add(i);
        }
        // 满了之后扩容（扩容之后的容量是20.）
        list.add(11);
        Iterator iterator = list.iterator();
        while (iterator.hasNext()){
            Object obj = iterator.next();
            System.out.println(obj);
        }

        // 这个可能以后要使用！！！！
        List myList = new ArrayList(); // 非线程安全的。

        // 变成线程安全的
        Collections.synchronizedList(myList);
        // myList集合就是线程安全的了。
        myList.add("def");
    }
}
```

