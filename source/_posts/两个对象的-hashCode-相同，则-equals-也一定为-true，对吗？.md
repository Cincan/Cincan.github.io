---
title: 两个对象的 hashCode()相同，则 equals()也一定为 true，对吗？
date: 2020-12-22 22:13:46
tags:
---
# 两个对象的 hashCode()相同，则 equals()也一定为 true，对吗？

不对，两个对象的 hashCode()相同，equals()不一定 true。
代码示例：
```java
String str1 = "通话";
String str2 = "重地";
System.out.println(String.format("str1：%d | str2：%d",  str1.hashCode(),str2.hashCode()));
System.out.println(str1.equals(str2));
```
执行的结果：

```java
str1：1179395 | str2：1179395
false
```
代码解读：很显然“通话”和“重地”的 hashCode() 相同，然而 equals() 则为 false，因为在散列表中，hashCode()相等即两个键值对的哈希值相等，然而哈希值相等，并不一定能得出键值对相等。