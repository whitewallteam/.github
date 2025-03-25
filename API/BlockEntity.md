
### getBlockEntityNBT

**描述**: 获取指定方块实体 NBT 数据。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标

**返回值**: `string` - NBT 数据

**示例代码**:
```javascript
let blockEntityNBT = getBlockEntityNBT(10, 64, 10);
console.log("Block Entity NBT: ", blockEntityNBT);
```

**注意事项**: 无

---

### setBlockEntityData

**描述**: 设置方块实体 NBT 数据。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `mojangson` - `string` - NBT 数据字符串

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isBlockEntityDataSet = setBlockEntityData(10, 64, 10, "{Data}");
console.log("Block Entity Data Set: " + isBlockEntityDataSet);
```

**注意事项**: 确保传入的 NBT 数据字符串格式正确。

---

### setCommandBlockMinecartData

**描述**: 设置命令方块矿车数据(需要 op 权限)。

**参数**:
- `id` - `string` - 矿车的唯一标识
- `data` - `CommandData` - 命令数据

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let commandMinecartData = { /* Command Data */ };
let isMinecartDataSet = setCommandBlockMinecartData("minecart123", commandMinecartData);
console.log("Command Block Minecart Data Set: " + isMinecartDataSet);
```

**注意事项**: 确保有 op 权限。
