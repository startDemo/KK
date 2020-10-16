# DOM 开篇

## 1. javascript-DOM 开篇
### 什么是 window ？
  - window: 是一个全局对象，代表浏览器中一个打开的窗口，每一个窗口就是一个window对象
### 什么是 document ？
  - document 是 window 对象的一个属性，这个属性是一个对象。
  - document 代表当前窗口中的整个网页。
  - document 对象保存了网页上的所有内容，通过 document 对象可以操作网页上的内容
### 什么是 DOM
  - DOM 定义了访问和操作 HTML 文档的标准方法
  - DOM 全称为 document object model，文档对象模型
  - 学习 DOM 就是学习如何通过 document 操作网页

## 2. javascript 操作 DOM 元素
### 获取 DOM 元素
  - 通过 id 找指定元素 --> document.getElementById("IDName")
    - id 是唯一的，所以获取到的是一个对象，找不到时返回 Null
    - 返回的这个对象是宿主类型对象(浏览器提供的对象)
  
  - 通过 class 类名获取指定元素  --> document.getElementsByClassName("clsName")
    - 由于 class 可以重复，所以获取到的是一个存着匹配元素的数组，当找不到时返回空数组
  
  - 通过 name 获取指定元素  --> document.getElementsByName("name")
    - 由于 name 可以重复，所以找到了则返回数组，找不到就返回一个空数组
    - getElementsByName 在 IE9- 和 Opera 中，还会返回 id 为指定名称的元素
  
  - 通过标签名称获取指定元素 --> document.getElementsByTagName("eleName")
    - 页面有很多的标签，所以找到时会返回存放匹配元素的数组，找不到返回空数组

  - 通过选择器获取单个指定元素  --> document.querySelector("选择器")
    - 只会返回匹配目标的第一个元素

  - 通过选择器获取多个指定元素  --> document.querySelectorAll("选择器")
    - 返回所有匹配结果存入数组

  - 找到获取元素的所有子元素
    - children 属性获取到指定元素中所有的子元素
    - childNodes 属性获取到指定元素中所有的子节点
  - 获取指定节点中的第一个子元素/子节点
    - firstChild 获取指定元素的第一个子节点
    - firstElementChild 获取指定元素的第一个子元素
  - 获取指定节点中的最后一个子元素/子节点
    - lastChild 获取指定元素的最后一个子节点
    - lastElementChild 获取指定元素的最后一个子元素

