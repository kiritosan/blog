---
title: 执行git push到GitHub时提示waring
date: 2021-05-08 19:35:51
tags:
- GitHub
---
## 解决

```bash
# 执行 git push 但没有指定分支，将 push 所有本地的分支到远程仓库中对应匹配的分支
git config --global push.default matching
```

simple指的是执行 git push 没有指定分支时，只有当前分支会被 push 到使用 git pull 获取的代码。

## 链接

https://blog.csdn.net/jrainbow/article/details/19338525