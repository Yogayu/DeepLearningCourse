Classification

Let's play a game. Suppose you have a stick and you need to separate the beetles from the butterflies on the ground.
Pictures

What if you can't see it, but you can have another frind. He or she can tell you, wether you are doing right or wrong. And they will tell you which item you make mistakes.

Instruction

You can't see it with visual image, you can only see it with data.

You want to teach a computer a computer. While they do not know what go right a little means, they can only perform specific instructions, like translate 12cm to the right.

So, we build a coordinate system.

Pictures

 y = Ax + B
 
 
 
 
 
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

class Perceptron(object):
    def __init__(self, eta=0.01, n_iter=10):
        self.eta = eta
        self.n_iter = n_iter

    def fit(self, X, y):
        self.w_ = np.zeros(1 + X.shape[1])
        self.errors_ = []

        for _ in range(self.n_iter):
            errors = 0
            for xi, target in zip(X, y):
                update = self.eta * (target - self.predict(xi))
                self.w_[1:] += update * xi
                self.w_[0] += update
                errors += int(update != 0.0)
            self.errors_.append(errors)
        return self

    def net_input(self, X):
        """Calculate net input"""
        return np.dot(X, self.w_[1:]) + self.w_[0]

    def predict(self, X):
        """Return class label after unit step"""
        return np.where(self.net_input(X) >= 0.0, 1, -1)


df = pd.read_csv('iris.csv', header=None)
print(df.tail())
y = df.iloc[0:100, 4].values
#print(y)

y = np.where(y == 'Iris-setosa', -1, 1)
#print(y)

X = df.iloc[0:100,[0,2]].values
print(X)

plt.scatter(X[:50, 0], X[:50,1], label='setosa', color='red', marker='o')
plt.scatter(X[50:100,0], X[50:100, 1], label='versicolor', color='blue',marker='x')
plt.xlabel('petal length')
plt.ylabel('sepal length')
plt.legend()
plt.show()

ppn = Perceptron(0.1, 10)
ppn.fit(X,y)
plt.plot(range(1,len(ppn.errors_)+1), ppn.errors_, marker='o')
plt.xlabel('epoch')
plt.ylabel('Number of misclassification')
plt.show()


---

Iris也称鸢尾花卉数据集，是一类多重变量分析的数据集。数据集包含150个数据集，分为3类，每类50个数据，每个数据包含4个属性。
可通过花萼长度，花萼宽度，花瓣长度，花瓣宽度4个属性预测鸢尾花卉属于（Setosa，Versicolour，Virginica）三个种类中的哪一类。


```
import matplotlib.pyplot as plt

fig, ax = plt.subplots()

ax.plot([1, 2, 3], label=r'$up$')
ax.legend()

ax.set_xlabel(r'$\Delta_i^j$', fontsize=20)
ax.set_ylabel(r'$\Delta_{i+1}^j$', fontsize=20)
ax.set_title(r'$\Delta_i^j \hspace{0.4} \mathrm{versus} \hspace{0.4} '
             r'\Delta_{i+1}^j$', fontsize=20)

tex = r'$\mathcal{R}\prod_{i=\alpha_{i+1}}^\infty a_i\sin(2 \pi f x_i)$'
ax.text(1, 1.6, tex, fontsize=20, va='bottom')

fig.tight_layout()
plt.show()
```

↑