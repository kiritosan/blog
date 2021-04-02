---
title: Intro to Machine Learning
date: 2021-04-02 03:06:04
tags:
- 机器学习
---
## 机器学习入门

[链接](https://www.kaggle.com/learn/intro-to-machine-learning)

## 从房价预测开始

### 决策树

简单的决策树

![决策树](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/%E5%86%B3%E7%AD%96%E6%A0%91.png)

深层决策树

![深层的(Deep)决策树](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/%E6%B7%B1%E5%B1%82%E7%9A%84(Deep)%E5%86%B3%E7%AD%96%E6%A0%91.png)

### 使用pandas处理数据

X.describe()

X.head()

### 使用现成的库进行数据训练

```python
from sklearn.tree import DecisionTreeRegressor

# Define model. Specify a number for random_state to ensure same results each run
melbourne_model = DecisionTreeRegressor(random_state=1)

# Fit model
melbourne_model.fit(X, y)
```

### Model Validation

在进行机器学习的时候，不能犯使用数据集进行训练后再用之前进行训练的数据集中的数据进行检验的错误。

为了判别机器学习的效果，需要设定一个指标。

衡量机器学习效果的指标有很多，先从Mean Absolute Error (also called MAE)入手。

学习MAE，先从error入手，error=actual−predicted

平均绝对误差为error绝对值的平均值。

### 计算MAE的例子

```python
# Data Loading Code Hidden Here
import pandas as pd

# Load data
melbourne_file_path = '../input/melbourne-housing-snapshot/melb_data.csv'
melbourne_data = pd.read_csv(melbourne_file_path) 
# Filter rows with missing price values
filtered_melbourne_data = melbourne_data.dropna(axis=0)
# Choose target and features
y = filtered_melbourne_data.Price
melbourne_features = ['Rooms', 'Bathroom', 'Landsize', 'BuildingArea', 
                        'YearBuilt', 'Lattitude', 'Longtitude']
X = filtered_melbourne_data[melbourne_features]

from sklearn.tree import DecisionTreeRegressor
# Define model
melbourne_model = DecisionTreeRegressor()
# Fit model
melbourne_model.fit(X, y)
```

```python
// 重点： 调用MAE
from sklearn.metrics import mean_absolute_error

predicted_home_prices = melbourne_model.predict(X)
mean_absolute_error(y, predicted_home_prices)
```

由此，错误就发生了。

这里就犯了开头提到的错误，用来预测的数据又用来做了检验。

这个错误叫做"In-Sample" Scores。

> Imagine that, in the large real estate market, door color is unrelated to home price.

> However, in the sample of data you used to build the model, all homes with green doors were very expensive. The model's job is to find patterns that predict home prices, so it will see this pattern, and it will always predict high prices for homes with green doors.

##  scikit-learn的train_test_split函数

scikit-learn自带train_test_split函数从而将数据分成训练集和测试集两部分

示例代码：

```python
from sklearn.model_selection import train_test_split

# split data into training and validation data, for both features and target
# The split is based on a random number generator. Supplying a numeric value to
# the random_state argument guarantees we get the same split every time we
# run this script.
train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)
# Define model
melbourne_model = DecisionTreeRegressor()
# Fit model
melbourne_model.fit(train_X, train_y)

# get predicted prices on validation data
val_predictions = melbourne_model.predict(val_X)
print(mean_absolute_error(val_y, val_predictions))
```

### 欠拟合和过拟合

![欠拟合和过拟合](https://cdn.jsdelivr.net/gh/kiritosan/pic@master/img/underfitting%20and%20overfitting.png)

示例代码

```python
from sklearn.metrics import mean_absolute_error
from sklearn.tree import DecisionTreeRegressor

def get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y):
// 重点：这里在生成决策树模型的时候加入了max_leaf_nodes和radom_state参数
    model = DecisionTreeRegressor(max_leaf_nodes=max_leaf_nodes, random_state=0)
    model.fit(train_X, train_y)
    preds_val = model.predict(val_X)
    mae = mean_absolute_error(val_y, preds_val)
    return(mae)
```

数据集为之前经过分割的数据

使用for循环比较不同深度的预测结果的MAE

一般来说，max_leaf_nodes数值越大，深度越深，决策树的树叶就越多，房子被分的组就越多，就越容易发生过拟合。

```python
# compare MAE with differing values of max_leaf_nodes
for max_leaf_nodes in [5, 50, 500, 5000]:
    my_mae = get_mae(max_leaf_nodes, train_X, val_X, train_y, val_y)
    print("Max leaf nodes: %d  \t\t Mean Absolute Error:  %d" %(max_leaf_nodes, my_mae))
```

| 叶节点              | 平均绝对误差            |
| ---------------------- | ----------------------------- |
| Max leaf nodes: 5      |  Mean Absolute Error:  347380 |
| Max leaf nodes: 50     |  Mean Absolute Error:  258171 |
| Max leaf nodes: 500    |  Mean Absolute Error:  243495 |
| Max leaf nodes: 5000   |  Mean Absolute Error:  254983 |







## 代码中random_state的作用

通过设置random_state为一个特定的数值，可以保证下次运行同样的代码时，会出现同样的结果。

如果不设置的话，随着时间的改变，随机种子也会改变，结果也会变得不定。

参考:

[random_state](https://www.jianshu.com/p/4deb2cb2502f)