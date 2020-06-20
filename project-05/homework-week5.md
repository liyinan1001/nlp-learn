# Homework-week5
## 前三题必做

## 1. 不考虑多头的原因，self-attention中词向量不乘QKV（Wq、Wk、Wv）参数矩阵，会有什么问题？
一方面，没有QKV矩阵就无法表征一个词语和其他词语之间的attention关系。另一方面，QKV矩阵对于不同的输入词语是共享的，是一种参数共享机制，能够抽取出句子中的高阶特征。

## 2. Transformer的点积模型做缩放的原因是什么？
点积的结果会输入到softmax层。softmax函数在输入的绝对值较大时梯度很小，会导致梯度下降的速度太慢。缩放后softmax的输入值得绝对值较小，梯度较大，训练速度快。
## 3. Self-Attention 的时间复杂度是怎么计算的？为多少？

词向量矩阵X.shape = (n, d)  
矩阵W<sup>Q</sup>, W<sup>K</sup>, W<sup>V</sup>, shape = (d, h)  
矩阵Q, K, V, shape = (n, h)   
矩阵S =  Q \* K<sup>T</sup>, shape = (n, n)    
time complexity (X \* W<sup>Q</sup>) = O(ndh)  
time complexity (Q \* K<sup>T</sup>) = O(n<sup>2</sup>h)  
time complexity (softmax(S)) = O(n<sup>2</sup>)   
time complexity (S \* V) = O(n<sup>2</sup>h)  
最终的 time complexity = O(ndh) + O(n<sup>2</sup>h) ~ O(n<sup>2</sup>d)  

## 附加思考题（可做可不做）：

根据问题3求的计算复杂度可以看出，输入序列长度过长会造成计算量太大，那你有什么的想法从结构上改进么？  
可以每个词不和所有词计算attention，而是和相邻的一些词计算。复杂度会下降为O(nrd)，r为选取的相邻词的数目









