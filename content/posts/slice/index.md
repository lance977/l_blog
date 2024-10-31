---
title: Slice
description: 
date: 2022-03-10
# 草稿
draft: true
slug: slice
image: go.png
categories:
    - Go
---

## 数据结构

```go
type slice struct {
    array unsafe.Pointer
    len int
    cap int
}
```

## 扩容规则

### 1.18前
1. 当`原容量 * 2 < 所需的容量`时, 分配一个预估的容量
2. 当`原容量 * 2 >= 所需容量`时
    1. 小于1024时, 翻倍
    2. 大于1024时, 1.25倍

### 1.18后
- `原容量 * 2 < 所需容量`时, 直接按照所需容量扩容
- `原容量 < 256(临界值)`时, 新切片容量变成原来的2倍
- `原容量 > 256`时, 每次容量增加`(旧容量 + 3 * 256) / 4`