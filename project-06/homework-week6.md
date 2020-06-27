# Homework-week6
## 前三题必做

## 1. 为什么BERT在第一句前会加一个[CLS]标志?
预训练任务中需要有一个vector用来表征整个sequence的特征。由于self attention机制，[CLS]对应的输出整合了sequence中所有token的信息，可以表示整个句子的特征。其本质类似于句子中所有token的pooling
## 2. BERT的训练任务有几个，具体描述下每个任务的内容？
masked language model （MLM）和 next sentence prediction (NSP)  
MLM: 将输入词的15%掩盖，使得输出满足相应条件。包括80%的 mask -> 原词，10%的错词 -> 原词，10% 原词->原词。  
NSP: 预测两个句子是否相连。正样本为相连的句子，负样本为构造的原本不相连的句子。  
两个任务的loss相加为整体的loss


## 3. 如何利用BERT等预训练模型完成抽提式文本摘要任务？  
训练数据中文本的句子会被标注为是否属于摘要。将整个文本输入预训练好的bert模型，每个句子对应的[CLS]的输出vector经过一些summarization layer后预测这个句子是否属于摘要。还是cross entropy loss。

## 附加思考题（可做可不做）：

BERT有哪些可以提升的地方呢？  









