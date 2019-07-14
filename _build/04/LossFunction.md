---
redirect_from:
  - "/04/lossfunction"
interact_link: content/04/LossFunction.ipynb
kernel_name: python3
has_widgets: false
title: 'Loss Function'
prev_page:
  url: /04/Intro
  title: '4. Training Neural Networks'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Loss funcation

Everyone makes mistakes. The wise are not people who never make mistakes, but those who forgive themselves and learn from their mistakes. —— Ajahn Brahm

When you take a math test, the teacher will mark you down for the mistakes you made. Your friend ask you how's your test? You may say: well, not bad. I made two mistakes and deducted 6 points. Then you learn from your mistakes and perform better the next time. The score you get on a test is an indicator. The fewer errors you make, the fewer points you deduct, the higher your score.

For neural network, there is such an indicator too. It's called **loss function** (or cost function). Many function can be used as loss function.

Let's think about which function should we use as loss function.

This table shows each node's actual value and target value.

|  Node | Actual value by network | Target training values |
| ---- | ----------------------- | ---------------------- |
| 1    | 0.6                     | 0.5                    |
| 2    | 0.6                     | 0.7                    |
| 3    | 0.7                     | 0.85                   |
| 4    | 0.95                    | 0.8                    |

The first thing that comes to mind is to use the difference between the target training values (t) and the actual value(y) calculated by neural network directly.


$$E = \sum_{i=1}^{n}\left ( y_{i} - t_{i} \right )$$


Here, $n$ is the number of output nodes. $y_{i}$ is the output value of neural network and $t_{i}$ is the target training value.

[add image]

Using this loss function, each node's error is:

| Node | Actual value by network | Target training values | Error |
| ---- | ----------------------- | ---------------------- | ----- |
| 1    | 0.6                     | 0.5                    | 0.1   |
| 2    | 0.6                     | 0.7                    | -0.1  |
| 3    | 0.7                     | 0.85                   | -0.15 |
| 4    | 0.95                    | 0.8                    | 0.15  |

And then we sum them up:

$$E = 0.1 + (-0.1) + (-0.15) + (0.15)$$
$$E = 0$$

As you can see, the positive and negative errors cancel each other out. So the total error become 0 which suggest the neural network makes no mistakes. However, that's not true.

## Mean Absolute Error

Maybe we can use the mean of absolute value of the difference. It's called The Mean Absolute Error (MAE).

$$E =\frac{1}{n} \sum_{i=1}^{n}\left | y_{i} - t_{i} \right |$$

| Node | Actual value by network | Target training values | Error |
| ---- | ----------------------- | ---------------------- | ----- |
| 1    | 0.6                     | 0.5                    | 0.1   |
| 2    | 0.6                     | 0.7                    | 0.1  |
| 3    | 0.7                     | 0.85                   | 0.15 |
| 4    | 0.95                    | 0.8                    | 0.15  |

$$E = 0.1 + 0.1 + 0.15 + 0.15$$
$$E = 0.6$$

[add image]

In this way, the above problem will be solved.



{:.input_area}
```python
import numpy as np
def mean_absolute_error(y, t):
    mse = 1/len(y) * np.sum(abs(y-t))
    return mse
```




{:.input_area}
```python
y = np.array([0.6, 0.6, 0.7, 0.95])
t = np.array([0.5, 0.7, 0.85, 0.8])
e = mean_absolute_error(y, t)
print(e)
```


{:.output .output_stream}
```
0.12499999999999997

```

## Mean Squared Error

There is one more common loss function: Mean Squared Error(MSE).

$$E = \frac{1}{n}\sum_{i=1}^{k}\left ( y_{k} - t_{k} \right )^2$$

[add image]



{:.input_area}
```python
import numpy as np
def mean_squared_error(y, t):
    mse = 1/len(y) * np.sum((y-t) ** 2)
    return mse
```




{:.input_area}
```python
y = np.array([0.6, 0.6, 0.7, 0.95])
t = np.array([0.5, 0.7, 0.85, 0.8])
e = mean_squared_error(y, t)
print(e)
```


{:.output .output_stream}
```
0.016249999999999994

```

Actually, we use MSE as loss function more than MAE. It relates to the gradient descent we'll talk about next. MAE isn’t continuous near the minimum which makes gradient descent not work so well.

## Cross Entropy Error
