# jupyter学习
Jupyter Notebook 是一个交互式笔记本，支持运行 40 多种编程语言，目前只分享python和js做一些简单的页面。
## python做图表
你可以使用bokeh来画图，[学习bokeh](https://e271828182.github.io/BokehStudy/)里面简单介绍了如何使用bokeh画图的步骤，以及ipywidgets来实现交互和布局
做表格则更加简单，用[pandas](https://pandas.pydata.org/pandas-docs/stable/style.html)的方法就可以实现

## js做图表
js画图就有百度的[echarts](http://echarts.baidu.com/)，蚂蚁金服[antv](https://antv.alipay.com/zh-cn/index.html)和[antd](https://ant.design/index-cn)

### echarts
首先可以阅读官网教程 [5 分钟上手 ECharts](http://echarts.baidu.com/tutorial.html#5%20%E5%88%86%E9%92%9F%E4%B8%8A%E6%89%8B%20ECharts)
1. 引入echarts
2. 定义容器
3. 初始化echarts
4. 定义option([移动端自适应](http://echarts.baidu.com/tutorial.html#%E7%A7%BB%E5%8A%A8%E7%AB%AF%E8%87%AA%E9%80%82%E5%BA%94))
5. 设置option
6. 注册事件([ECharts 中的事件和行为](http://echarts.baidu.com/tutorial.html#ECharts%20%E4%B8%AD%E7%9A%84%E4%BA%8B%E4%BB%B6%E5%92%8C%E8%A1%8C%E4%B8%BA))
官网的案例提供了option,了解以上步骤后就可以开始使用案例和api开发。

### antv
[antv](https://antv.alipay.com/zh-cn/index.html)是蚂蚁金服研发的画图js框架，分为G2、G6和F2三个板块，G2与echart类似，画图步骤也类似。G6是关系图，F2针对移动端

### antd
以上的框架主要都是画图，而[antd](https://ant.design/index-cn)则是基于React的js框架，处理ui的能力与bootstrap类似，此外，它还可以较好的处理table。
官网的例子都是基于TypeScript（微软的开发的JavaScript的一个超集），可以编译成javascript后再使用。同时，官网只介绍了利用webpack和nodejs来构建项目，门槛比较高，这里介绍只用引入标签就可以开始开发的低级用法。
```html
<script type="text/javascript" src="react.min.js"></script>
<script type="text/javascript" src="react-dom.min.js"></script>
<script src='moment.min.js'></script>
<script src='antd-with-locales.min.js'></script>
```
## 优劣总结
bokeh和ipywidgets画图比较快捷，ipywidgets可以调用python代码，执行sql和pandas来处理数据。但是ui不好控制，bokeh只支持谷歌地图，ipywidgets控件数量少，不稳定。且在远程调用执行后，不能直接生成控件，而是必须每次页面初始化生成，导致页面开启速度慢。
js画图更加漂亮，可以结合百度地图，但是静态页面生成后，不能再请求调用服务端，只能一次将数据塞进页面，导致数据交互处理比较麻烦。

## 小技巧
1. ipywidgets导致页面开启慢，可能导致无法截图，可以设置两个页面，用于截图的页面不使用初始化页面的功能。
2. 用js开发静态页面时，利用python取出数据并包装，jsonp的方式请求数据，以便于编辑html页面

