
# Classifying Iris Flowers 【Draft】
## Simple Perceptron Learning Algorithm


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

How could machine learn from data? To answer this question, let's look at an example first: there is a data set winch consists two species of Iris, how to classify those two species? When given a new Iris, how to predict which Iris category it belongs to?

## Data Set

The data set we will use is modified from the Iris dataset which can be found on the [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Iris/). It consists of 50 samples from each of **two species** of Iris (Iris setosa, Iris virginica). **Two features** were measured from each sample: the length of the sepals and petals, in centimeters.

Let's get a close look at the dataset.


```python
# read csv file
iris_dataset = pd.read_csv("iris_data.csv")
# show the first 5 lines
iris_dataset.head()
```




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


```python
sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_dataset,fit_reg=False,hue="target_class")
```




    <seaborn.axisgrid.FacetGrid at 0x1a1f592630>




![png](output_10_1.png)


I believe you can classify those two species category immediately.

Get back to our question, identify which category a new Iris belongs to?

Suppose the new Iris' sepal length is 5.5 cm and petal length is 3.2. We draw this new Iris to the plot.


```python
new_iris_dataset = iris_dataset.append([{"sepal length (cm)":5.5, "petal length (cm)":3.2,"target_class":"unknown"}])
sns.lmplot("sepal length (cm)", "petal length (cm)", data=new_iris_dataset,fit_reg=False,hue="target_class")
```




    <seaborn.axisgrid.FacetGrid at 0x1a1f59bba8>




![png](output_12_1.png)


The unknown dot is the new Iris. Obviously, it belongs to versicolor specie (target_clss=-1).

This task is easy for us. We can classify them by eyes. Howevere, the computer doesn't has eyes, how can it split those two groups?

You may have noticed that this is a two-dimensional plane, and if  want to separate the two classes, we can put a line between them. It looks like the following plot.


```python
x = np.linspace(4,8,18)
a = 0.1
b = 2
y = a * x + b

sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_dataset,fit_reg=False,hue="target_class")
plt.plot(x, y, '-r')
```




    [<matplotlib.lines.Line2D at 0x1a1f033550>]




![png](output_15_1.png)


All the points above the line are setosa category(-1), and all the points below the line are versicolor category(1). When a new Iris comes, a computer can predict which category it falls into by deciding whether it is above or below the line. 

Therefore, **if we can teach computer to find such a kind of line, we can solve our problem!** Let's do it.

In formal, this line in a two-dimensional plane can be represent as following:

$$y = ax + b$$


In other words, y is the function f of x:

$$f(x) = ax + b$$


Because $f(x)$ is a linear function, we call it **a linear classifier**.

### Training a linear classifier

To focus on the essential concept, we simply the problem by supposing that parameter $b$ is known as 2.

Which means the liner function becomes:

$$y = ax + 2$$

We'll use data to train this line to be a suitable linear classifier. Essentially, it's looking for a suitable parameter $a$.

To get start, we choose a randome value 0.6 for $a$.


```python
def draw_classify(a,direction=""):
    x = np.linspace(4,7.5,18)
    y = a*x + b
    
    sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_dataset,fit_reg=False,hue="target_class")
    plt.plot(x, y, '-r',)
    
    label="y={0}*x + 2".format(str(a))
    plt.text(6.5,3.8,label,fontsize=15)
    
    if direction == 1:
        direction = r'↑'
    elif direction == -1:
        direction = r'↓'
    else: direction = ""
    
    plt.text(7.5, a*7.5+1.8, direction, fontsize=25, va='bottom')
    
    plt.show()
```


```python
a = 0.6
draw_classify(a,-1)
```


![png](output_21_0.png)


It seems that this classifier is not so good, it doesn't split those two species. All dots are below it. So, we need to move the line down a bit.

We want to see if we can find a repeatable recipe to do this, a series of computer instructions, which computer scientists call an algorithm.

How much should we move down?

step length = 0.4


```python
a = 0.2
draw_classify(a,-1)
```


![png](output_23_0.png)



```python
a = -0.2
draw_classify(a,1)
```


![png](output_24_0.png)


## Data Set
[Iris Data Set](https://archive.ics.uci.edu/ml/datasets/iris)

### Attribute Information:

1. sepal length in cm 
2. sepal width in cm 
3. petal length in cm 
4. petal width in cm 
5. class: 
- Iris Setosa 
- Iris Versicolour 
- Iris Virginica

How can algorithm learns from data? 
Let's see an example. Here are two kinds of iris flowers: Setosa and Versicolour.


```python
iris = datasets.load_iris()
x = pd.DataFrame(iris['data'], columns=iris['feature_names'])
print("target_names: "+str(iris['target_names']))
y = pd.DataFrame(iris['target'], columns=['target'])
iris_data = pd.concat([x,y], axis=1)
iris_data.head(3)
```

    target_names: ['setosa' 'versicolor' 'virginica']





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
      <th>sepal width (cm)</th>
      <th>petal length (cm)</th>
      <th>petal width (cm)</th>
      <th>target</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>3.5</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>3.0</td>
      <td>1.4</td>
      <td>0.2</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>3.2</td>
      <td>1.3</td>
      <td>0.2</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
</div>




```python
iris["target_names"]
```




    array(['setosa', 'versicolor', 'virginica'], dtype='<U10')




```python
target_name = {
    0:'setosa',
    1:'versicolor',
    2:'virginica'
}
```


```python
iris_data['target_name'] = iris_data['target'].map(target_name)
iris_data = iris_data[(iris_data['target_name'] == 'setosa')|(iris_data['target_name'] == 'versicolor')]
iris_data = iris_data[['sepal length (cm)','petal length (cm)','target_name']]
iris_data.head(5)
```




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
      <th>target_name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>5.1</td>
      <td>1.4</td>
      <td>setosa</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4.9</td>
      <td>1.4</td>
      <td>setosa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4.7</td>
      <td>1.3</td>
      <td>setosa</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4.6</td>
      <td>1.5</td>
      <td>setosa</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5.0</td>
      <td>1.4</td>
      <td>setosa</td>
    </tr>
  </tbody>
</table>
</div>




```python
target_class = {
    'setosa':1,
    'versicolor':-1
}
```


```python
iris_data['target_class'] = iris_data['target_name'].map(target_class)
```


```python
del iris_data['target_name']
```


```python
iris_data.head()
```




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




```python
# iris_data.to_csv("iris_data.csv")
```


```python
def sign(z):
    if z > 0:
        return 1
    else:
        return -1
```


```python
import matplotlib.pyplot as plt
import numpy as np
x = np.linspace(-5,5,100)
a = 1
b = 2.5
y = a*x+b
plt.plot(x, y, '-r', label='y=2x+1')
plt.title('Graph of y=2x+1')
plt.xlabel('x', color='#1C2833')
plt.ylabel('y', color='#1C2833')
plt.legend(loc='upper left')
plt.grid()
plt.show()
```


![png](output_37_0.png)



```python
import seaborn as sns
import matplotlib.pyplot as plt

iris = sns.load_dataset("iris")    
grid = sns.JointGrid(iris.petal_length, iris.petal_width, space=0, size=6, ratio=50)
grid.plot_joint(plt.scatter, color="g")
plt.plot([0, 4], [1.5, 0], linewidth=2)
```




    [<matplotlib.lines.Line2D at 0x1a298ffe48>]




![png](output_38_1.png)


## Classify


```python
# iris_data = pd.read_csv("iris_data.csv")
sns.lmplot("sepal length (cm)", "petal length (cm)", data=iris_data,fit_reg=False,hue="target_class")

# x,y = np.concatenate((np.array([1.]), np.array(iris_data.iloc[i])[:2])), np.array(iris_data.iloc[i])[2]
# x_vector = np.linspace(0,x[1])
# y_vector = (x[2]/x[1])*x_vector
# print(x_vector)
# print(y_vector)

# plt.plot(x_vector, y_vector,'b')
plt.show()
```


![png](output_40_0.png)



```python
w = np.array([0.,0.,0.])
error = 1
iterator = 0
while error != 0:
    error = 0
    for i in range(len(iris_data)):
        x,y = np.concatenate((np.array([1.]), np.array(iris_data.iloc[i])[:2])), np.array(iris_data.iloc[i])[2]
        if sign(np.dot(w,x)) != y:
            print("iterator: "+str(iterator))
            iterator += 1
            error += 1
            sns.lmplot('sepal length (cm)','petal length (cm)',data=iris_data, fit_reg=False, hue ='target_class')
            
            # 前一個Decision boundary 的法向量
            if w[1] != 0:
                x_last_decision_boundary = np.linspace(0,w[1])
                y_last_decision_boundary = (w[2]/w[1])*x_last_decision_boundary
                plt.plot(x_last_decision_boundary, y_last_decision_boundary,'c--')
            w += y*x            
            print("x: " + str(x))            
            print("w: " + str(w))
            # x向量 
            x_vector = np.linspace(0,x[1])
            y_vector = (x[2]/x[1])*x_vector
            plt.plot(x_vector, y_vector,'b')
            # Decision boundary 的方向向量
            x_decision_boundary = np.linspace(-0.5,7)
            y_decision_boundary = (-w[1]/w[2])*x_decision_boundary - (w[0]/w[2])
            plt.plot(x_decision_boundary, y_decision_boundary,'r')
            # Decision boundary 的法向量
            x_decision_boundary_normal_vector = np.linspace(0,w[1])
            y_decision_boundary_normal_vector = (w[2]/w[1])*x_decision_boundary_normal_vector
            plt.plot(x_decision_boundary_normal_vector, y_decision_boundary_normal_vector,'g')
            plt.xlim(-0.5,7.5)
            plt.ylim(5,-3)
            plt.show()
```

    iterator: 0
    x: [1.  5.1 1.4]
    w: [1.  5.1 1.4]



![png](output_41_1.png)


    iterator: 1
    x: [1.  7.  4.7]
    w: [ 0.  -1.9 -3.3]



![png](output_41_3.png)


    iterator: 2
    x: [1.  5.1 1.4]
    w: [ 1.   3.2 -1.9]



![png](output_41_5.png)


    iterator: 3
    x: [1.  7.  4.7]
    w: [ 0.  -3.8 -6.6]



![png](output_41_7.png)


    iterator: 4
    x: [1.  5.1 1.4]
    w: [ 1.   1.3 -5.2]



![png](output_41_9.png)


    iterator: 5
    x: [1.  4.6 1.5]
    w: [ 2.   5.9 -3.7]



![png](output_41_11.png)


    iterator: 6
    x: [1.  7.  4.7]
    w: [ 1.  -1.1 -8.4]



![png](output_41_13.png)


    iterator: 7
    x: [1.  5.1 1.4]
    w: [ 2.  4. -7.]



![png](output_41_15.png)


    iterator: 8
    x: [1.  5.7 3.5]
    w: [  1.   -1.7 -10.5]



![png](output_41_17.png)


    iterator: 9
    x: [1.  5.1 1.4]
    w: [ 2.   3.4 -9.1]



![png](output_41_19.png)


## Reference
- [perceptron introduction](https://medium.com/jameslearningnote/資料分析-機器學習-第3-2講-線性分類-感知器-perceptron-介紹-84d8b809f866)
