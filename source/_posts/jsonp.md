---
title: jsonp
date: 2022-03-26 10:44:28
tags:
---
```script

function jsonp(url, param, cb) {
    // 构造query
    let query = url.indexOf('?') === -1 ? '?' : '&'

    for (let key of Object.keys(param)) {
         query += key + '=' + param[key] + '&'
    }
    // 随机回调函数名
    let random = Math.random().toString().replace('.', '')
    let cbname = 'cb' + random

    query += 'callback=' + cbname

    let script = document.createElement('script')
    script.setAttribute("type", "text/javascript");
    script.src = url + query
    
    window[cbname] = (params) => {
        cb(params)
        document.removeChild(script)
    }
    
    // 后添加 因为一经添加立马请求
    document.body.appendChild(script)
}

let url = 'https://XXXXXXX'
jsonp(url, {}, (val)=>{console.log(val)})
```

```javascript

const jsonp = ({ url, params, callbackName }) => {
  const generateURL = () => {
    let dataStr = '';
    for(let key in params) {
      dataStr += `${key}=${params[key]}&`;
    }
    dataStr += `callback=${callbackName}`;
    return `${url}?${dataStr}`;
  };
  return new Promise((resolve, reject) => {
    // 初始化回调函数名称
    callbackName = callbackName || Math.random().toString.replace(',', ''); 
    // 创建 script 元素并加入到当前文档中
    let scriptEle = document.createElement('script');
    scriptEle.src = generateURL();
    document.body.appendChild(scriptEle);
    // 绑定到 window 上，为了后面调用
    window[callbackName] = (data) => {
      resolve(data);
      // script 执行完了，成为无用元素，需要清除
      document.body.removeChild(scriptEle);
    }
  });
}

```

## ref

https://juejin.cn/post/6844904100035821575
https://www.cnblogs.com/zzc5464/p/jsonp.html
