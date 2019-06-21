---
redirect_from:
  - "/part2/iris"
interact_link: content/part2/Iris.ipynb
kernel_name: python3
has_widgets: false
title: 'Iris Classification'
prev_page:
  url: /part2/Perceptron
  title: 'Perceptron'
next_page:
  url: 
  title: ''
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

# Iris Flowers Classification



{:.input_area}
```python
# dataset
from sklearn import datasets
# plot
import seaborn as sns
sns.set_style("darkgrid")
import matplotlib.pyplot as plt
# data manipulation
import pandas as pd
import numpy as np
# To display image in the jupyter notebook cell
%matplotlib inline
```


## Question

How to use a perceptron to classify data? 

To answer this question, let's look at an example first: there is a data set which consists of two species of Iris. Our question are: 
- How to classify those two species? 
- When given a new Iris, how to predict which Iris category it belongs to?

## Data Set

The data set we will use is modified from the Iris dataset which can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Iris/). It consists of 50 samples from each of **two species** of Iris (Iris setosa, Iris virginica). **Two features** were measured from each sample: the length of the sepals and petals, in centimeters.

Let's get a close look at the dataset.



{:.input_area}
```python
# read csv file
iris_dataset = pd.read_csv("iris_data.csv")
# show the first 5 lines
iris_dataset.head()
```





<div markdown="0" class="output output_html">
<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sepal length (cm)</th>
      <th>petal length (cm)</th>
      <th>target_class</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>1.4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>1.4</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>1.3</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.6</td>
      <td>1.5</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>1.4</td>
      <td>1</td>
    </tr>
  </tbody>
</table>
</div>
</div>



The columns in this dataset are:
- sepal length in cm
- petal length in cm
- Species
    - target_class 1: setosa
    - target_class -1: versicolor

![](./img/iris.png)

*Image source* [1](https://en.wikipedia.org/wiki/Iris_flower_data_set#/media/File:Iris_versicolor_3.jpg) [2](http://www.twofrog.com/images/iris38a.jpg)


## Classification

The following graph showing the measured sepal length and sepal length of Iris.



{:.input_area}
```python
sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_dataset,fit_reg=False,hue="target_class")
```





{:.output .output_data_text}
```
<seaborn.axisgrid.FacetGrid at 0x10d5a8eb8>
```




{:.output .output_png}
![png](/Users/yogayu/Library/Mobile%20Documents/com%7Eapple%7ECloudDocs/Documents/3%20%E9%A1%B9%E7%9B%AE/DeepLearningCourseGSoC/_build/images/part2/Iris_10_1.png)



I believe you can classify those two species category immediately.

Get back to our question: identify which category a new Iris belongs to?

Suppose the new Iris' sepal length is 5.5 cm and petal length is 3.2. We draw this new Iris point to the plot.



{:.input_area}
```python
new_iris_dataset = iris_dataset.append([{"sepal length (cm)":5.5, "petal length (cm)":3.2,"target_class":"unknown"}])
sns.lmplot("sepal length (cm)", "petal length (cm)", data=new_iris_dataset,fit_reg=False,hue="target_class")
```





{:.output .output_data_text}
```
<seaborn.axisgrid.FacetGrid at 0x1a1f8fecf8>
```




{:.output .output_png}
![png](/Users/yogayu/Library/Mobile%20Documents/com%7Eapple%7ECloudDocs/Documents/3%20%E9%A1%B9%E7%9B%AE/DeepLearningCourseGSoC/_build/images/part2/Iris_12_1.png)



The unknown dot is the new Iris. Obviously, it belongs to versicolor specie (target_clss=-1).

### Linear Classifier

This task is easy for us. We can classify them by eyes. However, the computer doesn't has eyes, how can it split those two groups?

You may have noticed that this is a two-dimensional plane, and if  want to separate the two classes, we can put a line between them. It looks like the following plot.



{:.input_area}
```python
x = np.linspace(4,8,18)
a = 0.1
b = 2
y = a * x + b

sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_dataset,fit_reg=False,hue="target_class")
plt.plot(x, y, '-r')
```





{:.output .output_data_text}
```
[<matplotlib.lines.Line2D at 0x1a1fc3fcc0>]
```




{:.output .output_png}
![png](/Users/yogayu/Library/Mobile%20Documents/com%7Eapple%7ECloudDocs/Documents/3%20%E9%A1%B9%E7%9B%AE/DeepLearningCourseGSoC/_build/images/part2/Iris_16_1.png)



All the points above the line are setosa category(-1), and all the points below the line are versicolor category(1). When a new Iris comes, a computer can predict which category it falls into by deciding whether it is above or below the line. 

Therefore, **if we can teach computer to find such a kind of line, we can solve our problem!** Let's do it.

In formal, a line in a two-dimensional plane can be represent as following:

$$ax + by + c = 0 $$

let:

$$w_0 = c$$
$$w_1 = a$$
$$w_2 = b$$


then it becomes:

$$w_1x + w_2y + w_0 = 0$$

Therefore, in mathematics form, all points above the line are:

$$w_1*x + w_2*y + w_0 > 0$$

and all points below and on the line are:

$$w_1*x + w_2*y + w_0 \leq 0$$


Actually, this is exactly **how a perceptron looks like when n = 2**:


$$
y=\left\{
\begin{array}{rcl}
0       &      & {w_0 + w_1x_1 + w_2x_2 + ... + w_nx_n > 0}\\
1     &      & {w_0 + w_1x_1 + w_2x_2 + ... + w_nx_n\leq 0}\\
\end{array} \right.
$$

let n = 2:

$$
y=\left\{
\begin{array}{rcl}
0       &      & {w_0 + w_1x_1 + w_2x_2 > 0}\\
1     &      & {w_0 + w_1x_1 + w_2x_2 \leq 0}\\
\end{array} \right.
$$


Because $f(x,y)$ is a linear function, we call it **a linear classifier**. To find a appropriate linear classifier of Iris, we need to find suitable $w_0,w_1$, and $w_3$.

## Implement a perceptron



{:.input_area}
```python
def classifier(x1,x2):
    w0 = 2
    w1 = 0.1
    w2 = -1
    
    value = w0 + w1*x1 + w2*x2
    print(value)
    
    if value > 0:
        return -1
    else:
        return 1
```




{:.input_area}
```python
classifier(5.1,1.4)
```


{:.output .output_stream}
```
1.1099999999999999

```




{:.output .output_data_text}
```
-1
```



## Vector

give some basic vector operation



{:.input_area}
```python
import numpy as np
x1 = 5.1 
x2 = 1.4

w1 = 0.1
w2 = -1

x = np.array([x1,x2])
w = np.array([w1,w2])
b = 2

print(np.sum(w*x) + b)
```


{:.output .output_stream}
```
1.11

```



{:.input_area}
```python
In next section, we will learn about how to use "Perceptron Learning Algorithm" to find those parameters.
```


## Reference
- [Iris data set](https://archive.ics.uci.edu/ml/datasets/Iris/)
- [perceptron introduction](https://medium.com/jameslearningnote/資料分析-機器學習-第3-2講-線性分類-感知器-perceptron-介紹-84d8b809f866)
