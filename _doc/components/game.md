---
title: Class Game
sections:
  - Constructor
  - players
  - zones
  - Me
  - player
  - Controller
  - zone
  - Trace
  - drones
  - Control
  - UpdateZones
  - SocialDistancing
  - Output
  - StayHome
  - Sort
---

# Constructor
```cpp
game(np, me, nd, nz)
```
<div class="table-responsive">

{: .table .table-bordered}
| np | int | 遊戲總人數 |
| me | int | 自己的 ID |
| nd | int | 玩家的無人機數量 |
| nz | int | 此遊戲的戰區數量 |

</div>

# Member Variables

---

##### players
##### `Iter<Player> players`
Iter of Player
##### 範例
輸出玩家的 ID
```cpp
for(const Player & player : game.players) {
    cerr << "Player #" << player.id << ':' << endl;
}
```

---

##### zones
##### `Iter<Zone> zones`
Iter of Zone
##### 範例
輸入各個 zone 的位置
```cpp
for(Zone & zone : game.zones) {
    cin >> zone; cin.ignore();
}
```

# Member Functions

---
##### Me()
```cpp
Player & Me() const
```
得到自己的 `Player` object
##### 參數
*none*
##### 回傳值型態
Player &

---
##### player()
```cpp
Player & player(int) const
```
透過 ID 得到某個 `Player` object
##### 參數
1. player's ID

##### 回傳值型態
Player &

---
##### Controller()
```cpp
Player & Controller(const Zone &) const
```
查詢某個 zone 的佔領者是誰
##### 參數
1. the Zone object

##### 回傳值型態
Player &

---
##### zone()
```cpp
Zone & zone(int) const
```
透過 ID 得到某個 `Zone` object
##### 參數
1. the zone's ID

##### 回傳值型態
Zone &

---
##### Trace()
```cpp
Zone & Trace(const Drone &) const
```
根據某臺無人機的動向預測他要去哪個 zone
##### 參數
1. the Drone object

##### 回傳值型態
Zone &

##### 說明
根據該無人機前進的方向，找尋夾角最小的 zone，如果沒有 zone 與前進方向夾角小於 90 度，則會回傳最近的 zone

---
##### drones()
```cpp
Iter<Drone> drones(const Player &, const Zone &) const
```
查詢某位玩家在某個 zone 裡的所有無人機
##### 參數
1. the Player object
2. the Zone object

##### 回傳值型態
Iter\<Drone\>

---
##### Control()
```cpp
int Control(const Zone &) const
```
查詢某個 zone 當下最少需要派遣幾架無人機才能佔領
##### 參數
1. the Zone object

##### 回傳值型態
int

---
##### UpdateZones()
```cpp
void UpdateZones()
```
更新每個 zone 的佔領者，注意你需要在遊戲回合中呼叫它，請參考我們的 `main.cpp`
##### 參數
*none*

##### 回傳值型態
*none*

---
##### SocialDistancing()
```cpp
void SocialDistancing() const
```
期間限定功能，讓每臺無人機維持社交距離
##### 參數
*none*

##### 回傳值型態
*none*

---
##### Output()
```cpp
void Output() const
```
輸出自己每臺無人機的目標位置，注意你需要在遊戲回合中呼叫它，請參考我們的 `main.cpp`
##### 參數
*none*

##### 回傳值型態
*none*

---
##### StayHome()
```cpp
void StayHome() const
```
期間限定功能，讓每臺無人機進行居家隔離
##### 參數
*none*

##### 回傳值型態
*none*

---
##### Sort()

```cpp
template<typename T, typename U> static void Sort(Iter<T> &, const U &)
```
根據與給定目標的距離，排序給定的 Iter，給定目標可以是一個 zone 或是一台 drone
##### 參數
1. the Iter object
2. Zone object **or** Drone object

##### 回傳值型態
*none*

```cpp
template<typename T> static void Sort(Iter<T> &, bool (*)(const T &, const T &))
```
根據給定的 compare function，排序給定的 Iter
##### 參數
1. the Iter object
2. a compare function with `bool` type returns

##### 回傳值型態
*none*
