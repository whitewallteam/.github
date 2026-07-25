`packet` 模块提供 Minecraft 网络数据包相关 API，可用于创建自定义数据包、写入二进制数据、向服务器或本地发送数据包，以及发送常用游戏网络数据包。

通过 `require` 获取：

```javascript
const packet = require("packet");
````

---

## Packet

用于创建和操作二进制数据流，可用于构造自定义 Minecraft 数据包。

#### 创建实例

#### 语法

```javascript
const p = new packet.Packet();
```

#### 示例

```javascript
const packet = require("packet");

const p = new packet.Packet();

p.writeString("Hello");
p.sendToServer(1);
```

---

#### 属性

### buffer

获取或设置当前数据流缓冲区。

#### 类型

`ArrayBuffer`

#### 示例

读取数据：

```javascript
const packet = require("packet");

const p = new packet.Packet();

const buffer = p.buffer;
```

设置数据：

```javascript
const packet = require("packet");

const p = new packet.Packet();

p.buffer = new ArrayBuffer(10);
```

---

#### Packet 方法

### sendToServer

将当前 Packet 数据发送到服务器。

#### 语法

```javascript
packet.sendToServer(packetId);
```

#### 参数

| 参数     | 类型   | 必填 | 说明                |
|----------|--------|------|---------------------|
| packetId | number | 是   | Minecraft 数据包 ID |

#### 返回值

`boolean`

* `true`：发送成功
* `false`：当前未进入游戏或发送失败

#### 示例

```javascript
const p = new packet.Packet();

p.writeString("test");

if (p.sendToServer(1)) {
    console.log("发送成功");
}
```

---

### sendToLocal

将当前 Packet 数据发送到本地网络处理。

#### 语法

```javascript
packet.sendToLocal(packetId);
```

#### 参数

| 参数     | 类型   | 必填 | 说明                |
|----------|--------|------|---------------------|
| packetId | number | 是   | Minecraft 数据包 ID |

#### 返回值

`boolean`

---

#### 数据写入方法

以下方法用于向 Packet 缓冲区写入不同类型的数据。

---

### writeBool

写入布尔值。

#### 语法

```javascript
packet.writeBool(value);
```

#### 参数

| 参数  | 类型    | 必填 | 说明     |
|-------|---------|------|----------|
| value | boolean | 是   | 写入的值 |

---

### writeByte

写入单字节整数。

#### 语法

```javascript
packet.writeByte(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明   |
|-------|--------|------|--------|
| value | number | 是   | 字节值 |

---

### writeUnsignedShort

写入无符号短整数。

#### 语法

```javascript
packet.writeUnsignedShort(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明    |
|-------|--------|------|---------|
| value | number | 是   | 0-65535 |

---

### writeSignedShort

写入有符号短整数。

#### 语法

```javascript
packet.writeSignedShort(value);
```

---

### writeUnsignedInt

写入无符号整数。

#### 语法

```javascript
packet.writeUnsignedInt(value);
```

---

### writeSignedInt

写入有符号整数。

#### 语法

```javascript
packet.writeSignedInt(value);
```

---

### writeSignedBigEndianInt

以大端序写入整数。

#### 语法

```javascript
packet.writeSignedBigEndianInt(value);
```

---

### writeUnsignedInt64

写入无符号 64 位整数。

#### 语法

```javascript
packet.writeUnsignedInt64(value);
```

---

### writeSignedInt64

写入有符号 64 位整数。

#### 语法

```javascript
packet.writeSignedInt64(value);
```

---

### writeUnsignedVarInt

写入无符号变长整数。

#### 语法

```javascript
packet.writeUnsignedVarInt(value);
```

---

### writeUnsignedVarInt64

写入无符号 64 位变长整数。

#### 语法

```javascript
packet.writeUnsignedVarInt64(value);
```

---

### writeVarInt

写入有符号变长整数。

#### 语法

```javascript
packet.writeVarInt(value);
```

---

### writeVarInt64

写入有符号 64 位变长整数。

#### 语法

```javascript
packet.writeVarInt64(value);
```

---

### writeDouble

写入双精度浮点数。

#### 语法

```javascript
packet.writeDouble(value);
```

---

### writeFloat

写入单精度浮点数。

#### 语法

```javascript
packet.writeFloat(value);
```

---

### writeFixedFloat

写入固定精度浮点数。

#### 语法

```javascript
packet.writeFixedFloat(value);
```

---

### writeNormalizedFloat

写入归一化浮点数。

#### 语法

```javascript
packet.writeNormalizedFloat(value);
```

---

### writeString

写入字符串。

#### 语法

```javascript
packet.writeString(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明         |
|-------|--------|------|--------------|
| value | string | 是   | 写入的字符串 |

#### 示例

```javascript
const p = new packet.Packet();

p.writeString("Hello Minecraft");
```

---

#### 快捷数据包发送

## sendLevelSoundEventPacket

发送 `LevelSoundEventPacket` 数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendLevelSoundEventPacket(options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明       |
|---------|--------|------|------------|
| options | object | 是   | 数据包参数 |

`options`：

| 参数            | 类型    | 必填 | 说明           |
|-----------------|---------|------|----------------|
| eventId         | number  | 否   | 声音事件 ID    |
| pos             | object  | 否   | 坐标 `{x,y,z}` |
| data            | number  | 否   | 附加数据       |
| actorIdentifier | string  | 否   | 实体标识       |
| isBaby          | boolean | 否   | 是否幼体       |
| isGlobal        | boolean | 否   | 是否全局声音   |

#### 示例

```javascript
const packet = require("packet");

packet.sendLevelSoundEventPacket({
    eventId: 1,
    pos: {
        x: 0,
        y: 64,
        z: 0
    }
});
```

---

## sendPyRpcPacket

发送 `PyRpcPacket` 数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendPyRpcPacket(id, data);
```

#### 参数

| 参数 | 类型   | 必填        | 说明   |
|------|--------|-------------|--------|
| id   | number | 是          | RPC ID |
| data | string | ArrayBuffer | 是     | 数据内容   |

字符串数据会自动转换为 MsgPack。

#### 示例

```javascript
const packet = require("packet");

packet.sendPyRpcPacket(
    100,
    JSON.stringify({
        action: "test"
    })
);
```

---

## sendMovePlayerPacket

发送玩家移动数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendMovePlayerPacket(options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| options | object | 是   | 移动参数 |

参数：

| 参数          | 类型    | 说明                |
|---------------|---------|---------------------|
| pos           | object  | 玩家位置 `{x,y,z}`  |
| rot           | object  | 玩家旋转 `{x,y}`    |
| yHeadRot      | number  | 头部旋转            |
| mode          | number  | 移动模式            |
| ground        | boolean | 是否在地面          |
| rideRuntimeId | string  | 骑乘实体 Runtime ID |
| teleportCause | number  | 传送原因            |
| teleportItem  | number  | 传送物品            |
| tick          | number  | 客户端 Tick         |

---

## sendPlayerActionPacket

发送玩家动作数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendPlayerActionPacket(options);
```

#### 参数

| 参数      | 类型   | 说明     |
|-----------|--------|----------|
| pos       | object | 方块位置 |
| resultPos | object | 结果位置 |
| face      | number | 方块面   |
| action    | number | 动作类型 |

---

## sendPlayerAuthInputPacket

发送玩家输入数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendPlayerAuthInputPacket(options);
```

#### 参数

| 参数                     | 类型     | 说明             |
|--------------------------|----------|------------------|
| rot                      | object   | 玩家旋转         |
| pos                      | object   | 玩家位置         |
| yHeadRot                 | number   | 头部旋转         |
| posDelta                 | object   | 位置变化         |
| isCameraDeparted         | boolean  | 摄像机是否分离   |
| isThirdPersonPerspective | boolean  | 是否第三人称     |
| playerRotationToCamera   | object   | 玩家到摄像机旋转 |
| isReadyPosDeltaDirty     | boolean  | 位置变化状态     |
| isOnGround               | boolean  | 是否在地面       |
| resetPosition            | number   | 重置位置状态     |
| vehicleRotation          | object   | 载具旋转         |
| analogMoveVector         | object   | 模拟移动向量     |
| move                     | object   | 移动向量         |
| interactRotation         | object   | 交互旋转         |
| cameraOrientation        | object   | 摄像机方向       |
| rawMoveVector            | object   | 原始移动向量     |
| inputData                | number[] | 输入状态列表     |
| inputMode                | number   | 输入模式         |
| playMode                 | number   | 游戏模式         |
| newInteractionModel      | number   | 新交互模式       |
| clientTick               | number   | 客户端 Tick      |
| playerBlockActions       | object[] | 方块操作列表     |
| clientPredictedVehicle   | string   | 客户端预测载具   |

---

#### playerBlockActions

数组元素：

```
{
    type: number,
    pos: {
        x: number,
        y: number,
        z: number
    },
    facing: number
}
```

---

## sendCommandRequestPacket

发送命令请求数据包。

#### 语法

```javascript
const packet = require("packet");

packet.sendCommandRequestPacket(options);
```

#### 参数

| 参数           | 类型    | 说明         |
|----------------|---------|--------------|
| command        | string  | 执行的命令   |
| origin         | object  | 命令来源     |
| version        | number  | 命令版本     |
| internalSource | boolean | 是否内部来源 |

`origin`：

| 参数      | 类型   | 说明     |
|-----------|--------|----------|
| type      | number | 来源类型 |
| uuid      | string | UUID     |
| requestId | string | 请求 ID  |
| playerId  | string | 玩家 ID  |

#### 示例

```javascript
const packet = require("packet");

packet.sendCommandRequestPacket({
    command: "/say hello"
});
```

