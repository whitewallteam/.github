`player` 模块提供玩家相关 API，包括玩家背包操作、能力设置、游戏模式切换、方块破坏与放置、物品交互以及本地玩家控制等功能。

通过 `require` 获取：

```javascript
const player = require("player");
````

---

# Player

玩家对象，继承自 [Actor](/API/v2/Actor.md)。

---

### getInventoryItem

获取指定背包槽位中的物品。

#### 语法

```javascript
player.getInventoryItem(slot);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| slot | number | 是   | 背包槽位 |

#### 返回值

返回 `ItemStack` 对象。

#### 示例

```javascript
const item = player.getInventoryItem(0);
```

---

### setInventoryItem

设置指定背包槽位中的物品。

#### 语法

```javascript
player.setInventoryItem(slot, item);
```

#### 参数

| 参数 | 类型      | 必填 | 说明         |
|------|-----------|------|--------------|
| slot | number    | 是   | 背包槽位     |
| item | ItemStack | 是   | 要设置的物品 |

#### 返回值

无。

#### 示例

```javascript
const item = new ItemStack("minecraft:diamond", 64);

player.setInventoryItem(0, item);
```

---

### addInventoryItem

添加物品到玩家背包。

#### 语法

```javascript
player.addInventoryItem(item);
```

或：

```javascript
player.addInventoryItem(nbt);
```

#### 参数

| 参数 | 类型   | 必填 | 说明             |
|------|--------|------|------------------|
| item | object | 是   | 物品信息对象     |
| nbt  | string | 是   | NBT 格式物品数据 |

物品信息对象：

| 参数  | 类型   | 必填 | 说明                               |
|-------|--------|------|------------------------------------|
| name  | string | 是   | 物品名称，例如 `minecraft:diamond` |
| count | number | 是   | 数量                               |
| data  | number | 否   | 物品数据值                         |
| aux   | number | 否   | 附加值                             |

#### 示例

添加钻石：

```javascript
player.addInventoryItem({
    name: "minecraft:diamond",
    count: 64
});
```

使用 NBT 添加：

```javascript
player.addInventoryItem(
    '{"Count":1b,"Name":"minecraft:diamond"}'
);
```

---

### getInventorySize

获取玩家背包容量。

#### 语法

```javascript
player.getInventorySize();
```

#### 返回值

| 类型   | 说明         |
|--------|--------------|
| number | 背包槽位数量 |

---

### getEmptySlotsCount

获取背包空余槽位数量。

#### 语法

```javascript
player.getEmptySlotsCount();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 空槽数量 |

---

### getFirstEmptySlot

获取第一个空背包槽位。

#### 语法

```javascript
player.getFirstEmptySlot();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 空槽位置 |

---

### getHotBarSize

获取快捷栏大小。

#### 语法

```javascript
player.getHotBarSize();
```

#### 返回值

| 类型   | 说明           |
|--------|----------------|
| number | 快捷栏槽位数量 |

---

### getSelectItemSlot

获取当前选中的快捷栏槽位。

#### 语法

```javascript
player.getSelectItemSlot();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 当前槽位 |

---

### setSelectItemSlot

设置当前选中的快捷栏槽位。

#### 语法

```javascript
player.setSelectItemSlot(slot);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| slot | number | 是   | 槽位编号 |

#### 示例

```javascript
player.setSelectItemSlot(2);
```

---

### dropInventorySlot

丢弃指定槽位物品。

#### 语法

```javascript
player.dropInventorySlot(slot);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| slot | number | 是   | 背包槽位 |

---

### getAbilities

获取玩家能力。

#### 语法

```javascript
player.getAbilities();
```

#### 返回值

返回能力对象。

示例：

```
{
    "mayfly": true,
    "instabuild": false,
    "flySpeed": 0.05
}
```

---

### setAbilities

设置玩家能力。

#### 语法

```javascript
player.setAbilities(abilities);
```

#### 参数

| 参数      | 类型   | 必填 | 说明     |
|-----------|--------|------|----------|
| abilities | object | 是   | 能力对象 |

#### 示例

```javascript
player.setAbilities({
    mayfly: true
});
```

---

### getBlockDestroyTime

获取破坏指定方块所需时间。

#### 语法

```javascript
player.getBlockDestroyTime(slot, block);
```

#### 参数

| 参数  | 类型   | 必填 | 说明           |
|-------|--------|------|----------------|
| slot  | number | 是   | 使用的工具槽位 |
| block | string | 是   | 方块名称       |

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 破坏速度 |

---

### startDestroyBlock

开始破坏方块。

#### 语法

```javascript
player.startDestroyBlock(pos, face);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| pos  | object | 是   | 方块坐标 |
| face | number | 是   | 面方向   |

#### 返回值

是否成功。

---

### continueDestroyBlock

继续破坏方块。

#### 语法

```javascript
player.continueDestroyBlock(pos, face);
```

---

### destroyBlock

立即破坏方块。

#### 语法

```javascript
player.destroyBlock(pos, face);
```

---

### stopDestroyBlock

停止破坏方块。

#### 语法

```javascript
player.stopDestroyBlock(pos);
```

---

### startBuildBlock

开始放置方块。

#### 语法

```javascript
player.startBuildBlock(pos, face);
```

---

### buildBlock

放置方块。

#### 语法

```javascript
player.buildBlock(pos, face);
```

---

### continueBuildBlock

继续放置方块。

#### 语法

```javascript
player.continueBuildBlock(pos, face);
```

---

### stopBuildBlock

停止放置方块。

#### 语法

```javascript
player.stopBuildBlock();
```

---

### useItem

使用当前手持物品。

#### 语法

```javascript
player.useItem();
```

#### 返回值

操作结果。

---

### releaseUsingItem

释放正在使用的物品。

#### 语法

```javascript
player.releaseUsingItem();
```

---

### attack

攻击实体。

#### 语法

```javascript
player.attack(entity);
```

#### 参数

| 参数   | 类型  | 必填 | 说明     |
|--------|-------|------|----------|
| entity | Actor | 是   | 目标实体 |

---

### interact

与实体交互。

#### 语法

```javascript
player.interact(entity);
```

#### 返回值

交互结果。

---

### getGameType

获取当前游戏模式。

#### 语法

```javascript
player.getGameType();
```

#### 返回值

| 类型   | 说明        |
|--------|-------------|
| number | 游戏模式 ID |

---

### setGameType

设置游戏模式。

#### 语法

```javascript
player.setGameType(type);
```

#### 参数

| 参数 | 类型   | 必填 | 说明        |
|------|--------|------|-------------|
| type | number | 是   | 游戏模式 ID |

---

### deleteContainerManager

删除容器管理器。

#### 语法

```javascript
player.deleteContainerManager();
```
