---
title: Java的foreach写法
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
summary: 类似Python的for循环 # 摘要内容
tags: # 标签
- Java
---

### foreach的学习

增强for（foreach）

##### 语法

```java
for(元素类型 变量名 : 数组或集合){
	System.out.println(变量名);
}
```

###### 代码示例

```java
import java.util.*;

public class Test {
    public static void main(String[] args) {
        // int类型数组
        int[] arr = {1314,521,100};
        // 遍历数组（普通for循环）
        for(int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
        // foreach有一个缺点：没有下标。在需要使用下标的循环中，不建议使用foreach循环。
        for (int data : arr){
            // data就是数组中的元素（数组中的每一个元素。）
            System.out.println(data);
        }
        List<String> stringList = new ArrayList<>();
        stringList.add("abc");
        stringList.add("def");
        for (String str : stringList) {
            System.out.println(str);
        }
    }
}
```

