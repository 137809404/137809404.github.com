---
title: Multiplying Matrices Without Multiplying
date: 2021-10-07 21:45:42
tags:
- 论文
categories：
- 论文笔记
---



## Abstract

### 方法

* 近似矩阵乘法
* 操作
    * hashing
    * averaging
    * byte shuffling

### 结果

* 速度
    * 100×精确计算方法
    * 10×现有近似计算方法
* 特性
    * 矩阵已知时，无需乘加操作（a+b×c）

---

## 算法背景

### PQ

1. Prototype Learning
    - 使用现有矩阵A~进行K-means聚类
2. Encoding Function（g(a)）
    - 寻找近似向量
    - ![](.\Multiplying-Matrices-Without-Multiplying\image-20210913151208828.png)
3. Table Construction（h(b)）
    - 预先计算b与子空间每个向量的点积并存储，记作c表
    - 输入b，在c表中查找近似点积结果
    - ![](.\Multiplying-Matrices-Without-Multiplying\image-20210913151226194.png)
4. Aggregation
    - 聚合g(a)与h(b)的结果，将C表对应位置结果相加
    - ![](.\Multiplying-Matrices-Without-Multiplying\image-20210913151338536.png)



----

## 论文方法

- g(a)

    - 使用平衡二叉树对训练集进行聚类

- h(b)

  ![image-20210913152049269](.\Multiplying-Matrices-Without-Multiplying\image-20210913152049269.png)

- f(·,·)

    - ![image-20210913152148362](.\Multiplying-Matrices-Without-Multiplying\image-20210913152148362.png)

