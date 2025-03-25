
### findEntity

**描述**: 判断实体是否存在。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `boolean` - 实体存在返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let entityExists = findEntity("entity123");
console.log("Entity Exists: " + entityExists);
```

**注意事项**: 无

---

### isPlayer

**描述**: 判断实体是否为玩家。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `boolean` - 实体为玩家返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isPlayerEntity = isPlayer("entity123");
console.log("Is Player: " + isPlayerEntity);
```

**注意事项**: 无

---

### getEntityPos

**描述**: 获取实体坐标。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `Pos` - 实体的坐标

**示例代码**:
```javascript
let position = getEntityPos("entity123");
console.log("Entity Position: ", position);
```

**注意事项**: 无

---

### getEntityPosPrev

**描述**: 获取实体旧坐标。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `Pos` - 实体的坐标

**示例代码**:
```javascript
let position = getEntityPosPrev("entity123");
console.log("Entity Position: ", position);
```

**注意事项**: 无

---

### getEntityRot

**描述**: 获取实体视角弧度。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `Rot` - 实体的视角弧度

**示例代码**:
```javascript
let rotation = getEntityRot("entity123");
console.log("Entity Rotation: ", rotation);
```

**注意事项**: 无

---

### setEntityRot

**描述**: 设置实体视角角度。

**参数**:
- `id` - `string` - 实体唯一标识
- `pitch` - `number` - 俯仰角
- `yaw` - `number` - 偏航角

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didSetRot = setEntityRot('entityId',45, 90);
console.log("Entity Rotation Set: " + didSetRot);
```

**注意事项**: 无

---

### getEntityBodyRot

**描述**: 获取实体身体角度。

**参数**:
- `id` - `string` - 实体唯一标识

**返回值**: `number` - 角度

**示例代码**:
```javascript
let result = getEntityBodyRot('entityId');
console.log("Entity Body Rotation Get: " + result);
```

**注意事项**: 无

---

### setEntityBodyRot

**描述**: 设置实体身体角度。

**参数**:
- `id` - `string` - 实体唯一标识
- `rot` - `number` - 角度

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let result = setEntityBodyRot('entityId',10);
console.log("ok: " + result);
```

**注意事项**: 无

---

### getEntityMotion

**描述**: 获取实体移动值。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `Velocity` - 实体的移动值

**示例代码**:
```javascript
let motion = getEntityMotion("entity123");
console.log("Entity Motion: ", motion);
```

**注意事项**: 无

---

### setEntityPos

**描述**: 设置实体坐标。

**参数**:
- `id` - `string` - 实体的唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isPositionSet = setEntityPos("entity123", 100, 64, 200);
console.log("Is Position Set: " + isPositionSet);
```

**注意事项**: 无

---

### setEntityMotion

**描述**: 设置实体移动值。

**参数**:
- `id` - `string` - 实体的唯一标识
- `x` - `number` - X 方向的移动值
- `y` - `number` - Y 方向的移动值
- `z` - `number` - Z 方向的移动值

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMotionSet = setEntityMotion("entity123", 1, 0, 1);
console.log("Is Motion Set: " + isMotionSet);
```

**注意事项**: 无

---

### getEntityList

**描述**: 获取实体列表。

**参数**: 无

**返回值**: `array(string)` - 实体ID列表

**示例代码**:
```javascript
let entityList = getEntityList();
console.log("Entity List: ", entityList);
```

**注意事项**: 无

---

### getEntityTypeId

**描述**: 获取实体类型。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `number` - 实体类型ID

**示例代码**:
```javascript
let typeId = getEntityTypeId("entity123");
console.log("Entity Type ID: " + typeId);
```

**注意事项**: 无

---

### getEntityNamespace

**描述**: 获取实体命名空间。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 实体命名空间

**示例代码**:
```javascript
let namespace = getEntityNamespace("entity123");
console.log("Entity Namespace: " + namespace);
```

**注意事项**: 无

---

### getEntityName

**描述**: 获取实体名称。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 实体名称

**示例代码**:
```javascript
let name = getEntityName("entity123");
console.log("Entity Name: " + name);
```

**注意事项**: 无

---

### setEntityName

**描述**: 设置实体名称。

**参数**:
- `id` - `string` - 实体的唯一标识
- `name` - `string` - 实体的新名称

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isNameSet = setEntityName("entity123", "NewName");
console.log("Is Name Set: " + isNameSet);
```

**注意事项**: 无

---

### getEntitySize

**描述**: 获取实体大小。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `Collision` - 实体的大小

**示例代码**:
```javascript
let size = getEntitySize("entity123");
console.log("Entity Size: ", size);
```

**注意事项**: 无

---

### setEntitySize

**描述**: 设置实体大小。

**参数**:
- `id` - `string` - 实体的唯一标识
- `x` - `number` - 实体的宽度
- `y` - `number` - 实体的高度

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isSizeSet = setEntitySize("entity123", 2.0, 3.0);
console.log("Is Size Set: " + isSizeSet);
```

**注意事项**: 无

---

### setEntityAttribute

**描述**: 设置实体属性。

**参数**:
- `id` - `string` - 实体的唯一标识
- `name` - `string` - 属性名称
- `attribute` - `Attribute` - 属性值

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let attribute = { max:100,min:1,current:50 };
let isAttributeSet = setEntityAttribute("entity123", "minecraft:health", attribute);
console.log("Is Attribute Set: " + isAttributeSet);
```

**注意事项**: 无

---

### getEntityAttribute

**描述**: 获取实体属性。

**参数**:
- `id` - `string` - 实体的唯一标识
- `name` - `string` - 属性名称

**返回值**: `Attribute` - 属性值

**示例代码**:
```javascript
let attribute = getEntityAttribute("entity123", "minecraft:health");
console.log("Entity Attribute: ", attribute);
```

**注意事项**: 无

---

### getEntityNBT

**描述**: 获取实体 NBT 数据。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 实体的 NBT 数据

**示例代码**:
```javascript
let nbt = getEntityNBT("entity123");
console.log("Entity NBT: " + nbt);
```

**注意事项**: 无

---

### getEntityCompleteNBT

**描述**: 获取实体完整 NBT 数据。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 实体的完整 NBT 数据

**示例代码**:
```javascript
let completeNbt = getEntityCompleteNBT("entity123");
console.log("Entity Complete NBT: " + completeNbt);
```

**注意事项**: 无

---

### setEntityNBT

**描述**: 设置实体 NBT 数据。

**参数**:
- `id` - `string` - 实体的唯一标识
- `mojangson` - `string` - NBT 数据的字符串表示

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isNbtSet = setEntityNBT("entity123", "{Health:20}");
console.log("Is NBT Set: " + isNbtSet);
```

**注意事项**: 确保传入的 NBT 数据字符串格式正确。

---

### getEntityIsGround

**描述**: 获取实体是否在地上。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `boolean` - 实体在地上返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isGround = getEntityIsGround("entity123");
console.log("Is Entity On Ground: " + isGround);
```

**注意事项**: 无

---

### getEntityCarriedItem

**描述**: 获取实体手持物品数据。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 手持物品NBT数据

**示例代码**:
```javascript
let carriedItem = getEntityCarriedItem("entity123");
console.log("Entity Carried Item: ", carriedItem);
```

**注意事项**: 无

---

### setEntityCarriedItem

**描述**: 设置实体手持物品数据。

**参数**:
- `id` - `string` - 实体的唯一标识
- `nbt` - `string` - 物品NBT数据

**返回值**: `boolean` - 操作状态

**示例代码**:
```javascript
let status = setEntityCarriedItem("entity123","{...}");
console.log("status: ", status);
```

**注意事项**: 无

---

### getEntityOffhandItem

**描述**: 获取实体副手手持物品数据。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 副手手持物品NBT数据

**示例代码**:
```javascript
let offhandItem = getEntityOffhandItem("entity123");
console.log("Entity Offhand Item: ", offhandItem);
```

**注意事项**: 无

---

### setEntityOffhandItem

**描述**: 设置实体副手手持物品数据。

**参数**:
- `id` - `string` - 实体的唯一标识
- `nbt` - `string` - 物品NBT数据

**返回值**: `boolean` - 操作状态

**示例代码**:
```javascript
let status = setEntityOffhandItem("entity123","{...}");
console.log("status: ", status);
```

**注意事项**: 无

---

### setEntityTarget

**描述**: 设置实体目标(仅服务端)。

**参数**:
- `id` - `string` - 实体的唯一标识
- `target` - `string` - 目标实体的唯一标识

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isTargetSet = setEntityTarget("entity123", "targetEntity456");
console.log("Is Target Set: " + isTargetSet);
```

**注意事项**: 无

---

### getEntityTarget

**描述**: 获取实体目标(仅服务端)。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `string` - 目标实体的唯一标识

**示例代码**:
```javascript
let target = getEntityTarget("entity123");
console.log("Entity Target: " + target);
```

**注意事项**: 无

---

### setEntityModelName

**描述**: 设置实体模型名称。

**参数**:
- `id` - `string` - 实体的唯一标识
- `name` - `string` - 模型名称

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isModelNameSet = setEntityModelName("entity123", "NewModelName");
console.log("Is Model Name Set: " + isModelNameSet);
```

**注意事项**: 无

---

### setEntityModelTexture

**描述**: 设置实体模型材质。

**参数**:
- `id` - `string` - 实体的唯一标识
- `texture` - `string` - 模型材质

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isModelTextureSet = setEntityModelTexture("entity123", "NewTexture");
console.log("Is Model Texture Set: " + isModelTextureSet);
```

**注意事项**: 无

---

### getEntityFlag

**描述**: 获取实体状态标志。

**参数**:
- `id` - `string` - 实体的唯一标识
- `EntityFlag` - 实体状态标志

**返回值**: `boolean` - 状态标志的值

**示例代码**:
```javascript
const OnFire = 0;
let flagValue = getEntityFlag('entityId',OnFire);
console.log("Entity Flag ON_FIRE: " + flagValue);
```

**注意事项**: 无

---

### setEntityFlag

**描述**: 设置实体状态标志。

**参数**:
- `id` - `string` - 实体的唯一标识
- `EntityFlag` - 实体状态标志
- `bool` - 标志值

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
const OnFire = 0;
let isFlagSet = setEntityFlag('entityId',OnFire, true);
console.log("Is Flag Set: " + isFlagSet);
```

**注意事项**: 无

---

### getEntityEffectList

**描述**: 获取指定实体的效果列表。

**参数**:
- `entityId` - `string` - 实体的唯一标识符。

**返回值**: `array(EntityEffect)` - 实体的效果列表。

**示例代码**:
```javascript
let effects = getEntityEffectList("entity123");
console.log(effects);
```

**注意事项**: 确保 `entityId` 是有效的实体标识符。

---

### getEntityEffect

**描述**: 获取指定实体的单个效果。

**参数**:
- `entityId` - `string` - 实体的唯一标识符。

**返回值**: `EntityEffect` - 实体的效果。

**示例代码**:
```javascript
let effect = getEntityEffect("entity123");
console.log(effect);
```

**注意事项**: 确保 `entityId` 是有效的实体标识符。

---

### setEntityEffect

**描述**: 设置指定实体的效果。

**参数**:
- `entityId` - `string` - 实体的唯一标识符。
- `effect` - `number` - 要设置的效果。

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`。

**示例代码**:
```javascript
let effect = {id :1};
let isSet = setEntityEffect("entity123", effect);
console.log("Effect set: " + isSet);
```

**注意事项**: 确保 `entityId` 是有效的实体标识符，并且 `effect` 为有效的效果对象。

---

### removeEntityEffect

**描述**: 移除指定实体的特定效果。

**参数**:
- `entityId` - `string` - 实体的唯一标识符。
- `effectId` - `number` - 要移除的效果的唯一标识符。

**返回值**: `boolean` - 移除成功返回 `true`，否则返回 `false`。

**示例代码**:
```javascript
let isRemoved = removeEntityEffect("entity123", 0);
console.log("Effect removed: " + isRemoved);
```

**注意事项**: 确保 `entityId` 和 `effectId` 都是有效的标识符。

---

### startRidingEntity

**描述**: 让玩家开始骑乘指定的实体。

**参数**:
- `id` - `string` - 实体的唯一标识符。

**返回值**: 无。

**示例代码**:
```javascript
startRidingEntity("entity123");
```

**注意事项**: 
- 确保 `id` 是有效的实体标识符。
- 骑乘的实体必须支持被玩家骑乘的功能。
- 如果玩家当前已经骑乘另一个实体，调用该方法可能会失败。

---

### stopRidingEntity

**描述**: 让玩家停止骑乘当前骑乘的实体。

**参数**: 无

**返回值**: 无。

**示例代码**:
```javascript
stopRidingEntity();
```

**注意事项**:
- 确保玩家当前正处于骑乘状态，否则调用该方法可能会失败。

