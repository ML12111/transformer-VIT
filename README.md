## 代码使用简介
1. 下载好数据集，代码中使用的是CIFAR100。注意数据集格式如下：
- CIFAR100
	- \- test
    	- 0
        - 1
        - 2
        - …
     - \- train
    	- 0
        - 1
        - 2
        - …

其中一个类别对应一个文件夹，属于相同类别的图片存放在同一文件夹中。注意将训练以及预测脚本中的`num_classes`设置成你自己数据的类别数。在`unzip.ipynd`脚本中解压数据集。
2. 在`train.py`脚本中将`--data-path`设置成解压后的训练集文件夹绝对路径
3. 下载预训练权重，在`model.py`文件中每个模型都有提供预训练权重的下载地址，根据自己使用的模型下载对应预训练权重
4. 在`train.py`脚本中将`--weights`参数设成下载好的预训练权重路径
5. 设置好数据集的路径`--data-path`以及预训练权重的路径`--weights`就能使用`train.py`脚本开始训练了(训练过程中会自动生成`class_indices.json`文件)
6. 在`test.ipynd`脚本中导入和训练脚本中同样的模型，并将`model_weight_path`设置成训练好的模型权重路径(默认保存在weights文件夹下)。将`data_root`改成测试集根目录，即可对测试集准确率、召回率、F1分数进行计算（包括对每个类别的三种指标计算以及平均结果），并输出其柱形图，同时输出混淆矩阵。