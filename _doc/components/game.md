---
title: Class Game
sections:
  - Constructor
  - Member Variables
  - Member Functions
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

##### `Iter<Player> players`
iterator of players
##### Example
輸出玩家的 ID
```cpp
for(const Player & player : game.players) {
	cerr << "Player #" << player.id << ':' << endl;
}
```

---

##### `Iter<Zone> zones`
iterator of zones
##### Example
輸入各個 zone 的位置
```cpp
for(Zone & zone : game.zones) {
    cin >> zone; cin.ignore();
}
```

# Member Functions

---

```cpp
Player & Me() const
```
得到自己的 `player` object.
##### Parameters
*none*
##### Return type
Player &

---

```cpp
Player & player(int) const
```
透過 ID 得到某個 `Player` object.
##### Parameters
1. player's ID

##### Return type
Player &

---

```cpp
Player & Controller(const Zone &) const
```
查詢某個 zone 的佔領者是誰
##### Parameters
1. zone object

##### Return type
Player &

---

```cpp
Zone & zone(int) const
```
透過 ID 得到某個 `Zone` object.
##### Parameters
1. the zone's ID

##### Return type
Zone &

---

```cpp
Zone & Trace(const Drone &) const
```

---

```cpp
Iter<Drone> drones(const Player &, const Zone &) const
```

---

```cpp
int Control(const Zone &) const
```

---

```cpp
void UpdateZones()
```

---

```cpp
void SocialDistancing() const
```
```cpp
void Output() const
```
```cpp
void StayHome() const
```
```cpp
template<typename T, typename U> static void Sort(Iter<T> &, const U &)
```
```cpp
template<typename T> static void Sort(Iter<T> &, bool (*)(const T &, const T &))
```