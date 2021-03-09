---
title: 使用python从c代码文件中读取一个函数
date: 2021-02-04 19:55:51
summary: 通过正则匹配从c代码文件中读取一个函数，python实现
cover: true
categories: 
  - 编程 
tags: 
  - Python
---

读取C文件中函数，可能存在多种字符集的情况，需要多次尝试

```python
file_path = "test_file_name.c"
fun_name = "test_function"

rule = r'\w+\**? \**?' + fun_name + '\(.*?\).*?\n\{.*?\n\}'
charsets = ["GBK", "UTF-8", "BIG5", "ASCII"]
for charset in charsets:
    try:
        with open(file_path, 'r', encoding=charset) as f:
            data = f.read()
        break
    except Exception as e:
        print(str(e))
temp_str = re.findall(rule, data, re.DOTALL)
for temp in temp_str:
    print(temp)
```

