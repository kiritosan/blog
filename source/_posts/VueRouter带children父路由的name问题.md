---
title: VueRouter带children父路由的name问题
date: 2021-11-19 16:38:50
tags:
- vue
- 前端
---

带childern的父路由不能有name属性，有的话开发者工具会提示warning。

当父路由有name属性时，通过to{name:父路由name}的方式访问该路由时，如果该父路由存在默认子路由（children中path为''的路由），则该子路由不会被渲染(通过to=路径的方式不会出现这种问题，但是仍会提示waring)

解决方法是删除父路由的name属性，这样waring提示就会消失。如果还想要通过toname来访问这个路由的话，则应将name属性设置到默认子路由上

假设一个没有name的场景，一个父路由有一个默认子路由和别的子路由。
这时想要通过name访问路由，于是给父路由设置name，想象的是toname访问父路由默认将子路由渲染出来，然而实际情况是没有渲染，开发者工具提示warning，原因是vuerouter没有这样实现。于是为了使用name，采取了将name添加到默认子路由之上的方法，然后通过toname访问这个默认子路由就访问到了父路由的路径（因为父路由的路径和与这个父路由相对应的默认子路由的路径相同）

提示warning的意思指的是当采用to{name}方式访问路由时可能会出现的错误，如果不采用这种方式则不会出现错误。

而为什么出现这种错误可能是因为官方没有好的解决办法或者是故意设置成这种情况。
当父路由有默认子路由时，如果父路由有name那么通过toname方式访问路由则不会渲染默认子组件，然后提示开发者此时默认子路由不会被渲染。