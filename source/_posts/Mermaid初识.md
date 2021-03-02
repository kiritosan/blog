---
title: Mermaid初识
date: 2021-02-18 10:50:54
tags:
- tools
---

## Mermaid是什么

Mermaid lets you represent diagrams using text and code. This simplifies maintaining complex diagrams. It is a Javascript based diagramming and charting tool that renders Markdown-inspired text definitions to create and modify diagrams dynamically. The main purpose of Mermaid is to help Documentation catch up with Development.

Many editors, wikis and other tools have mermaid integrations already making it easy to start using mermaid. A few of those are described in Simple start to write diagrams.

Mermaid通过使用文本和代码表示图表以简化复杂图的维护。 这是一个基于Javascript的图表绘制工具，支持使用Markdown格式动态创建和修改图表。 Mermaid的主要目的是帮助文档追上开发进程。
许多编辑器，Wiki和其他工具已经具有Mermaid集成功能，可以轻松开始使用Mermaid。其中一些编辑器在“简单开始编写图表”中进行了描述。

## 怎么用

<https://mermaid-js.github.io/mermaid-live-editor>
这是一个在线的Mermaid编辑器可以方便的生成图表，还支持各种格式的导出，打开即用。

## 语法

Mermaid可以生成各种图表，包括流程图、序列图、类图、状态图、实体关系图(E-R图)、用户行为地图、甘特图、饼图。

### 流程图

#### 开头

```bash
graph 方向描述
    图表中的其他语句...
```

流程图方向(Flowchart Orientation)：

TB - 从上到下（Top Bottom）

TD - 从上到下(top-down/ same as top to bottom)

BT - 从下到上

RL - 从右到左

LR - 从左到右

#### 节点

```bash
graph LR
    id
```

| 表述 | 说明 |
|  ----  | ----  |
| id[文字] | 矩形节点 |
| id([文字]) | 圆角矩形节点 |
| id[[文字]] | 子程序形节点 |
| id[(文字)] | 圆柱形节点 |
| id((文字)) | 圆形节点 |
| id>文字] | 右向旗帜状节点 |
| id{文字} | 菱形节点 |
| id{{文字}} | 六边形节点 |
| id[/文字/] | 平行四边形节点 |
| id[\文字\\] | 另一个方向的平行四边形节点 |
| id[/文字\\] | 不规则四边形节点 |
| id[\文字/] | 另一种不规则四边形节点 |

#### 连线

在--的基础上变形，--本身不符合语法

| 表述 | 说明 |
|  ----  | ----  |
| 添加 | |
| > | 箭头 |
| - | 直线 |
| 文字---| 直线间文字 |
| -\|文字\| | 直线间文字另一种语法 |
| >\|文字\| | 箭头间文字 |
|  文字 --> | 箭头键文字另一种语法 |
| 修改 | |
| -.-> | 虚线箭头 |
| -. 文字 .-> | 虚线箭头间文字 |
| ==> | 加粗箭头 |
| == 文字 ==> | 加粗箭头间文字 |

#### 多重连线

 A -- 文字1 --> B -- 文字2 --> C

 a --> b & c--> d

 A & B--> C & D

文本用双引号包裹起来可以预防一些转义的错误

#### 子图表

```bash
subgraph 子图表名称
    子图表中的描述语句...
end
```

一个例子：

```bash
graph TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```

另一个例子：

```bash
graph TB
    c1-->a2
    subgraph ide1 [one]
    a1-->a2
    end
```

#### 交互

```bash
click nodeId callback
click nodeId call callback()
```

callback is the name of a javascript function defined on the page displaying the graph, the function will be called with the nodeId as parameter.

用法：

```bash
<script>
  var callback = function(){
      alert('A callback was triggered');
  }
</script>
```

```bash
graph LR;
    A-->B;
    B-->C;
    C-->D;
    click A callback "Tooltip for a callback"
    click B "http://www.github.com" "This is a tooltip for a link"
    click A call callback() "Tooltip for a callback"
    click B href "http://www.github.com" "This is a tooltip for a link"
```

## 参考

<https://mermaid-js.github.io/mermaid>
<https://mermaid-js.github.io/mermaid/#/flowchart>
<https://blog.csdn.net/fenghuizhidao/article/details/79440583>
