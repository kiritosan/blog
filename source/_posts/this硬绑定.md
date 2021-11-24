---
title: this硬绑定
date: 2021-11-24 13:46:33
tags:
- js
---
## this

```javascript
function foo() {
	console.log( this.a );
}

var obj = {
	a: 2
};

var bar = function() {
	foo.call( obj );
};

bar(); // 2
setTimeout( bar, 100 ); // 2

// `bar` hard binds `foo`'s `this` to `obj`
// so that it cannot be overriden
bar.call( window ); // 2
```

包装函数bar可能被任何人调用(使得bar的this指向任何人)，但其被调用时强制使其内部函数foo被obj调用（使得foo的this一直指向obj）