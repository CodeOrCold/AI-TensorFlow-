# AI-TensorFlow-
怎么在Mac OSX系统 使用pip下安装TensorFlow (Docker下次补上)
# 目录
1. 机器学习
2. TensorFlow 介绍
    2.1 什么是 TensorFlow
    2.2 TensorFlow 能做什么
3. 安装 TensorFlow
    3.1 安装 pip
    3.2 安装 TensorFlow
    3.3 运行 Hello,TensorFlow 案例
4. 小结 

# 一、机器学习
机器学习，并不能理解成机器学习算法。机器学习，就是为了让机器可以去模拟人类。在应用实践上，可以狭义理解为机器学习算法，但聚焦在具体算法实现和编程上，往往实践中不尽人意。

机器学习是一种学科，一种类似数学的学科，交叉了数学、算法、计算机等多门学科。目的是让机器（这里指计算机）如何模拟或者实现人类的学习行为。就像我们读小学，读初中，读高中... 让机器学习的话可能需要 1 小时，因为机器效率很高。

# 二、TensorFlow 介绍
TensorFlow 是一个用于人工智能的开源神器

什么是 TensorFlow 呢？
TensorFlow™ 是一个采用数据流图（Data Flow Graphs），用于数值计算的开源软件库。节点（Nodes）在图中表示数学操作，图中的线（edges）则表示在节点间相互联系的多维数据数组，即张量（tensor）。它灵活的架构让你可以在多种平台上展开计算，例如台式计算机中的一个或多个 CPU（或GPU），服务器，移动设备等等。TensorFlow 最初由 Google 大脑小组（隶属于 Google 机器智能研究机构）的研究员和工程师们开发出来，用于机器学习和深度神经网络方面的研究，但这个系统的通用性使其也可广泛用于其他计算领域。

那什么是数据流图（Data Flow Graphs）呢？
数据流图用“结点”（nodes）和“线”(edges)的有向图来描述数学计算。“节点” 一般用来表示施加的数学操作，但也可以表示数据输入（feed in）的起点/输出（push out）的终点，或者是读取/写入持久变量（persistent variable）的终点。“线”表示“节点”之间的输入/输出关系。这些数据“线”可以输运“size可动态调整”的多维数据数组，即“张量”（tensor）。张量从图中流过的直观图像是这个工具取名为“Tensorflow”的原因。一旦输入端的所有张量准备好，节点将被分配到各种计算设备完成异步并行地执行运算。

TensorFlow 能做什么？
上面也说了，用于数值计算。具体而言，语音识别，自然语言理解，计算机视觉，广告等等。所以未来有更多的产品，将想法和机器学习算法产品化。

TensorFlow 的特征如下：
1. 高度的灵活性 
2. 真正的可移植性（Portability）  
3. 将科研和产品联系在一起 
4. 自动求微分 
5. 多语言支持 
6. 性能最优化

三、安装 TensorFlow
环境：Mac OS 10.x
TensorFlow 支持多种安装，比如 Pip, Docker, Virtualenv, Anaconda 或源码编译的方法安装 TensorFlow。我自己推荐当然是 Pip 安装。什么是 Pip ？Pip 是一个 Python 的软件包安装与管理工具。

1. 安装 pip
pip 下载地址：https://pypi.python.org/pypi/pip
然后解压 pip ，并执行 python 进行安装。
tar zvxf pip-9.0.1.tar.gz
cd pip-9.0.1 
sudo python setup.py install

2. 安装 TensorFlow
用 pip 安装 TensorFlow ：
sudo pip install https://storage.googleapis.com/tensorflow/mac/tensorflow-0.5.0-py2-none-any.whl

Mac OS X 10.x 因 SIP 安全问题无法运行，安装会不成功。所以重启 OS，长按 Command + R 。点击 Utilities（实用工具）-> Terminal（终端），输入如下命令：
csrutil disable

然后开机，重新用 pip 安装 TensorFlow ：
sudo pip install https://storage.googleapis.com/tensorflow/mac/tensorflow-0.5.0-py2-none-any.whl
（需要翻墙>_<!）

3. 运行 Hello,TensorFlow 案例
使用 TensorFlow, 你必须明白 TensorFlow:
a. 使用图 (graph) 来表示计算任务.
b. 在被称之为 会话 (Session) 的上下文 (context) 中执行图.
c. 使用 tensor 表示数据.
d. 通过 变量 (Variable) 维护状态.
e. 使用 feed 和 fetch 可以为任意的操作(arbitrary operation) 赋值或者从其中获取数据

这里我们执行下 HL:Hello,TensorFlow 。证明 TensorFlow 安装成功就好。打开 PyCharm，新建一个 HL_HelloTensorFlow.py 。创建一个字符串常量，然后创建一个 Session 对象，从会话中构造器中会默认启动一个图，Session 对象使用后要需要关闭并释放资源。
代码如下：
# -*- coding: utf-8 -*-
import tensorflow as tf

# 创建另外一个字符串常量
helloTf = tf.constant('HL:Hello,TensorFlow!')

# 启动默认图
sess = tf.Session()

# 调用 sess 的 'run()' 方法来执行
# 返回值 'result' 是一个字符串对象.
result = sess.run(helloTf)
print result
# ==> HL:Hello,TensorFlow!

# 任务完成, 关闭会话.
sess.close()

然后运行即可得到输出：
HL:Hello,TensorFlow!

四、小结
本文主要介绍了机器学习、TensorFlow 安装及简单使用。
