---
title: onpopstate 以及历史栈
date: 2022-04-04 19:49:07
tags:
---
每跳转到一个新的页面，这个页面的链接会放到栈里
执行replaceState()方法到的页面会替换栈中顶层的链接
history.length显示栈内的链接数量
history.onpopstate事件:当点击浏览器的前进后退或执行history.go history.forward history.back会触发

document.location.pathname显示当前路径(不显示origin)
document.location.hash显示当前锚点