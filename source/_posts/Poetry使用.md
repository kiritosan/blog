---
title: Poetry使用
date: 2021-04-24 03:47:31
tags:
- python
---
## 配置poetry安装源

在pyproject.toml里添加如下内容：

```bash
[[tool.poetry.source]]
name = "tsinghua"
default = true
url = "https://pypi.tuna.tsinghua.edu.cn/simple"
```

参考：

https://www.cnblogs.com/zhenzi0322/p/14188895.html#%E9%85%8D%E7%BD%AEpoetry%E5%AE%89%E8%A3%85%E6%BA%90

https://zhuanlan.zhihu.com/p/110721747

https://www.pythonf.cn/read/137815