# LocalPlayer

`LocalPlayer` 继承自 [Player](/API/v2/Player.md)，表示当前客户端玩家。

---

### getLocalPlayer

获取当前本地玩家。

#### 语法

```javascript
player.getLocalPlayer();
```

#### 返回值

返回 `LocalPlayer` 对象。

#### 示例

```javascript
const player = require("player");

const localPlayer = player.getLocalPlayer();
```

---

### setTurn

设置玩家视角旋转。

#### 语法

```javascript
localPlayer.setTurn(rotation);
```

#### 参数

| 参数     | 类型   | 必填 | 说明     |
|----------|--------|------|----------|
| rotation | object | 是   | 旋转角度 |

---

### openInventory

打开玩家背包。

#### 语法

```javascript
localPlayer.openInventory();
```

---

### closeInventory

关闭玩家背包。

#### 语法

```javascript
localPlayer.closeInventory();
```

---

### moveInventoryItem

移动背包物品。

#### 语法

```javascript
localPlayer.moveInventoryItem(fromSlot, toSlot);
```

#### 参数

| 参数     | 类型   | 必填 | 说明     |
|----------|--------|------|----------|
| fromSlot | number | 是   | 来源槽位 |
| toSlot   | number | 是   | 目标槽位 |

---

### moveContainerItem

移动容器物品。

#### 语法

```javascript
localPlayer.moveContainerItem(items);
```

#### 参数

| 参数  | 类型  | 必填 | 说明         |
|-------|-------|------|--------------|
| items | array | 是   | 移动物品列表 |

列表元素：

| 参数            | 类型   | 说明            |
|-----------------|--------|-----------------|
| fromSlot        | number | 来源槽位        |
| fromNetId       | number | 来源物品网络 ID |
| fromContainerId | number | 来源容器 ID     |
| toSlot          | number | 目标槽位        |
| toNetId         | number | 目标物品网络 ID |
| toContainerId   | number | 目标容器 ID     |
| count           | number | 数量            |

---

### swapContainerItem

交换容器物品。

#### 语法

```javascript
localPlayer.swapContainerItem(items);
```

#### 参数

参数格式同 `moveContainerItem`，但不需要 `count`。
