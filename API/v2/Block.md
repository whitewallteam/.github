# block

`block` 模块提供 Minecraft 方块相关 API，包括方块状态查询、方块实体数据读取、命令方块修改以及方块实体数据更新等功能。

通过 `require` 获取：

```javascript
const block = require("block");
````

---

# Block

表示一个 Minecraft 方块状态对象。

## 构造方法

### 语法

```javascript
new block.Block(name, state);
```

### 参数

| 参数  | 类型   | 必填 | 说明       |
|-------|--------|------|------------|
| name  | string | 是   | 方块名称   |
| state | number | 否   | 方块状态值 |

### 示例

```javascript
const block = require("block");

const stone = new block.Block("minecraft:stone");
```

指定状态：

```javascript
const blockState = new block.Block(
    "minecraft:oak_log",
    1
);
```

### 注意

* 必须使用 `new` 创建实例。
* 方块不存在时会抛出异常。

---

## Block.getData

获取方块数据。

### 语法

```javascript
block.getData();
```

### 返回值

返回方块内部数据。

### 示例

```javascript
const data = stone.getData();
```

---

## Block.getRuntimeId

获取方块 Runtime ID。

### 语法

```javascript
block.getRuntimeId();
```

### 返回值

| 类型   | 说明          |
|--------|---------------|
| number | 方块运行时 ID |

### 示例

```javascript
console.log(stone.getRuntimeId());
```

---

## Block.getItemId

获取对应方块物品 ID。

### 语法

```javascript
block.getItemId();
```

### 返回值

| 类型   | 说明        |
|--------|-------------|
| number | 方块物品 ID |

---

## Block.getDescriptionId

获取方块描述 ID。

### 语法

```javascript
block.getDescriptionId();
```

### 返回值

| 类型   | 说明         |
|--------|--------------|
| string | 方块描述标识 |

示例：

```javascript
console.log(block.getDescriptionId());
```

---

## Block.getDescriptionName

获取方块显示名称。

### 语法

```javascript
block.getDescriptionName();
```

### 返回值

| 类型   | 说明         |
|--------|--------------|
| string | 方块名称文本 |

---

## Block.getNamespace

获取方块命名空间。

### 语法

```javascript
block.getNamespace();
```

### 返回值

| 类型   | 说明         |
|--------|--------------|
| string | 方块命名空间 |

示例：

```javascript
console.log(block.getNamespace());
// minecraft
```

---

## Block.getExplosionResistance

获取爆炸抗性。

### 语法

```javascript
block.getExplosionResistance();
```

### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 爆炸抗性 |

---

## Block.getLightEmission

获取光照发射等级。

### 语法

```javascript
block.getLightEmission();
```

### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 发光等级 |

---

## Block.getLightAbsorption

获取光照吸收等级。

### 语法

```javascript
block.getLightAbsorption();
```

### 返回值

| 类型   | 说明       |
|--------|------------|
| number | 光照吸收值 |

---

## Block.isSolid

判断方块是否为实体方块。

### 语法

```javascript
block.isSolid();
```

### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 是否为实体方块 |

示例：

```javascript
if (stone.isSolid()) {
    console.log("实体方块");
}
```

---

## Block.getNBT

获取方块 NBT 数据。

### 语法

```javascript
block.getNBT();
```

### 返回值

| 类型   | 说明               |
|--------|--------------------|
| string | Mojangson 格式 NBT |

### 示例

```javascript
console.log(block.getNBT());
```

---

# block.setCommandBlock

修改命令方块数据。

### 语法

```javascript
block.setCommandBlock(data);
```

### 参数

| 参数 | 类型   | 必填 | 说明         |
|------|--------|------|--------------|
| data | object | 是   | 命令方块数据 |

### data 参数

| 字段               | 类型          | 必填 | 说明         |
|--------------------|---------------|------|--------------|
| pos                | object        | 否   | 方块坐标     |
| mode               | number/string | 是   | 命令方块模式 |
| redstoneMode       | boolean       | 否   | 是否需要红石 |
| isConditional      | boolean       | 否   | 是否条件执行 |
| entityId           | string        | 否   | 实体 ID      |
| command            | string        | 否   | 命令内容     |
| lastOutput         | string        | 否   | 上次输出     |
| name               | string        | 否   | 命令方块名称 |
| tickDelay          | number        | 否   | 延迟 Tick    |
| trackOutput        | boolean       | 否   | 是否记录输出 |
| executeOnFirstTick | boolean       | 否   | 首 Tick 执行 |
| isBlock            | boolean       | 否   | 是否方块模式 |

### mode 支持

字符串形式：

| 值        | 说明         |
|-----------|--------------|
| Tick      | 普通命令方块 |
| Repeating | 循环命令方块 |
| Chain     | 连锁命令方块 |

### 示例

```javascript
const block = require("block");

block.setCommandBlock({
    pos: {
        x: 0,
        y: 64,
        z: 0
    },
    mode: "Repeating",
    command: "say hello",
    tickDelay: 20
});
```

### 注意

* 必须处于游戏内。
* 需要当前玩家存在。

---

# block.setBlockEntityData

更新方块实体数据。

### 语法

```javascript
block.setBlockEntityData(position, nbt);
```

### 参数

| 参数     | 类型   | 必填 | 说明               |
|----------|--------|------|--------------------|
| position | object | 是   | 方块坐标           |
| nbt      | string | 是   | Mojangson 格式 NBT |

### position 格式

```text
{
    x: number,
    y: number,
    z: number
}
```

### 示例

```javascript
block.setBlockEntityData(
    {
        x: 10,
        y: 64,
        z: 10
    },
    "{CustomName:'Test'}"
);
```

### 注意

* 必须处于游戏内。
* 需要当前玩家存在。

