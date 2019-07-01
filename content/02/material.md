### Non-linear activate function
The activate function in neural network must be an non-linearities function.

Why activate function must to be non-linearities function? 

Generally speaking, the purpose of activation functions is to introduce non-linearities into the network.

The activate function in neural network must be an non-linearities function.

Why activate function must to be non-linearities function? 

Generally speaking, the purpose of activation functions is to introduce non-linearities into the network. If we only allow linear activation functions in a neural network, the output will just be a linear transformation of the input. The activation function does the non-linear transformation to the input making it capable to learn and perform more complex tasks. From another point of view, without non-linear function, adding more layer to the network would be nonesence.



$h(h(h(x))) = a*a*a*x$

要知道如何传播，才能知道为什么需要用非线性的计划函数。

线性可分和线性不可分：什么是线性可分

线性分类器叠加在一起还是只是线性的。但是在真实数据中，很多数据都是线性不可分的。所以，我们就需要非线性的激活函数。使得神经网络可以处理复杂的情况。

1. 如果没有激活函数，那么神经网络的权重、偏置全是线性的仿射变换（affine transformation）。仿射变换是啥？
2. 如果是使用线性函数作为激活函数，那么叠加层就没有了意义。为了发挥叠加层带来的优势。