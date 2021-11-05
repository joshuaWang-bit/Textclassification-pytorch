# Textclassification-pytorch
练习题，基于torchtext，huggingface，pytorch，在一个中文多分类任务和一个英文二分类任务上实验了TextCNN，BERT和XLnet三个模型。

中文数据是：清华NLP组提供的THUCNews新闻文本分类数据集
英文数据是：https://www.kaggle.com/nopdev/real-and-fake-news-dataset

xlnet介绍
结合了自回归和自编码两种目标函数
bert采用的是AE自编码，将输入复制到输出
传统的单项语言模型ELMo,GPT则是假设序列数据存在线性关系，使用历史数据预测下一位数据，是自回归模型
作者指出BERT采用的AE方法存在两个问题
1）盖住的token并不是互相独立的，忽略了token之间的联系
2）预训练和精调阶段存在差异，因为在预训练阶段大部分输入都包含[MASK]，引入了噪声。
这篇文章提出了Permutation Language Modeling
并使用了two-stream的训练方法，对乱序排列的模型添加位置编码
