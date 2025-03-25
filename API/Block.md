
### setBlock

**描述**: 设置指定位置方块。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `name` - `string` - 方块名称
- `state` - `number` - 方块状态

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isBlockSet = setBlock(10, 64, 10, "stone", 1);
console.log("Block Set: " + isBlockSet);
```

**注意事项**: 无

---

### getBlock

**描述**: 获取指定方块数据。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标

**返回值**: `Block` - 方块数据

**示例代码**:
```javascript
let block = getBlock(10, 64, 10);
console.log("Block Data: ", block);
```

**注意事项**: 无

---

### getBlockNBT

**描述**: 获取指定方块 NBT 数据。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标

**返回值**: `string` - NBT 数据

**示例代码**:
```javascript
let blockNBT = getBlockNBT(10, 64, 10);
console.log("Block NBT: ", blockNBT);
```

**注意事项**: 无

---

### setCommandBlockData

**描述**: 设置命令方块数据(需要 op 权限)。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `data` - `CommandData` - 命令数据

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let commandData = { /* Command Data */ };
let isCommandBlockDataSet = setCommandBlockData(10, 64, 10, commandData);
console.log("Command Block Data Set: " + isCommandBlockDataSet);
```

**注意事项**: 确保有 op 权限。
