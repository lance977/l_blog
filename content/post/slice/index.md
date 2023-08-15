---
title: Slice
description: 
date: 2022-03-10
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


### 1.18后