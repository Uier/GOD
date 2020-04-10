---
title: Class Iter
sections:
  - size
  - operator[]
  - begin/end
---

```cpp
template <typename T> class Iter;
```

> A Random-Access-Iterator template for double pointer

`Iter` 是我們類別庫中特色的容器，我們用 Iter 來儲存多個 Drones, Zones, Players, ...
Iter 除了可以像陣列一般使用 for loop 遍歷，我們也提供排序 Iter 的方法，在許多函式中我們會用 Iter 作為參數作為傳遞多個物件的方法，他有以下幾個 Member types，不感興趣的可以跳過。

# Member types

---
<div class="table-responsive">

{: .table .table-bordered}
| difference_type | size_t |
| value_type | T |
| reference | T & |
| pointer | T * |
| pointer | T * |
| iterator_category | std::random_access_iteratoe_tag |

</div>

# Member Functions
---

##### size()
```cpp
difference_type size() const
```
回傳 Iter 內的元素數量
##### 參數
*none*
##### 回傳值型態
difference_type，
##### 範例
假設 drones 是一個 Iter of Drone
```cpp
drones[0] = (Drone){123, 456};
```

---

##### operator[]
```cpp
reference operator[](difference_type) const;
```
您可以使用中括號存取 Iter 中的資料

---

##### begin() end()
```cpp
Iter begin() const
Iter end() const
```
您可以使用 begin() 和 end() 作為排序的參數
