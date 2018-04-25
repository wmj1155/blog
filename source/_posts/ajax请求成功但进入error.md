---
title: ajax请求成功但进入error
date: 2017-08-08 09:15:08
tags:
---

又是一个老生常谈的问题啦，ajax老爷大大~

### 问题

在用jq的ajax请求后端接口时数据有返回，但是却进入了error是咋回事呢？

先来看一个正常的请求格式:

```$.ajax({
$.ajax({
url:'',
timeout:12000,
dataType:'json',
success:function(data){
  console.log(data);
},
error:function(e){
  console.log(e);
}
});
```

​     上面的代码块就是我们通常用ajax请求接口的写法，当存在跨域并且后端支持跨域时把dataType写成'jsonp'就可以了。

​      但是有时候你会发现请求状态是200，但还是进入了error,这个时候就需要查看并确认后台的回调函数是否为默认的callback函数名，如果不是就需要在加入一个自定义回调函数名的参数，jsonp:'重写回调函数的名字'

