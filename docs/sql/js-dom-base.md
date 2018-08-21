# dom-base

## query dom

1. document.getElementById('id')
2. document.querySelect()
3. document.querySelectAll(), return _list_
4. document.getElementByTagName('div'),  return _list_
5. document.getElementsByClassName(name), return _list_

```javascript
// querySelect 查询满足第一个dom 节点
document.querySelect('#id')
document.querySelect('.id')
document.querySelect('div')
```

## element 元素属性问题

```javascript
//控制台打印element 对象
console.dir(ele)
// data-* 属性对象
ele.dataset.name 
// css 
ele.className
ele.classList
// style
ele.style.color
ele.style.fontSize
//得到element 的计算属性
ele.getBoundingClientReact()

// input 输入框 pattern 与 required 的属性

```





## 严格模式 use strict

严格模式主要有以下限制： 

1. 变量必须声明后再使用 
2. 函数的参数不能有同名属性，否则报错 
3. 不能使用with语句 
4. 不能对只读属性赋值，否则报错 
5. 不能使用前缀 0 表示八进制数，否则报错 
6. 不能删除不可删除的属性，否则报错 
7. 不能删除变量delete prop，会报错，只能删除属性delete global[prop] 
8. eval不会在它的外层作用域引入变量 
9. eval和arguments不能被重新赋值 
10. arguments不会自动反映函数参数的变化 
11. 不能使用arguments.callee 
12. 不能使用arguments.caller 
13. 禁止this指向全局对象 
14. 不能使用fn.caller和fn.arguments获取函数调用的堆栈 
15. 增加了保留字（比如protected、static和interface）

设立”严格模式”的目的，主要有以下几个：

1. 消除Javascript语法的一些不合理、不严谨之处，减少一些怪异行为; 
2. 消除代码运行的一些不安全之处，保证代码运行的安全； 
3. 提高编译器效率，增加运行速度； 
4. 为未来新版本的Javascript做好铺垫。
