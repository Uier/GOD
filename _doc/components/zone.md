---
title: Class Zone
---

Zone 是繼承 Coord 的類別，其中有

#### Member variable

`x` 是區域的 x 座標

`y` 是區域的 y 座標


#### Member Function

##### *`template<typename U> int operator-(const U &) const;`*
判斷是否距離目標小於等於 100 單位

##### Example
判斷這個 zone 這個物件是否距離 (0, 1) 這個 Drone 小於等於 100 。

```cpp
Zone z = {123, 345};
z.In((Drone){0, 1});
```

##### `template<typename U> int operator-(const U &) const;`

到其他物件 (Zone, Drone) 的距離平方。

##### Example
回傳與座標 (123, 345) 這個無人機的距離平方

```cpp
Zone z = game.zone(0);
Drone d = {123, 345};
int distance = d - z;
```
