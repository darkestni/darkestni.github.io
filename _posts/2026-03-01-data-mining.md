---
title: 数据挖掘
date: 2026-03-01 00:00:00 +0800
categories: [数据挖掘]
tags: [课程笔记, Python]
description: 数据挖掘课程学习笔记和资料
---

## 课程简介

数据挖掘是从大量数据中提取有价值信息的过程。本课程涵盖 Python 基础、数据处理、机器学习等内容。

## 实验资料

- [Lab 1](/assets/数据挖掘/Lab1.pdf)
- [Lab1.ipynb](/assets/数据挖掘/Lab1.ipynb)

---

## Lab 1: Python 基础练习

### 1. 计算奇数和偶数的和

计算从 1 到 100 的所有奇数和偶数的和。

```python
# 方法一：使用循环
odd_sum = 0
even_sum = 0

for i in range(1, 101):
    if i % 2 == 0:
        even_sum += i
    else:
        odd_sum += i

print(f"1 到 100 的偶数和为：{even_sum}")  # 2550
print(f"1 到 100 的奇数和为：{odd_sum}")   # 2500
```

```python
# 方法二：使用列表推导式
odd_sum = sum(i for i in range(1, 101) if i % 2 != 0)
even_sum = sum(i for i in range(1, 101) if i % 2 == 0)
```

### 2. 合并重叠区间

实现一个函数，输入一组区间，合并所有重叠的区间。

```python
def merge_intervals(intervals):
    if not intervals:
        return []

    # 按区间起始位置排序
    intervals.sort(key=lambda x: x[0])

    merged = [intervals[0]]

    for current in intervals[1:]:
        last = merged[-1]

        # 如果有重叠，合并区间
        if current[0] <= last[1]:
            last[1] = max(last[1], current[1])
        else:
            merged.append(current)

    return merged

# 测试
intervals = [[1,3],[2,6],[8,10],[15,18]]
print(merge_intervals(intervals))  # [[1, 6], [8, 10], [15, 18]]
```

### 3. 文件读写操作

#### TXT 文件读写

```python
# 写入 TXT 文件
with open('sample.txt', 'w', encoding='utf-8') as f:
    f.write('第一行内容\n')
    f.write('第二行内容\n')

# 读取 TXT 文件
with open('sample.txt', 'r', encoding='utf-8') as f:
    content = f.read()
    print(content)

# 逐行读取
with open('sample.txt', 'r', encoding='utf-8') as f:
    for line in f:
        print(line.strip())
```

#### CSV 文件读写

```python
import csv

# 写入 CSV 文件
with open('sample.csv', 'w', encoding='utf-8', newline='') as f:
    writer = csv.writer(f)
    writer.writerow(['姓名', '年龄', '城市'])
    writer.writerow(['张三', 20, '北京'])

# 使用 DictWriter（更直观）
with open('sample_dict.csv', 'w', encoding='utf-8', newline='') as f:
    fieldnames = ['姓名', '年龄', '城市']
    writer = csv.DictWriter(f, fieldnames=fieldnames)
    writer.writeheader()
    writer.writerow({'姓名': '张三', '年龄': 20, '城市': '北京'})

# 读取 CSV 文件
with open('sample.csv', 'r', encoding='utf-8') as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(dict(row))
```

---

## 重点知识点

| 知识点 | 说明 |
|--------|------|
| `range(start, end)` | 生成从 start 到 end-1 的序列 |
| 列表推导式 | `[x for x in iter if condition]` |
| `lambda` 匿名函数 | `lambda x: x[0]` 返回第一个元素 |
| `with open()` | 自动管理文件资源，无需手动关闭 |
| `csv.DictReader/Writer` | 以字典方式读写 CSV，更直观 |

## 待补充

- [ ] Lab 2 笔记
- [ ] 数据预处理方法
- [ ] 常用数据挖掘算法
