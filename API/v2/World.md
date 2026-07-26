`world` 模块提供世界相关 API，包括世界实例获取、维度访问、实体查询、方块操作、粒子生成、命中检测、结构定位以及调试图形等功能。

通过 `require` 获取：

```javascript
const world = require("world");
```

---

| 名称      | 类型  | 说明                             |
|-----------|-------|----------------------------------|
| Level     | class | 世界对象。                       |
| Dimension | class | 维度对象。                       |
| Shape     | class | 调试图形对象，用于渲染 AABB 盒。 |

---

## getServerWorld

获取当前服务端世界。

#### 语法

```javascript
world.getServerWorld();
```

#### 返回值

| 类型  | 说明             |
|-------|------------------|
| Level | 服务端世界对象。 |

#### 示例

```javascript
const world = require("world");

const level = world.getServerWorld();
```

---

## getClientWorld

获取当前客户端世界。

#### 语法

```javascript
world.getClientWorld();
```

#### 返回值

| 类型  | 说明             |
|-------|------------------|
| Level | 客户端世界对象。 |

#### 示例

```javascript
const world = require("world");

const level = world.getClientWorld();
```

---

## leaveWorld

退出当前世界。

多人游戏中会主动向服务器发送断开连接请求，然后退出当前世界。

#### 语法

```javascript
world.leaveWorld();
```

#### 返回值

无。

#### 示例

```javascript
const world = require("world");

world.leaveWorld();
```

## Shape

`Shape` 用于创建并管理调试渲染图形，目前支持渲染三维包围盒（AABB）。

创建实例：

```javascript
const {Shape} = require("world");
```

---

创建一个调试包围盒。

#### 语法

```javascript
new Shape(options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明       |
|---------|--------|------|------------|
| options | object | 是   | 图形配置。 |

`options` 对象支持以下字段：

| 字段    | 类型    | 必填 | 默认值                       | 说明             |
|---------|---------|------|------------------------------|------------------|
| visible | boolean | 否   | `true`                       | 是否显示图形。   |
| isFill  | boolean | 否   | `false`                      | 是否填充显示。   |
| lower   | Vec3    | 是   | -                            | 包围盒最小坐标。 |
| upper   | Vec3    | 是   | -                            | 包围盒最大坐标。 |
| color   | Color   | 否   | `{ r: 0, g: 0, b: 0, a: 0 }` | 图形颜色。       |

#### 返回值

| 类型  | 说明               |
|-------|--------------------|
| Shape | 创建后的图形对象。 |

#### 示例

```javascript
const {Shape} = require("world");

const box = new Shape({
    lower: {
        x: 0,
        y: 64,
        z: 0
    },
    upper: {
        x: 1,
        y: 65,
        z: 1
    },
    color: {
        r: 1,
        g: 0,
        b: 0,
        a: 1
    }
});
```

---

### visible

图形是否可见。

#### 类型

```javascript
boolean
```

#### 可读

是。

#### 可写

是。

#### 示例

```javascript
shape.visible = false;

shape.visible = true;
```

---

### isFill

是否以填充方式渲染。

#### 类型

```javascript
boolean
```

#### 可读

是。

#### 可写

是。

#### 示例

```javascript
shape.isFill = true;
```

---

### lower

包围盒最小坐标。

#### 类型

```javascript
Vec3
```

#### 可读

是。

#### 可写

是。

#### 示例

```javascript
shape.lower = {
    x: 0,
    y: 60,
    z: 0
};
```

---

### upper

包围盒最大坐标。

#### 类型

```javascript
Vec3
```

#### 可读

是。

#### 可写

是。

#### 示例

```javascript
shape.upper = {
    x: 10,
    y: 70,
    z: 10
};
```

---

### color

图形颜色。

#### 类型

```javascript
Color
```

#### 可读

是。

#### 可写

是。

#### 示例

```javascript
shape.color = {
    r: 0,
    g: 1,
    b: 0,
    a: 1
};
```

---

### remove

移除该图形。

#### 语法

```javascript
shape.remove();
```

#### 返回值

无。

#### 示例

```javascript
shape.remove();
```

## Level

`Level` 类用于操作当前世界，提供玩家、实体、维度、世界设置、粒子、射线检测等功能。

通常通过 `world.getServerWorld()` 或 `world.getClientWorld()` 获取实例，而不是直接创建。

```javascript
const world = require("world");

const level = world.getClientWorld();
```

---

### getPlayerList

获取玩家列表信息。

#### 语法

```javascript
level.getPlayerList();
```

#### 参数

无。

#### 返回值

返回 `Object`，键为玩家 UUID，值为玩家信息对象。

玩家信息结构：

| 字段                   | 类型   | 说明               |
|------------------------|--------|--------------------|
| id                     | string | 玩家唯一 ID        |
| name                   | string | 玩家名称           |
| uuid                   | string | UUID               |
| xuid                   | string | XUID               |
| platformOnlineId       | string | 平台在线 ID        |
| buildPlatform          | string | 登录平台           |
| growthLevelData        | number | 成长等级数据       |
| permissionLevel        | string | 玩家权限（存在时） |
| commandPermissionLevel | string | 指令权限（存在时） |

#### 示例

```javascript
const list = level.getPlayerList();

for (const uuid in list) {
    console.log(list[uuid].name);
}
```

---

### getPlayers

获取当前世界所有玩家。

#### 语法

```javascript
level.getPlayers();
```

#### 参数

无。

#### 返回值

返回 `Player[]`。

#### 示例

```javascript
const players = level.getPlayers();

for (const player of players) {
    console.log(player.getName());
}
```

---

### getActors

获取当前世界所有实体。

#### 语法

```javascript
level.getActors();
```

#### 参数

无。

#### 返回值

返回 `Actor[]`。

#### 示例

```javascript
const actors = level.getActors();

console.log(actors.length);
```

---

### getDifficulty

获取世界难度。

#### 语法

```javascript
level.getDifficulty();
```

#### 参数

无。

#### 返回值

返回 `number`。

#### 示例

```javascript
const difficulty = level.getDifficulty();
```

---

### setDifficulty

设置世界难度。

#### 语法

```javascript
level.setDifficulty(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| value | number | 是   | 世界难度 |

#### 返回值

无。

#### 示例

```javascript
level.setDifficulty(2);
```

---

### getFlatWorldLayers

获取超平坦世界层配置。

#### 语法

```javascript
level.getFlatWorldLayers();
```

#### 参数

无。

#### 返回值

返回 `string`。

---

### setFlatWorldLayers

设置超平坦世界层配置。

#### 语法

```javascript
level.setFlatWorldLayers(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明       |
|-------|--------|------|------------|
| value | string | 是   | 世界层配置 |

#### 返回值

无。

---

### getForceGameType

获取是否强制游戏模式。

#### 语法

```javascript
level.getForceGameType();
```

#### 返回值

返回 `boolean`。

---

### setForceGameType

设置是否强制游戏模式。

#### 语法

```javascript
level.setForceGameType(value);
```

#### 参数

| 参数  | 类型    | 必填 |
|-------|---------|------|
| value | boolean | 是   |

#### 返回值

无。

---

### getGameType

获取默认游戏模式。

#### 语法

```javascript
level.getGameType();
```

#### 返回值

返回 `number`。

---

### setGameType

设置默认游戏模式。

#### 语法

```javascript
level.setGameType(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getLastPlayed

获取最后游玩时间。

#### 语法

```javascript
level.getLastPlayed();
```

#### 返回值

返回 `string`。

---

### setLastPlayed

设置最后游玩时间。

#### 语法

```javascript
level.setLastPlayed(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | string | 是   |

#### 返回值

无。

---

### getLevelName

获取世界名称。

#### 语法

```javascript
level.getLevelName();
```

#### 返回值

返回 `string`。

---

### setLevelName

设置世界名称。

#### 语法

```javascript
level.setLevelName(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | string | 是   |

#### 返回值

无。

---

### getRandomSeed

获取世界种子。

#### 语法

```javascript
level.getRandomSeed();
```

#### 返回值

返回 `bigint`。

---

### setRandomSeed

设置世界种子。

> **注意：**
>
> 客户端世界（多人游戏）无法修改世界种子，否则会抛出异常。

#### 语法

```javascript
level.setRandomSeed(seed);
```

#### 参数

| 参数 | 类型   | 必填 |
|------|--------|------|
| seed | bigint | 是   |

#### 返回值

无。

---

### getTime

获取世界时间。

#### 语法

```javascript
level.getTime();
```

#### 返回值

返回 `bigint`。

---

### setTime

设置世界时间。

#### 语法

```javascript
level.setTime(time);
```

#### 参数

| 参数 | 类型   | 必填 |
|------|--------|------|
| time | bigint | 是   |

#### 返回值

无。

---

### getLightningLevel

获取雷暴强度。

#### 语法

```javascript
level.getLightningLevel();
```

#### 返回值

返回 `number`。

---

### setLightningLevel

设置雷暴强度。

#### 语法

```javascript
level.setLightningLevel(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getLightningTime

获取雷暴持续时间。

#### 语法

```javascript
level.getLightningTime();
```

#### 返回值

返回 `number`。

---

### setLightningTime

设置雷暴持续时间。

#### 语法

```javascript
level.setLightningTime(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getRainLevel

获取降雨强度。

#### 语法

```javascript
level.getRainLevel();
```

#### 返回值

返回 `number`。

---

### setRainLevel

设置降雨强度。

#### 语法

```javascript
level.setRainLevel(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getRainTime

获取降雨持续时间。

#### 语法

```javascript
level.getRainTime();
```

#### 返回值

返回 `number`。

---

### setRainTime

设置降雨持续时间。

#### 语法

```javascript
level.setRainTime(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getRandomTickSpeed

获取随机刻速度。

#### 语法

```javascript
level.getRandomTickSpeed();
```

#### 返回值

返回 `number`。

---

### setRandomTickSpeed

设置随机刻速度。

#### 语法

```javascript
level.setRandomTickSpeed(value);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| value | number | 是   |

#### 返回值

无。

---

### getEntity

根据唯一 ID 获取实体。

#### 语法

```javascript
level.getEntity(uniqueId);
```

#### 参数

| 参数     | 类型   | 必填 | 说明          |
|----------|--------|------|---------------|
| uniqueId | string | 是   | ActorUniqueID |

#### 返回值

返回 `Actor`。

---

### getRuntimeEntity

根据运行时 ID 获取实体。

#### 语法

```javascript
level.getRuntimeEntity(runtimeId);
```

#### 参数

| 参数      | 类型   | 必填 |
|-----------|--------|------|
| runtimeId | string | 是   |

#### 返回值

返回 `Actor`。

---

### getPlayer

根据唯一 ID 获取玩家。

#### 语法

```javascript
level.getPlayer(uniqueId);
```

#### 参数

| 参数     | 类型   | 必填 |
|----------|--------|------|
| uniqueId | string | 是   |

#### 返回值

返回 `Player`。

---

### getRuntimePlayer

根据运行时 ID 获取玩家。

#### 语法

```javascript
level.getRuntimePlayer(runtimeId);
```

#### 参数

| 参数      | 类型   | 必填 |
|-----------|--------|------|
| runtimeId | string | 是   |

#### 返回值

返回 `Player`。

---

### findStructure

寻找指定结构。

#### 语法

```javascript
level.findStructure(name, pos);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 结构名称 |
| pos  | Vec3   | 是   | 搜索起点 |

#### 返回值

返回对象：

| 字段 | 类型   | 说明    |
|------|--------|---------|
| id   | number | 维度 ID |
| x    | number | X 坐标  |
| y    | number | Y 坐标  |
| z    | number | Z 坐标  |

#### 示例

```javascript
const result = level.findStructure(
    "minecraft:village",
    {x: 0, y: 64, z: 0}
);
```

---

### addParticle

生成粒子。

#### 语法

```javascript
level.addParticle(options);
```

#### 参数

| 字段   | 类型    | 必填 | 说明         |
|--------|---------|------|--------------|
| type   | number  | 是   | 粒子类型     |
| pos    | Vec3    | 否   | 粒子位置     |
| dir    | Vec3    | 否   | 粒子方向     |
| data   | number  | 否   | 粒子数据     |
| global | boolean | 否   | 是否全局广播 |

#### 返回值

无。

#### 示例

```javascript
level.addParticle({
    type: 1,
    pos: {
        x: 0,
        y: 64,
        z: 0
    }
});
```

---

### getHitResult

获取当前准星命中的结果。

#### 语法

```javascript
level.getHitResult();
```

#### 参数

无。

#### 返回值

返回命中信息对象。

主要字段：

| 字段         | 类型    |
|--------------|---------|
| startPos     | Vec3    |
| type         | string  |
| facing       | string  |
| blockPos     | Vec3    |
| pos          | Vec3    |
| entity       | string  |
| isHitLiquid  | boolean |
| liquidFacing | string  |
| liquid       | Vec3    |
| liquidPos    | Vec3    |
| indirectHit  | boolean |

---

### getLiquidHitResult

获取液体射线检测结果。

#### 语法

```javascript
level.getLiquidHitResult();
```

#### 返回值

返回对象结构与 `getHitResult()` 相同。

---

### getDimension

获取指定维度。

#### 语法

```javascript
level.getDimension(id);
```

或

```javascript
level.getDimension(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明                             |
|------|--------|------|----------------------------------|
| id   | number | 是   | 维度 ID                          |
| name | string | 是   | `overworld`、`nether`、`the_end` |

#### 返回值

返回 `Dimension`。

#### 示例

```javascript
const overworld = level.getDimension("overworld");

const nether = level.getDimension(-1);
```

---

## Dimension

`Dimension` 类用于操作世界维度，提供方块读取与修改、方块实体获取以及维度信息查询等功能。

---

### getDimensionId

获取当前维度 ID。

#### 语法

```javascript
dimension.getDimensionId();
```

#### 参数

无。

#### 返回值

| 类型   | 说明          |
|--------|---------------|
| number | 当前维度 ID。 |

#### 示例

```javascript
const id = dimension.getDimensionId();

console.log(id);
```

---

### getBlock

获取指定坐标的方块。

#### 语法

```javascript
dimension.getBlock(position);
```

#### 参数

| 参数     | 类型   | 必填 | 说明       |
|----------|--------|------|------------|
| position | Object | 是   | 方块坐标。 |

`position` 对象结构：

| 字段 | 类型   | 必填 | 说明   |
|------|--------|------|--------|
| x    | number | 是   | X 坐标 |
| y    | number | 是   | Y 坐标 |
| z    | number | 是   | Z 坐标 |

#### 返回值

| 类型  | 说明                 |
|-------|----------------------|
| Block | 对应位置的方块对象。 |

#### 示例

```javascript
const block = dimension.getBlock({
    x: 0,
    y: 64,
    z: 0
});

console.log(block);
```

---

### setBlock

设置指定坐标的方块。

#### 语法

```javascript
dimension.setBlock(position, block);
```

#### 参数

| 参数     | 类型   | 必填 | 说明               |
|----------|--------|------|--------------------|
| position | Object | 是   | 方块坐标。         |
| block    | Block  | 是   | 要设置的方块对象。 |

`position` 对象结构：

| 字段 | 类型   | 必填 | 说明   |
|------|--------|------|--------|
| x    | number | 是   | X 坐标 |
| y    | number | 是   | Y 坐标 |
| z    | number | 是   | Z 坐标 |

#### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 是否设置成功。 |

#### 示例

```javascript
const block = dimension.getBlock({
    x: 0,
    y: 64,
    z: 0
});

dimension.setBlock({
    x: 10,
    y: 64,
    z: 10
}, block);
```

---

### getBlockEntity

获取指定位置的方块实体（Block Entity）。

如果目标位置不存在方块实体，将抛出异常。

#### 语法

```javascript
dimension.getBlockEntity(position);
```

#### 参数

| 参数     | 类型   | 必填 | 说明       |
|----------|--------|------|------------|
| position | Object | 是   | 方块坐标。 |

`position` 对象结构：

| 字段 | 类型   | 必填 | 说明   |
|------|--------|------|--------|
| x    | number | 是   | X 坐标 |
| y    | number | 是   | Y 坐标 |
| z    | number | 是   | Z 坐标 |

#### 返回值

| 类型        | 说明                     |
|-------------|--------------------------|
| BlockEntity | 指定位置的方块实体对象。 |

#### 示例

```javascript
const blockEntity = dimension.getBlockEntity({
    x: 100,
    y: 64,
    z: 100
});

console.log(blockEntity);
```


