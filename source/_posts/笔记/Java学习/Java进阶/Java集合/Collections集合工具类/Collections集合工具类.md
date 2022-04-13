---
title: Java的Collections集合工具类
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
summary: Collection是接口，Collections是一个集合工具类 # 摘要内容
tags: # 标签
- Java
---

### Collections集合工具类

java.util.Collection 集合接口

java.util.Collections 集合工具类，方便集合的操作。

#### 常用方法

```java
Collections.synchronizedList(); // 变成线程安全的
Collections.sort(list); // 对list进行排序，前提是必须实现compareTo方法。（要求集合中元素实现Comparable接口。）
```

###### 代码示例

```java
import java.util.*;
public class Test {
    public static void main(String[] args) {
        // ArrayList集合不是线程安全的。
        List<String> list = new ArrayList<>();
        // 变成线程安全的
        Collections.synchronizedList(list);
        list.add("aba");
        list.add("abc");
        list.add("abb");
        Collections.sort(list);
        for (String str : list){
            System.out.println(str);
            /**
             * aba
             * abb
             * abc
             */
        }
        // 自定义类型的排序
        List<User> userList = new ArrayList<>();
        userList.add(new User(100));
        userList.add(new User(50));
        Collections.sort(userList);
        for (User user : userList){
            System.out.println(user);
            /**
             * User{age=50}
             * User{age=100}
             */
        }
        // 对Set集合怎么排序呢?
        Set<String> set = new HashSet<>();
        set.add("sort");
        set.add("king");
        // 将Set集合转换成List集合
        List<String> stringList = new ArrayList<>(set);
        Collections.sort(stringList);
        for (String str : stringList){
            System.out.println(str);
            /**
             * king
             * sort
             */
        }
        // 这种方式也可以排序。
        // Collections.sort(list集合, 比较器对象);
    }
}
class User implements Comparable<User>{
    private int age;
    public User(int age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "User{" +"age=" + age +'}';
    }

    @Override
    public int compareTo(User user) {
        return this.age - user.age;
    }
}
```

