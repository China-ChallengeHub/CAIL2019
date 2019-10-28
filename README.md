# 中国法研杯相似案例匹配Top1团队解决方案

## 赛题介绍
大赛共有三个赛道，我们参加了其中的法律文书“相似案例匹配”赛道。相似案例匹配赛题是针对多篇法律文书进行相似度的计算和判断。数据集是“中国裁判文书网”公开的民间借贷相关法律文书，每组数据由三篇法律文书组成。文书主要为案件的事实描述部分，选手需要从两篇候选集文书中找到与询问文书案件性质更为相似的一篇文书。

比赛分三个阶段。第一阶段训练数据有500组三元文书，我们用(A, B, C)表示一条数据中的三篇文书。每条数据中A与B的相似度大于A与C的相似度。第二阶段有5102组训练数据，第三阶段为封闭式评测阶段。每个阶段如果预测正确，那么该测试数据可以得到1分，否则是0分。每个阶段成绩为在该阶段的平均准确率。最终成绩计算方式： 第二阶段的成绩 * 0.3 + 第三阶段的成绩 * 0.7。

详情可查看[官网网站](http://cail.cipsc.org.cn/)和[官方Github](https://github.com/china-ai-law-challenge/CAIL2019)。

## 项目构建

#### 软件依赖
* Python 3.6+
* PyTorch 1.1.0+
* requirements.txt
* Windows 和 Linux 均可

### 模型文件
比赛中使用的BERT模型文件来自刘知远老师提供的[预训练模型文件](https://github.com/thunlp/OpenCLaP)。

#### 切分数据集
```
$ cd datasets
$ python ./split_folds.py
$ cd ..
```

### 模型训练
```
$ python train_bert.py
```

### 模型预测
```
$ python main.py
```