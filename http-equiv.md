# http-equiv
```html
expires 设置 过期时间 一旦过期必须重新获取数据
content: 0 or ...
<meta http-equiv="expires" content="Wed, 20 Jun 2007 22:33:00 GMT">

```
```html
Pragma(cache模式)  类似 cache-control
用于设定禁止浏览器从本地机的缓存中调阅页面内容，设定后一旦离开网页就无法从Cache中再调出 
content: no-cache
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="cache-control" content="no-cache">

```
```html
刷新 
指定时间，刷新指定页面 
content: time[s]; url[url]
<meta http-equiv="Refresh" content="2;URL=http://www.net.cn/">

```
```html
Set-Cookie(cookie设定) 
如果网页过期，那么存盘的cookie将被删除。 
content: ---
<meta http-equiv="Set-Cookie" content="cookievalue=xxx;expires=Wednesday, 20-Jun-2007 22:33:00 GMT; path=/">

```
```html
Window-target(显示窗口的设定) 
强制页面在当前窗口以独立页面显示。 
content: ---
<meta http-equiv="Window-target" content="_top">

```
```html
content-Type(显示字符集的设定)  
设定页面使用的字符集。  
content: ---
<meta http-equiv="content-Type" content="text/html; charset=gb2312">

```
```html
x-ua-compatible 
设定页面渲染方式 默认只有 ie8识别，所以针对 ie8
content: ie[ie]
<meta http-equiv="x-ua-compatible" content="ie=edge">

```
