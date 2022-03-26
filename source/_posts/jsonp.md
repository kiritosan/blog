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

## ref

https://www.cnblogs.com/zzc5464/p/jsonp.html