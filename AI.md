# 人工智能总结分析
***

## Facebook开源
Facebook公司的人工智能硬件平台Big Sur开源
Facebook开源了三款人工智能图像分割（Image Segementation）软件：

* DeepMask
* SharpMask
* MultiPathNet

### 运行
		DeepMask生成初始对象mask、SharpMask优化这些mask，最后由MultiPathNet来识别这些mask框定的物体。SharpMask目前已遵循BSD授权协议在GitHub上公开源码。

## 深度学习框架
* Torchnet 与其他不同，不关注深度网络中的有效推论执行和梯度计算，而是提供一个位于深度学习框架之上的框架（也即torch/nn），从而方便快速试验。Torchnet提供一组子集包并执行五种主要类型的抽象化  
	
		  数据集--提供返回数据集中样本数的size函数，及一个返回到数据集中idx-th样本的get(idx)函数。  
	 	  数据集迭代器--从1到数据集尺寸的简单for循环，并调用get()函数的循环值作为输入。  
		  引擎--提供训练和测试模型所必须的标准逻辑。
		  计量仪--用作性能测量，比如一次训练的运行时间或所有样本的平均损失函数值。
		  日志--用来记录实验。	
	
* Caffe
* Chainer
* TensorFlow
* Theano

## TensorFlow
TensorFlow是一个采用数据流图（data flow graphs），用于数值计算的开源软件库。

* 节点（Nodes）
* 线（edges）--> 张量（tensor）

### 什么是数据流图（Data Flow Graph）
数据流图用“结点”（nodes）和“线”(edges)的有向图来描述数学计算。“节点” 一般用来表示施加的数学操作，但也可以表示数据输入（feed in）的起点/输出（push out）的终点，或者是读取/写入持久变量（persistent variable）的终点。“线”表示“节点”之间的输入/输出关系。这些数据“线”可以输运“size可动态调整”的多维数据数组，即“张量”（tensor）。张量从图中流过的直观图像是这个工具取名为“Tensorflow”的原因。一旦输入端的所有张量准备好，节点将被分配到各种计算设备完成异步并行地执行运算。
