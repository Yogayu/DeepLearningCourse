
输入和输出是我们决定的，但是隐藏层结果是由模型自己决定的，我们预先无法看见。

Unlikely the input and output which are strictly observable or hidden layers learned so we don't explicitly enforce any behavior on the hidden layer.

> 1. It's called “hidden” because their values are not given in the data; instead the model must determine which concepts are useful for explaining the relationships in the observed data. The images here are visualizations of the kind of feature represented by each hidden unit.
> 2. we can't see it 🤔


上述问题的根源在于全连接层只是对数据做仿射变换（affine transformation），而多个仿射变换的叠加仍然是一个仿射变换。解决问题的一个方法是引入非线性变换，例如对隐藏变量使用按元素运算的非线性函数进行变换，然后再作为下一个全连接层的输入。这个非线性函数被称为激活函数（activation function）。下面我们介绍几个常用的激活函数。

线性的分类器，叠加在一起，还是线性的分类器。