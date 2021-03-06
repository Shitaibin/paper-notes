## 摘要
基于图的方法具有最好的表现力，在短文本聚类，最小聚类误差上而言。

## 引言
短文本聚类的特点：
1. 简明扼要
2. 原始的文本
3. 稀疏性

## 2. 短文本聚类

挑战：稀疏

文本聚类使用TFIDF特征向量，因此得到的向量维度相当高，而短文本的特性又造成，稀疏高维度的特性。

由于大部分词只出现1次，因此TFIDF向量会降低到IDF向量。

### K-means

度量：
1. 余弦相似度
2. Jaccard系数

K的大小：
手动更改K，选取有最小错误的K。

### 奇异值分解（SVD）

应用：文本话题识别。

SVD：把m x n的矩阵X分解为：
1. m x t的矩阵U：话题-文档
2. t x t的矩阵sigma：话题-话题相似度
3. t x n的矩阵Vt：term-话题

基于话题的文本聚类，不像tweets那样只有一个话题，可能包含多个话题。因此文章考虑了2中变种：
1) 只考虑该文档中最主流的话题
2) 只考虑该文档中最主流的前2个话题

### 相似传播/近邻传播

基于图的算法，每个节点是一个文档，边则是相似度，可想而知，这是一个完全图。

在这个图上使用近邻传播的算法。

## 3. 实验

### 数据集

Tweets：
611条。
1678个单词（已移除stop words）。

### 预处理

1. 移除stop words。
2. 单词转换为base form。
3. 为每个文档形成IDF向量。

### 评估

定义类相识度矩阵。 

*目前感觉不太合理。*

除非所谓的CMm是已知数据。

近邻传播算法error最小，度量为余弦相似度。

## 4.结论


























