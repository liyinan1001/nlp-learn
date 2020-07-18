# Homework-week7
## 前三题必做

## 1. MATCHSUM里面pearl-summary是什么？为什么要找到pearl-summary？
sentence-level extractor分数低，summary-level extractor分数高的摘要称为pearl-summary。因为实验结果发现很多数据集里的标签摘要都是pearl-summary，因此最好的摘要应该不仅仅提取sentence-level分数高的句子，而是要考虑summary-level extractor分数
## 2. 知识蒸馏里参数T（temperature）的意义？
当T=1时即为标准softmax，当T增加时，softmax函数产生的概率分布更加soft，可能包含了关于class分布的更多信息，这被称为teacher model里的"dark knowledge"。让student model学习teacher model的dark knowledge有助于knowledge transfer。
## 3. TAPT（任务自适应预训练）是如何操作的？
目标任务提供的有标签数据集，可以去掉标签后作为pretrain的数据集。进一步增加预训练模型在目标任务上的表现。
## 附加思考题（可做可不做）：

从模型优化的角度，在推理阶段，如何更改MATCHSUM的孪生网络结构？









