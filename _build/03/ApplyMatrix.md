---
redirect_from:
  - "/03/applymatrix"
interact_link: content/03/ApplyMatrix.ipynb
kernel_name: python3
has_widgets: false
title: 'Apply matrix to neural network computation'
prev_page:
  url: /03/Matrix
  title: 'Matrix'
next_page:
  url: /03/OutputLayer
  title: 'Design the Output Layer'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

## Apply matrix to neural network computation

Now that you understand the basics, let's see how we can apply matrix  to neural network computation.

Let's using the variables in our neural networks.

Before, the calculation formula we use is as follows:

$$a_1 = w_{1,1}x_1+w_{2,1}x_2 + b_1$$

$$a_2 = w_{1,2}x_1+w_{2,2}x_2 + b_2$$

$$a_3 = w_{1,3}x_1+w_{2,3}x_2 + b_3$$


Now, we use matrix to represent:

![x](img/x.png)

![x](img/w.png)

![x](img/b.png)

W is the matrix of weights, X is the matrix of inputs, B is the bias.

The formula for calculating the input of the hidden layer is as follows

$$A = XW + B$$

![xw.png](img/xw.png)

![xw+b.png](img/xw+b.png)

We use a simple matrix operation expression $A = XW + B$ to calculate the input of the hidden layer node. Even if we add more nodes, the formula will be the same. It's pretty neat and powerful.

Let's use Numpy for hidden layer node calculations.



{:.input_area}
```python
import numpy as np
X = np.array([x1, x2])
W = np.array([[w11, w12, w13], [w21, w22, w23]])
B = np.array([b1, b2, b3])
```




{:.input_area}
```python
A = np.dot(X,W) + B
print(A)
```


{:.output .output_stream}
```
[1.    1.34  1.188]

```



{:.input_area}
```python
Z = sigmoid(A)
print(Z)
```


{:.output .output_stream}
```
[0.73105858 0.79248994 0.76638318]

```

The calculation process looks a lot cleaner than it did before.
