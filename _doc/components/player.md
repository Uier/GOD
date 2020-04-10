---
title: Class Player
sections:
  - isControl
  - drone
---

# Member Variables

##### drones()
```cpp
Iter<Drone> drones;
```
Iter of Drone
##### Example
輸入 0 號玩家各個 drone 的位置
```cpp
Player p = game.player(0);
for(Drone & drone : p.drones) {
    cin >> drone; cin.ignore();
}
```

# Member Functions

---

##### isControl()
```cpp
bool isControl(const Zone &) const;
```
判斷 Player 是否控制指定的 zone

##### Example
判斷 0 號玩家是否控制 0 號 zone
```cpp
Player p = game.player(0);
Player z = game.zone(0);
bool isControl = p.isContro(z);
```

---

##### drone()
```cpp
Drone & drone(int) const;
```
取得某個 id 的 Drone

##### Example
取得 0 號玩家的 0 號無人機物件
```cpp
Player p = game.player(0);
Drone d = p.drone(0);
```

---

#### Constant
##### id
```cpp
const int id {-1};
```
取得 Player 的 id
##### Example
取得玩家的 id
```cpp
Player p = game.player(0);
int id = p.id;
```


