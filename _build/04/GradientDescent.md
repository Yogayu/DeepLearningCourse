---
redirect_from:
  - "/04/gradientdescent"
interact_link: content/04/GradientDescent.ipynb
kernel_name: python3
has_widgets: false
title: 'Learning to minimize error gradient descent algorithm'
prev_page:
  url: /04/LossFunction
  title: 'How well does the neural network predict? Loss function'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Learning to minimize error: gradient descent algorithm

The goal of neural network is adjust the weight to minimize error. The error is a function of the network weights and biases. 

![](img/GA0.png)

The error is a function of the network weights and biases. 

So our goal of training is to find weights and biases which minimize the cost function.

In last section, we have introduced MAE loss function:

$$L(w, b) = \frac{1}{n}\sum_{i=1}^{n}\left ( y_{i} - t_{i} \right )^2$$

$$y_i = \sigma (w_ix_i+b_i)$$

$$L(w, b) = \frac{1}{n}\sum_{i=1}^{k}\left ( \sigma (w_ix_i+b_i) - t_{i} \right )^2$$

L 是关于 w，b 的函数。在此，我们不通过代数的方法去找到 L 最小值时，w、b的取值，因为对于该函数，那样太复杂。

我们会使用梯度下降的方法，让我们一起开始了解吧。

我们来看一个简单的神经网络，一共有两层，每一层中都只有一个节点。



{:.input_area}
```python
def numerical_gradient(f, x):
    h = 1e-4
    grad = np.zero_like(x)
    
    for idx in range(x.size):
        tmp_val = x[idx]
        x[idx] = tmp_val + h
        fxh1 = f(x)
        
        x[idx] = tmp_val - h
        fxh2 = f(x)
        
        grad[idx] = (fxh1 -fxh2) / (2*h)
        x[idx] = tmp_val
        
    return grad
```

