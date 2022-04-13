---
title: Java的枚举类型
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
summary: 枚举类型的学习 # 摘要内容
tags: # 标签
- Java
---

### Java的枚举类型

1. 使用enum作为关键字。

2. 枚举类型的常用在一个函数多个不同的返回状态，如果是两个返回状态可以使用boolean类型，但是如果是多个返回类型状态(情况)时需要使用枚举类型。

3. 尽量不要使用int类型作为返回值，因为这样可以随时修改返回值的值，程序也不会报错。

4. boolean类型也是特殊的枚举类型。

5. 枚举是一种引用数据类型

6. 枚举类型怎么定义，语法是？

   ```java
   enum 枚举类型名{
   	枚举值1,枚举值2
   }
   ```

7. 结果只有两种情况的，建议使用布尔类型。结果超过两种并且还是可以一枚一枚列举出来的，建议使用枚举类型。例如：颜色、四季、星期等都可以使用枚举类型。

8. 枚举中的每一个值，可以看做是“常量”

9. 枚举编译之后也是生成class文件。

###### 代码示例

```java
public class Test {
    public static void main(String[] args) {
        Result r = divide(10, 2);
        System.out.println(r == Result.SUCCESS ? "计算成功" : "计算失败");
    }

    /**
     * 计算两个int类型数据的商。
     * @param a a int数据
     * @param b b int数据
     * @return Result.SUCCESS表示成功，Result.FAIL表示失败！
     */
    public static Result divide(int a, int b){
        try {
            int c = a / b;
            return Result.SUCCESS;
        } catch (Exception e){
            return Result.FAIL;
        }
    }
}
// 枚举：一枚一枚可以列举出来的，才建议使用枚举类型。
// 枚举编译之后也是生成class文件。
// 枚举也是一种引用数据类型。
// 枚举中的每一个值可以看做是常量。
enum Result{
    // SUCCESS 是枚举Result类型中的一个值
    // FAIL 是枚举Result类型中的一个值
    // 枚举中的每一个值，可以看做是“常量”
    SUCCESS, FAIL
}
```

