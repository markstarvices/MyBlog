---
title: Java的List集合
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
summary: List集合概述 # 摘要内容
tags: # 标签
- Java
---

### List集合

1. List集合存储元素特点：

   1. 有序可重复
      1. 有序：List集合中的元素有下标。从0开始，以1递增。
      2. 可重复：存储一个1，还可以再存储1。

2. List既然是Collection接口的子接口，那么肯定List接口有自己“特色”的方法：以下只列出List接口特有的常用的方法：

   ```java
   void add(int index, Object element) // 在列表的指定位置插入指定元素（第一个参数是下标）
   Object set(int index, Object element) // 修改指定位置的元素
   Object get(int index) // 获取指定位置的元素。
   int indexOf(Object o) // 获取指定对象第一次出现处的索引。
   int lastIndexOf(Object o) // 获取指定对象最后一次出现处的索引。
   Object remove(int index) // 删除指定下标位置的元素
   ```
   
3. 迭代器迭代元素的过程中不能使用集合对象的remove方法删除元素，要使用迭代器Iterator的remove方法来删除元素，防止出现异常：ConcurrentModificationException


###### 代码示例

```java
import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;

public class Test {
    public static void main(String[] args) {
        // 创建List类型的集合。
        List list = new ArrayList();
        // 添加元素
        list.add("A");// 默认都是向集合末尾添加元素。
        list.add("B");
        list.add("C");
        // 在列表的指定位置插入指定元素（第一个参数是下标）
        // 这个方法使用不多，因为对于ArrayList集合来说效率比较低。
        list.add(1, "KING");
        // 迭代
        Iterator iterator = list.iterator();
        while (iterator.hasNext()){
            Object obj = iterator.next();
            System.out.println(obj);
        }
        // 根据下标获取元素
        Object firstObj = list.get(0);
        System.out.println(firstObj);// A
        // 因为有下标，所以List集合有自己比较特殊的遍历方式
        // 通过下标遍历。[List集合特有的方式，Set没有。]
        for (int i = 0; i < list.size(); i++) {
            Object allObj = list.get(i);
            System.out.println(allObj);
        }
        // 获取指定对象第一次出现处的索引。
        System.out.println(list.indexOf("C")); // 3
        // 获取指定对象最后一次出现处的索引。
        System.out.println(list.lastIndexOf("C")); // 3
        // 删除指定下标位置的元素
        // 删除下标为0的元素
        System.out.println(list.size());// 4
        list.remove(0);
        System.out.println(list.size()); // 3

        // 修改指定位置的元素
        list.set(2, "Soft");
        // 遍历集合
        for(int i = 0; i < list.size(); i++){
            Object obj = list.get(i);
            System.out.println(obj);
        }
    }
}
```

