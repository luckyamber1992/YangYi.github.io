---
title: hash table
date: 2023-08-02 15:21:52
tags:
  - data structures
  - algorithms
  - hash table
---

# python 中的 hash 结构

## set

- 增

  > my_set=set()
  > my_set.add(1)
  > my_set.update([1,2,3])

- 删

  > my_set.remove(1) 若元素不存在会报错
  > my_set.discard(1) 若元素不存在不会报错
  > my_set.pop()无序删除并返回元素

- 改
  set 不允许修改操作
- 查
  > for i in my_set:

### 集合间操作

该类操作不改变原集合

- union 求并集/ |
  set_1.union(set_2)
- intersection/ &
  set1.intersection(set2)
- difference/ -
  set2-set1

### 应用

set 的查找和插入操作效率很高，非常适合用来记录元素是否出现过

## 字典

字典中 key 无重复，别名 index，map

- 增
  update
  dict_1.update(dict_2)
- 查找
  if 'a' in dict_1:
  print(dict_1['a'])
  get()
  dict_1.get('a',-1)注：如果没有‘a’返回-1
  获取所有的 key
  dict_1.keys()
  获取所有 values
  dict_1.values()
  获取所有 items
  dict_1.items()
  for （key,val) in dict_1.items():
- 删
  del dict_2['food']

### 应用

可以用来记录某些元素是否出现过，同时还可以附带元素位置
【附】经典练习题 two sum

## 集合和字典总结

- set 元素和 key 元素必须可以 hash
  【附】不可变元素都是可以 hash 的，可变元素如 list、set、dict 都不可以

## 哈希表 Vs BST

- hash table 插入，删除，查找操作都是 o（1），空间消耗大
- bst 支持数据排序，在给出范围的情况下进行查找更快，对于平衡的 bst，时间复杂度为 o（logn），空间消耗小
  ![summary pic](../%E4%B9%B1%E4%B8%83%E5%85%AB%E7%B3%9F/Screenshot%202023-08-02%20at%2014.45.56.png)

## 哈希表的构建

### 哈希函数

- 输入任何二进制的数据返回的输出是一定的
- 输出是整数
- 计算复杂度不太高
- 尽量避免 collision

### 解决 collision

- open hashing
  开一个数组，其中每一个元素为链表的 head node 的引用（地址）
- closed hashing
- rehashing
  动态调整 hash 表空间
