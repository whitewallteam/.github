### sendSound

**描述**: 发送音效。

**参数**:

- `event` - `number` - 事件编号
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `level` - `number` - 音量级别

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
let isSoundSent = sendSound(1, 100, 64, 100, 5);
console.log("Sound Sent: " + isSoundSent);
```

**注意事项**: 无

---

### sendRpc

**描述**: 发送RPC。

**参数**:

- `id` - `number` - RPC ID
- `data` - `ArrayBuffer|string` - RPC 数据

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
let buffer = new ArrayBuffer(8);
let isRpcSent = sendRpc(1, buffer);
console.log("RPC Sent: " + isRpcSent);
```

```javascript
let json = JSON.stringify({type: "string", value: "Hello, World!"});
let isRpcSent = sendRpc(1, json);
console.log("RPC Sent: " + isRpcSent);
```

**注意事项**: 无

---

### sendMovePlayer

**描述**: 发送MovePlayer。

**参数结构**:

- `id` - `string` - 实体唯一标识
- `pos` - `Pos` - 坐标
- `rot` - `Rot` - 视角
- `yHeadRot` - `number` - 头部视角
- `mode` - `number` - 模式
- `ground` - `boolean` - 是否在地上

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
let send = sendMovePlayer({id: 'entityId', pos: {x: 100, y: 200, z: 300}});
console.log("MovePlayer Sent: " + send);
```

**注意事项**: 无

---

### sendPlayerAction

**描述**: 发送PlayerAction。

**参数结构**:

- `id` - `string` - 实体唯一标识
- `pos` - `Pos` - 坐标
- `value` - `number` - 数据值
- `type` - `PlayerAction` - 类型

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
let send = sendPlayerAction({id: 'entityId', pos: {x: 100, y: 200, z: 300}, type: 1});
console.log("PlayerAction Sent: " + send);
```

**注意事项**: 无

---

### sendPlayerAuthInput

**描述**: 发送玩家身份验证输入的网络数据包。

**参数结构**:

- `pos` - `Pos` (可选) - 玩家位置，包含 `x`, `y`, `z` 坐标。
- `rot` - `Rot` (可选) - 玩家旋转，包含 `yaw` 和 `pitch`。
- `yHeadRot` - `number` (可选) - 玩家头部旋转。
- `motion` - `Velocity` (可选) - 玩家运动，包含 `x`, `y`, `z` 运动数据。
- `analogMoveVector` - `Velocity` (可选) - 模拟移动向量，包含 `x` 和 `y`。
- `vehicleRotation` - `Rot` (可选) - 载具旋转，包含 `yaw` 和 `pitch`。
- `move` - `Object` (可选) - 玩家移动数据，包含 `x` 和 `y`。
- `gazeDir` - `Object` (可选) - 玩家视线方向，包含 `x`, `y`, `z`。
- `inputMode` - `InputMode` (可选) - 输入模式，默认为触控。
- `playMode` - `PlayMode` (可选) - 游戏模式，默认为屏幕模式。
- `newInteractionModel` - `number` (可选) - 新交互模型，默认为经典模型。
- `inputs` - `Array` (可选) - 输入数据数组，包含[PlayerInputFlags](/Enum/?id=playerinputflags)。
- `actions` - `Array` (可选) - 玩家动作数组，包含 `type`[(PlayerAction)](/Enum/?id=PlayerAction), `pos`, `value`。

**返回值**:

- `boolean` - 成功发送返回 `true`，否则返回 `false`。

**示例代码**:

```javascript
let result = sendPlayerAuthInput({pos: {x: 100, y: 200, z: 300}, rot: {yaw: 45, pitch: 90}});
console.log("PlayerAuthInput Sent: " + result);
```

**注意事项**: 确保提供有效的对象结构以避免发送失败。

---

### sendCommandRequest

**描述**: 发送命令请求。

**参数**:

- `command` - `string` - 命令字符串

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
let isCommandSent = sendCommandRequest("/give @p diamond 64");
console.log("Command Sent: " + isCommandSent);
```

**注意事项**: 无

---

## Packet

**描述**:
用于构建并发送自定义网络数据包的对象。通过一系列 `write*` 方法向包中写入二进制数据，最后使用 `send` 方法发送给本地玩家。

**构造方式**:

```javascript
let packet = new Packet();
```

**注意事项**:

* 必须使用 `new Packet()` 创建实例。
* `Packet` 内部维护一个二进制流，调用 `destroy` 后实例不可再使用。

---

### Packet.send

**描述**:
根据指定的数据包 ID 发送当前构建好的数据包。

**参数**:

* `packetId` - `number` - 数据包 ID（MinecraftPacketIds）

**返回值**:

* `boolean`

    * `true`：发送成功
    * `false`：发送失败

**示例代码**:

```javascript
let packet = new Packet();
packet.writeVarInt(123);
let result = packet.send(0x01);
```

**注意事项**:

* 必须在写入完所有数据后再调用。
* 若 `Packet` 已被销毁，将抛出异常。

---

### Packet.destroy

**描述**:
销毁当前 `Packet` 对象并释放内部资源。

**参数**: 无

**返回值**: 无

**示例代码**:

```javascript
packet.destroy();
```

**注意事项**:

* 调用后该 `Packet` 实例不可再使用。

---

### Packet.writeByte

**描述**:
向数据包写入一个有符号 8 位整数。

**参数**:

* `value` - `number` - `int8` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeByte(-5);
```

**注意事项**:

* 参数会被截断为 8 位。

---

### Packet.writeBool

**描述**:
向数据包写入一个布尔值。

**参数**:

* `value` - `boolean` - 布尔值

**返回值**: 无

**示例代码**:

```javascript
packet.writeBool(true);
```

**注意事项**: 无

---

### Packet.writeDouble

**描述**:
向数据包写入一个双精度浮点数。

**参数**:

* `value` - `number` - `double` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeDouble(3.1415926);
```

**注意事项**: 无

---

### Packet.writeFloat

**描述**:
向数据包写入一个单精度浮点数。

**参数**:

* `value` - `number` - `float` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeFloat(1.5);
```

**注意事项**:

* 精度为单精度浮点。

---

### Packet.writeVarInt

**描述**:
向数据包写入一个变长编码的 32 位整数（VarInt）。

**参数**:

* `value` - `number` - `int32` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeVarInt(300);
```

**注意事项**:

* 使用 VarInt 编码，适合小整数传输。

---

### Packet.writeVarInt64

**描述**:
向数据包写入一个变长编码的 64 位整数（VarInt64）。

**参数**:

* `value` - `bigint` - `int64` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeVarInt64(1234567890123n);
```

**注意事项**:

* 必须传入 `BigInt` 类型。

---

### Packet.writeSignedInt

**描述**:
向数据包写入一个有符号 32 位整数。

**参数**:

* `value` - `number` - `int32` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeSignedInt(-100);
```

**注意事项**: 无

---

### Packet.writeSignedInt64

**描述**:
向数据包写入一个有符号 64 位整数。

**参数**:

* `value` - `bigint` - `int64` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeSignedInt64(-999999999n);
```

**注意事项**:

* 参数必须为 `BigInt`。

---

### Packet.writeSignedShort

**描述**:
向数据包写入一个有符号 16 位整数。

**参数**:

* `value` - `number` - `int16` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeSignedShort(32000);
```

**注意事项**:

* 超出范围的值将被截断。

---

### Packet.writeUnsignedChar

**描述**:
向数据包写入一个无符号 8 位整数。

**参数**:

* `value` - `number` - `uint8` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeUnsignedChar(255);
```

**注意事项**:

* 有效范围为 `0 ~ 255`。

---

### Packet.writeUnsignedShort

**描述**:
向数据包写入一个无符号 16 位整数。

**参数**:

* `value` - `number` - `uint16` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeUnsignedShort(65535);
```

**注意事项**: 无

---

### Packet.writeUnsignedInt

**描述**:
向数据包写入一个无符号 32 位整数。

**参数**:

* `value` - `number` - `uint32` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeUnsignedInt(4294967295);
```

**注意事项**:

* JavaScript `number` 精度有限，避免超大值。

---

### Packet.writeUnsignedInt64

**描述**:
向数据包写入一个无符号 64 位整数。

**参数**:

* `value` - `bigint` - `uint64` 值

**返回值**: 无

**示例代码**:

```javascript
packet.writeUnsignedInt64(18446744073709551615n);
```

**注意事项**:

* 必须使用 `BigInt` 表示。
