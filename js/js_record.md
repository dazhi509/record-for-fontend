#### JavaScript 一些自己用的套路 记

##### 1. log 方法

```
var log = function() {
    console.log.apply(console, arguments)
}
```



##### 2. 选择

```
var e = function(selector) {
    return document.querySelector(selector)
}
```



##### 3. 追加标签

```
var appendHtml = function(element, html) {
	element.insertAdjacentHTML('beforeend', html)
}
```



##### 4. 事件绑定

```
var bindEvent = function(element, eventName, callback) {
    element.addEventListener(eventName, callback)
}
```



##### 5. 判断，移除，增加某一样式

```
var toggleClass = function(element, className) {
    if (element.classList.contains(className)) {
        element.classList.remove(className)
    } else {
        element.classList.add(className)
    }
}
```



##### 6. 清空全部的样式

```
var removeClassAll = function(className) {
    var selector = '.' + className
    var elements = document.querySelectorAll(selector)
    for (var i = 0; i < elements.length; i++) {
        var e = elements[i]
        e.classList.remove(className)
    }
}
```



##### 7. 对含有特定属性的标签同时绑定事件

```
var bindAll = function(selector, eventName, callback) {
    var elements = document.querySelectorAll(selector)
    for(var i = 0; i < elements.length; i++) {
        var e = elements[i]
        bindEvent(e, eventName, callback)
    }
}
```



##### 8. find 函数可以查找 element 的所有子元素

```
var find = function(element, selector) {
    return element.querySelector(selector)
}
```

