---
navicat连接mysql出现2059错误title: markdown时序图
date: 2021-03-04 18:21:59
summary: markdown进阶语法
cover: true
top: true
categories: 
  - 通用
tags: 
  - markdown
---

### 什么是时序图

- 时序图, 又名序列图、循序图、顺序图，是一种UML交互图。
- 它通过描述对象之间发送消息的时间顺序显示多个对象之间的动态协作。
- 它可以表示用例的行为顺序

#### 时序图的作用

- 用来描述接口的功能, 弥补原型图在逻辑细节上的不足

### 语法

<img src="markdownSequence-1.png" alt="一张图看懂时序图语法" style="zoom:50%;" />

### 使用样例

~~~md
```sequence
Andrew->China: Says Hello
Note right of China: China thinks\nabout it
China-->Andrew: How are you?
Andrew->>China: I am good thanks!
```
~~~



