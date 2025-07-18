
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
- `data` - `ArrayBuffer` - RPC 数据

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let buffer = new ArrayBuffer(8);
let isRpcSent = sendRpc(1, buffer);
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
let send = sendMovePlayer({id:'entityId',pos:{x:100,y:200,z:300}});
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
let send = sendPlayerAction({id:'entityId',pos:{x:100,y:200,z:300},type:1});
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

