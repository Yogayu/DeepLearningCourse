---
redirect_from:
  - "/03/forwardpropagation"
interact_link: content/03/ForwardPropagation.ipynb
kernel_name: python3
has_widgets: false
title: 'How the single pass through the network—Forward Propagation'
prev_page:
  url: /03/ActivateFunction
  title: 'Activate Function'
next_page:
  url: /03/Matrix
  title: 'Efficient Matrix'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Forward Propagation

Now we get familiar with the deep feedforward networks's structure, we are going to learn how the single pass through the network.

There is a two-layer neural network with one hidden layer. Here the value of input $x_1$ and $x_2$ are:



{:.input_area}
```python
x1 = 0.2
x2 = 0.8
```


We start with some random weights and bias from between layer0 and layer1:



{:.input_area}
```python
# Layer 0 to Layer 1
b1 = 0.4
b2 = 0.56
b3 = 0.64

w11 =1.0
w12 = 0.7
w13 = 0.34
w21 = 0.5
w22 = 0.8
w23 = 0.6
```


![initLayer](img/initLayer.png)

This animation shows how the single pass through the network:

![video](video/layer.gif)

A hidden unit in hidden layer looks like this:

![HiddenUnit](img/Node.png)

Here we use sigmod function as activate function h(x).



{:.input_area}
```python
import numpy as np
def sigmoid(x):
    return 1 / (1 + np.exp(-x))
```



The first layer of nodes is input layer which doing nothing but input signals. Notice that we add a bias node which weight is $b_1$.

Move to the second layer, let's calculate input of first node:

$$a_1 = w_{1,1}x_1+w_{2,1}x_2 + b_1$$

The input nodes have values of 0.2 and 0.8. The weight of bias node in input layer and the first node in hidden layer is 0.4. The weight from second node in input layer is 0.1. The link weight from third node is 0.5. So the combined $a_1$ input is:

$$a_1 = 1 * 0.2 + 0.5 * 0.8 + 0.4$$

$$a_1 = 0.2 + 0.4 + 0.4$$

$$a_1 =1$$



{:.input_area}
```python
a1 = w11 * x1 + w21 * x2 + b1
print(a1)
```


{:.output .output_stream}
```
1.0

```

Then we calculate the output of this node using activate function $h(x) = sigmod(x)$.

$$z_1 = sigmod(a_1)$$

$$ z_1 =  \frac{\mathrm{1} }{\mathrm{1} + e^{-1.1} }  $$

$$z_1 = 0.7310585786300049$$




{:.input_area}
```python
z1 = sigmoid(a1)
print(z1)
```


{:.output .output_stream}
```
0.7310585786300049

```

Cool! We have finished calculate the first node's output. 

The remaining two nodes can be calculated with the same way.

The second node of hidden layer:

$$a_2 = w_{1,2}x_1+w_{2,2}x_2 + b_2$$

$$a_2 = 0.7 * 0.2 + 0.8* 0.8 + 0.4 = 1.3400000000000003$$

$$z_2 = sigmod(a_2) = 0.7924899414403644$$



{:.input_area}
```python
a2 = w12 * x1 + w22 * x2 + b2
print(a2)
```


{:.output .output_stream}
```
1.3400000000000003

```



{:.input_area}
```python
z2 = sigmoid(a2)
print(z2)
```


{:.output .output_stream}
```
0.7924899414403644

```

The third node of hidden layer:

$$a_3 = w_{1,3}x_1+w_{2,3}x_2 + b_3$$

$$a_3 = 0.34 * 0.2 + 0.6 * 0.8 + 0.4 = 1.1880000000000002$$

$$z_3 = sigmod(a_3) = 0.7663831750110293$$



{:.input_area}
```python
a3 = w13 * x1 + w23 * x2 + b3
print(a3)
```


{:.output .output_stream}
```
1.1880000000000002

```



{:.input_area}
```python
z3 = sigmoid(a3)
print(z3)
```


{:.output .output_stream}
```
0.7663831750110293

```

For each node we need to write the corresponding calculation formula, now we just handwritten three nodes, you are likely to get the wrong index. In the future, our network will become more and more complex, and there may be hundreds or thousands of nodes. If we still use such a way, it would be difficult to ensure that nothing goes wrong, isn't it?

So how do we simplify this? Actually using the matrix in mathematics can simplify and speed up the node's calculation of the computer. Let's see what's going on in next section.
