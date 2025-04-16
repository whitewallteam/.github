
## onCallModuleEvent

**描述**: 主题 UI 调用时触发，内容格式为 key:value 形式。

**参数**:
- `args` - `object` - 调用参数

**返回值**: 无

**示例代码**:
```javascript
function onCallModuleEvent(args) {
    console.log("Module called with args: ", args);
}
```

**注意事项**: 无

---

## onPlayerBuildBlockEvent

**描述**: 玩家放置方块时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `playerId` - `string` - 玩家唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `side` - `number` - 方块的侧面

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPlayerBuildBlockEvent(playerId, x, y, z, side) {
    console.log(`Player ${playerId} built a block at (${x}, ${y}, ${z}) on side ${side}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPlayerDestroyBlockEvent

**描述**: 玩家破坏方块时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `playerId` - `string` - 玩家唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `side` - `number` - 方块的侧面

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPlayerDestroyBlockEvent(playerId, x, y, z, side) {
    console.log(`Player ${playerId} destroyed a block at (${x}, ${y}, ${z}) on side ${side}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPlayerUseItemEvent

**描述**: 玩家使用物品时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `playerId` - `string` - 玩家唯一标识
- `itemId` - `number` - 物品ID
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `side` - `number` - 方块的侧面

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPlayerUseItemEvent(playerId, itemId, x, y, z, side) {
    console.log(`Player ${playerId} used item ${itemId} at (${x}, ${y}, ${z}) on side ${side}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPlayerAttackEvent

**描述**: 玩家攻击实体时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `playerId` - `string` - 玩家唯一标识
- `targetId` - `string` - 目标实体唯一标识

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPlayerAttackEvent(playerId, targetId) {
    console.log(`Player ${playerId} attacked entity ${targetId}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPlayerJumpEvent

**描述**: 玩家跳跃时触发。

**参数**:
- `playerId` - `string` - 玩家唯一标识

**返回值**: 无

**示例代码**:
```javascript
function onPlayerJumpEvent(playerId) {
    console.log(`Player ${playerId} jumped`);
}
```

**注意事项**: 无

---

## onPlayerInteractEvent

**描述**: 玩家与实体交互时触发。

**参数**:
- `playerId` - `string` - 玩家唯一标识
- `targetId` - `string` - 目标实体唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标

**返回值**: 无

**示例代码**:
```javascript
function onPlayerInteractEvent(playerId, targetId, x, y, z) {
    console.log(`Player ${playerId} interacted with entity ${targetId} at (${x}, ${y}, ${z})`);
}
```

**注意事项**: 无

---

## onSendChatMessageEvent

**描述**: 发送消息时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `message` - `string` - 消息内容

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onSendChatMessageEvent(message) {
    console.log(`Chat message sent: ${message}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onExecuteCommandEvent

**描述**: 执行命令时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `command` - `string` - 命令内容

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onExecuteCommandEvent(command) {
    console.log(`Command executed: ${command}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onClientMessageEvent

**描述**: 收到消息时触发(返回值为 true 表示拦截事件发生)。

**参数**:
- `name` - `string` - 玩家名称
- `message` - `string` - 消息内容

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onClientMessageEvent(name, message) {
    console.log(`Client message received: ${message} ${name}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onTickEvent

**描述**: 游戏刻事件(正常情况每秒调用20次)。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
function onTickEvent() {
    console.log("Tick event");
}
```

**注意事项**: 无

---

## onCommandOutputEvent

**描述**: 命令输出事件(返回值为 true 表示拦截事件发生)。

**参数**:
- `type` - `number` - 输出类型
- `args` - `array` - 输出参数
- `value` - `number` - 输出值

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onCommandOutputEvent(type, args, value) {
    console.log(`Command output: type=${type}, args=${args}, value=${value}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onEntityBehaviorEvent

**描述**: 实体行为事件。

**参数**:
- `id` - `string` - 实体唯一标识
- `behavior` - `int` - 行为类型
- `value` - `int` - 数据值

**返回值**: 无

**示例代码**:
```javascript
function onEntityBehaviorEvent(id, behavior, value) {
    console.log(`Player behavior : ${behavior}`);
    const HURT_ANIMATION = 2;
    if (behavior == HURT_ANIMATION) {
        console.log(`Player ${id} attacked`);
    }
}
```

**注意事项**: 无

---

## onPyRpcSendEvent

**描述**: PyRpc 发送事件(返回值为 true 表示拦截事件发生)。

**参数**:
- `id` - `number` - RPC ID
- `data` - `string` - RPC 数据

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPyRpcSendEvent(id, data) {
    console.log(`PyRpc send: id=${id}, data=${data}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPyRpcReceiveEvent

**描述**: PyRpc 接收事件(返回值为 true 表示拦截事件发生)。

**参数**:
- `id` - `number` - RPC ID
- `data` - `string` - RPC 数据

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onPyRpcReceiveEvent(id, data) {
    console.log(`PyRpc receive: id=${id}, data=${data}`);
    return false; // 不拦截事件
}
```

**注意事项**: 无

---

## onPlayerAuthInputEvent

**描述**: 玩家授权输入(BDS Server)。

**参数**:
- `input` - `PlayerAuthInput` - 玩家授权输入数据

**返回值**: 无

**示例代码**:
```javascript
function onPlayerAuthInputEvent(input) {
    console.log("Player auth input: ", input);
}
```

**注意事项**: 无

---

## onPlayerInputEvent

**描述**: 玩家输入(Nukkit Server)。

**参数**:
- `input` - `PlayerInput` - 玩家输入数据

**返回值**: 无

**示例代码**:
```javascript
function onPlayerInputEvent(input) {
    console.log("Player input: ", input);
}
```

**注意事项**: 无

---

## onReadyEvent

**描述**: 玩家进入世界加载完成。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
function onReadyEvent() {
    console.log("Player ready");
}
```

**注意事项**: 无

---

## onKeyboardDownEvent

**描述**: 当键盘按键被按下时触发的事件。按键映射请参考[Android文档](https://developer.android.google.cn/ndk/reference/group/input)。

**参数**:
- `key` (number): 被按下的键的代码。

**返回值**: 无

**示例代码**:
```javascript
function onKeyboardDownEvent(key) {
    console.log("Key down: " + key);
}
```

**注意事项**: 无

---

## onKeyboardUpEvent

**描述**: 当键盘按键被释放时触发的事件。按键映射请参考[Android文档](https://developer.android.google.cn/ndk/reference/group/input)。

**参数**:
- `key` (number): 被释放的键的代码。

**返回值**: 无

**示例代码**:
```javascript
function onKeyboardUpEvent(key) {
    console.log("Key up: " + key);
}
```

**注意事项**: 无

---

## onTouchMotionDownEvent

**描述**: 当触摸屏幕时触发的事件。

**参数**:
- `pointer` (number): 触控点的标识符。
- `x` (number): 触控点的X坐标。
- `y` (number): 触控点的Y坐标。

**返回值**: 无

**示例代码**:
```javascript
function onTouchMotionDownEvent(pointer, x, y) {
    console.log("Touch down at (" + x + ", " + y + ") with pointer " + pointer);
}
```

**注意事项**: 无

---

## onTouchMotionMoveEvent

**描述**: 当在触摸屏幕上移动时触发的事件。

**参数**:
- `pointer` (number): 触控点的标识符。
- `x` (number): 触控点的X坐标。
- `y` (number): 触控点的Y坐标。

**返回值**: 无

**示例代码**:
```javascript
function onTouchMotionMoveEvent(pointer, x, y) {
    console.log("Touch move at (" + x + ", " + y + ") with pointer " + pointer);
}
```

**注意事项**: 无

---

## onTouchMotionUpEvent

**描述**: 当从触摸屏幕上抬起时触发的事件。

**参数**:
- `pointer` (number): 触控点的标识符。
- `x` (number): 触控点的X坐标。
- `y` (number): 触控点的Y坐标。

**返回值**: 无

**示例代码**:
```javascript
function onTouchMotionUpEvent(pointer, x, y) {
    console.log("Touch up at (" + x + ", " + y + ") with pointer " + pointer);
}
```

**注意事项**: 无

---

## onSendServerPacketEvent

**描述**: 发送数据包事件。

**参数**:
- `id` (number): 唯一id。
- `name` (string): 名称。

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onSendServerPacketEvent(id, name) {
    console.log("packet (" + id + ", " + name + ") ");
}
```

**注意事项**: 无

---

## onReceiveServerPacketEvent

**描述**: 接收数据包事件。

**参数**:
- `id` (number): 唯一id。
- `name` (string): 名称。

**返回值**: `boolean` - 返回 `true` 拦截事件，返回 `false` 继续执行

**示例代码**:
```javascript
function onReceiveServerPacketEvent(id, name) {
    console.log("packet (" + id + ", " + name + ") ");
}
```

**注意事项**: 无


---

## onSAuthLoginRequestEvent

**描述**: 授权登录事件。

**参数**:
- `body` (string): 请求主体。

**返回值**: `string` - 修改后的主体

**示例代码**:
```javascript
function onSAuthLoginRequestEvent(body) {
    console.log("login (" + body + ") ");
}
```

**注意事项**: 无

---

## onSAuthLoginResponseEvent

**描述**: 授权登录返回事件。

**参数**:
- `body` (string): 返回主体。

**返回值**: `string` - 修改后的主体

**示例代码**:
```javascript
function onSAuthLoginResponseEvent(body) {
    console.log("loginRes (" + body + ") ");
}
```

**注意事项**: 无

---

## onSAuthJsonHookEvent

**描述**: 获取SAuthJson钩子事件。

**参数**:
- `json` (string): 返回主体。

**返回值**: `string` - 修改后的主体

**示例代码**:
```javascript
function onSAuthJsonHook(json) {
    console.log("json (" + json + ") ");
}
```

**注意事项**: 无

---

## onContainerItemMoveEvent

**描述**: 容器物品移动事件。

**参数**:
- `slot` (number): 所在容器格子。
- `item` (string): 物品数据。

**返回值**: `boolean` - 返回 `true` 移动物品，返回 `false` 继续执行

**示例代码**:
```javascript
function onContainerItemMoveEvent(slot, item) {
    console.log("slot (" + slot + ") " + item);
}
```

**注意事项**: 无

