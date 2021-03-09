---
title: C语言小知识
date: 2021-03-04 19:55:51
summary: C语言小知识点（慢慢更新......）
cover: true
categories: 
  - 编程 
tags: 
  - C语言
---

#### 指针降级

对于一个数组，sizeof运算符返回数组元素的个数；但是如果把数组作为参数传入一个函数就会发生指针降级，这时sizeof运算符就会返回一个指针的大小

```c
void fun(int array[]) {
    printf("%d\n",sizeof(array));
}

int main() {
    int array[10];
    printf("%d\n",sizeof(array)); // 输出40
    fun(array); // 输出4
    int *arrayPoint = array;
    printf("%d\n",sizeof(arrayPoint)); // 输出4
    return 0;
}
```

