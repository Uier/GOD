---
title: Class Drone
---

# Member Variables

`x` 是無人機的 x 座標

`y` 是無人機的 y 座標

# Member Functions

##### `template<typename U> int operator-(const U &) const;`

判斷是否距離目標小於等於 100 單位

##### Example
判斷這個 drone 這個物件是否距離 (0, 1) 這個 Zone 小於等於 100 。

```cpp
Drone d = {123, 345};
d.In((Zone){0, 1});
```


##### `template<typename U> int operator-(const U &) const;`

到其他物件 (Zone, Drone) 的距離平方。

##### Example
回傳與 Drone d 的距離平方

```cpp
Drone d = {123, 345};
int distance = d - (Zone)(11, 26);
```

# Non-member Functions

##### *`istream & operator>>(ostream &, const Game &);`*
運算子重載用於 cin ，輸入座標 x, y

##### *`istream & operator>>(ostream &, const Game &);`*
運算子重載用於 cout, cerr ，輸出座標 x, y
