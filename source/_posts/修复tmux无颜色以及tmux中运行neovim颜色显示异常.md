---
title: 修复tmux无颜色以及tmux中运行neovim颜色显示异常
date: 2022-05-16 20:03:37
tags:
---

1. tmux从2.2版本开始才支持想要的彩色效果

cenos7升级tmux2.8：https://gist.github.com/pokev25/4b9516d32f4021d945a140df09bf1fde/

如果升级后运行tmux提示protocol version mismatch (client 8, server 7)，可能是因为旧的tmux程序还在内存中运行。
通过pgrep tmux找到正在运行的tmux的进程id，运行```/proc/12345/exe ls```可以查看该进行，运行kill结束进程
https://www.reddit.com/r/tmux/comments/rr63kc/protocol_version_mismatch_client_7_server_8/

2. 让彩色正常显示
https://github.com/arcticicestudio/nord-tmux/issues/15
https://github.com/arcticicestudio/nord-vim/issues/72

运行2.8版本tmux tmux info | grep Tc

设置配置文件在~/.tmux.conf

写入如下配置（使用上面链接说的xterm-256color不能正常显示颜色）

```conf
set -g default-terminal "screen-256color"
set-option -ga terminal-overrides ",screen-256color:Tc"
```

之后显示正常

注意：不用像stackoverflow上面搜到的答案那样更改.zshrc文件

color设置（putty vim screen tmux）
https://gist.github.com/limingjie/4975c36d13d0927613e6