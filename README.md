# [pyecharts](https://github.com/chenjiandongx/pyecharts) [![Build Status](https://travis-ci.org/pyecharts/pyecharts.svg?branch=master)](https://travis-ci.org/pyecharts/pyecharts) [![codecov](https://codecov.io/gh/pyecharts/pyecharts/branch/master/graph/badge.svg)](https://codecov.io/gh/pyecharts/pyecharts) [![PyPI version](https://badge.fury.io/py/pyecharts.svg)](https://badge.fury.io/py/pyecharts) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

### 简介

pyecharts 是 [Echarts](https://github.com/ecomfe/echarts) 在 Python 的封装，pyecharts 提供了一系列接口用于生成 Echarts 的图表。Echarts 是一个百度开源的可视化 JS 库，用其作出来的图效果很赞，所以我就想看看有没有 Python 对应的接口，但发现没有令我满意的，所以就动手造了 pyecharts 这个轮子。

### 安装

pyecharts 完全兼容 Python2 和 Python3

**Jupyter-Notebook**

pyecharts 支持在 Notebook 中渲染出图形，但首先请确保您已经安装了 Notebook 环境。下面是 Notebook 的安装方式。

```shell
$ pip install notebook
```

**pyecharts**

你可以通过 pip 安装 pyecharts

```shell
pip install pyecharts
```

或者通过源码安装（请使用 ----recursive 参数）

```shell
$ git clone --recursive https://github.com/pyecharts/pyecharts.git
$ cd pyecharts
$ pip install -r requirements.txt
$ python setup.py install
```

### 基本用法

#### 本地环境

```python
from pyecharts import Bar

attr = [
    "Jan", "Feb", "Mar", "Apr", "May", "Jun", 
    "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"]
v1 = [
    2.0, 4.9, 7.0, 23.2, 25.6, 76.7, 
    135.6, 162.2, 32.6, 20.0, 6.4, 3.3]
v2 = [
    2.6, 5.9, 9.0, 26.4, 28.7, 70.7,
    175.6, 182.2, 48.7, 18.8, 6.0, 2.3]
bar = Bar("Bar chart", "precipitation and evaporation one year")
bar.add("precipitation", attr, v1,
        mark_line=["average"], mark_point=["max", "min"])
bar.add("evaporation", attr, v2,
        mark_line=["average"], mark_point=["max", "min"])
bar.render()
```

render() 方法将会在本地生成一个 render.html 的文件，使用浏览器打开即可看到效果！

![usage-0](https://user-images.githubusercontent.com/19553554/35314229-be3ee1d2-00ff-11e8-880e-8dea5bcd29ae.gif)

#### Notebook 环境

可与 Pandas/Numpy 等第三方库协作！ 

![pandas-numpy](https://user-images.githubusercontent.com/19553554/35104252-3e36cee2-fca3-11e7-8e43-09bbe8dbbd1e.png)

#### Web 环境

**pyecharts+Flask**

![flask-0](https://user-images.githubusercontent.com/19553554/35081158-3faa7c34-fc4d-11e7-80c9-2de79371374f.gif)

**pyecharts+Django**

![django-0](https://user-images.githubusercontent.com/19553554/35081440-21efcf58-fc4f-11e7-8427-ed73306533e8.gif)

### 文档

* [中文文档](http://127.0.0.1:3000/#/zh-cn/)
* [English](http://127.0.0.1:3000/#/en-us/)

### 测试

```shell
$ cd test
$ nosetests --with-coverage --cover-package pyecharts --cover-package test

在 Linux/macOS 系统下可使用
$ make
```

### 开发团队

[![chenjiandongx](https://user-images.githubusercontent.com/19553554/35314407-c7f538ce-0100-11e8-8943-5b4dc8ec8e35.png)](https://github.com/chenjiandongx)  [![chfw](https://user-images.githubusercontent.com/19553554/35314405-c5618c5c-0100-11e8-99b0-93f6b38f8717.png)](https://github.com/chfw)  [![kinegratii](https://user-images.githubusercontent.com/19553554/35314406-c6c1d69c-0100-11e8-89d3-df66688f44b2.png)](https://github.com/kinegratii)


### LICENSE 

[MIT](https://github.com/pyecharts/pyecharts/blob/master/LICENSE)
