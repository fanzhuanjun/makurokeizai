# lambda 的用法

bilibili视频: https://www.bilibili.com/video/BV1pW411P7pr?from=search&seid=14781168951522176863

- **匿名函数的用法**

下面两种方式是等价的

```python
lambda x,y: x + y
# 等价
def addnum(x, y):
    return x + y
```



- **函数中的 key 用法**

```python
portfolio = [
    {'name': 'IBM', 'shares': 100, 'price': 91.1},
    {'name': 'AAPL', 'shares': 50, 'price': 543.22},
    {'name': 'FB', 'shares': 200, 'price': 21.09},
    {'name': 'HPQ', 'shares': 35, 'price': 31.75},
    {'name': 'YHOO', 'shares': 45, 'price': 16.35},
    {'name': 'ACME', 'shares': 75, 'price': 115.65}
]
def getPrice(info):
    return info['price']
sort(portfolis, key=getPrice)
# 匿名函数的用法
sort(portfolis, key=lambda x: x['price'])
```



- **复合函数的运用**

创建二次函数：$ax^2+bx+c$ ，并代入 x 值

```python
def quadratic(a, b, c):
    return lambda x: a * x * x + b * x + c

f(-2, 1, 3)(5)
```

扩展运用

```python
import matplotlib.pyplot as plt

def quadratic(a, b, c):
    return lambda x: a * x * x + b * x + c

f = quadratic(-1, 2, 3)
x = [a for a in range(10)]
y = [f(a) for a in range(10)]

plt.plot(x, y);plt.show()
```

<img src="C:\Users\13631\AppData\Roaming\Typora\typora-user-images\Figure_1.png" style="zoom: 67%;" />