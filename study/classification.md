# 分类算法



## 定义



​		分类是根据数据集的特点构造一个分类器, 利用分类器对未知类别的样本赋予类别的一种技术。构造分类器的过程一般分为训练和测试两个步骤。在训练阶段, 分析训练数据集的特点, 为每个类别产生一个对相应数据集的准确描述或模型。在测试阶段, 利用类别的描述或模型对测试进行分类, 测试其分类准确度。





## 类别



* 决策树
* 支持向量机
* 贝叶斯分类
* 关联规则分类
* mind算法
* GAC-RDB分类





## 实现举例



```R
library(rpart)
dtree<-rpart(churn~.,data=train,method = 'class',parms = list(split='information')) #生成树
prob<-predict(dtree,test,type = 'class')
dtree.perf<-table(test$churn,prob,dnn = c("Actual",'Predicted'))
dtree.perf
##       Predicted
## Actual  yes   no
##    yes  142   82
##    no    33 1410
```





