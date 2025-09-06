
### getLocalPlayerUniqueID

**描述**: 获取本地玩家唯一标识。

**参数**: 无

**返回值**: `string` - 本地玩家唯一标识

**示例代码**:
```javascript
let playerID = getLocalPlayerUniqueID();
console.log("Local Player Unique ID: " + playerID);
```

**注意事项**: 无

---

### playerJump

**描述**: 玩家跳跃。

**参数**: 无

**返回值**: `boolean` - 跳跃成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didJump = playerJump();
console.log("Player Jumped: " + didJump);
```

**注意事项**: 无

---

### simulateClick

**描述**: 模拟点击。

**参数**: 无

**返回值**: `boolean` - 操作状态

**示例代码**:
```javascript
let status = simulateClick();
console.log("status: " + status);
```

**注意事项**: 无

---

### attackEntity

**描述**: 攻击指定实体。

**参数**:
- `id` - `string` - 实体的唯一标识
- `action` - `boolean` - 攻击动作标识

**返回值**: `boolean` - 攻击成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didAttack = attackEntity("entity123", true);
console.log("Entity Attacked: " + didAttack);
```

**注意事项**: 无

---

### interactEntity

**描述**: 交互指定实体。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `boolean` - 交互成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didInteract = interactEntity("entity123");
console.log("Entity Interacted: " + didInteract);
```

**注意事项**: 无

---

### buildBlock

**描述**: 在指定位置放置/点击方块。

**参数**:
- `id` - `string` - 玩家唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `side` - `number` - 方块的侧面

**返回值**: `boolean` - 放置/点击成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didBuild = buildBlock("block123", 10, 64, 10, 1);
console.log("Block Built: " + didBuild);
```

**注意事项**: 无

---

### destroyBlock

**描述**: 在指定位置破坏方块。

**参数**:
- `id` - `string` - 玩家唯一标识
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `side` - `number` - 方块的侧面

**返回值**: `boolean` - 破坏成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didDestroy = destroyBlock("block123", 10, 64, 10, 1);
console.log("Block Destroyed: " + didDestroy);
```

**注意事项**: 无

---

### setLocalPlayerTurn

**描述**: 设置本地玩家视角转向角度。

**参数**:
- `pitch` - `number` - 俯仰角
- `yaw` - `number` - 偏航角

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didSetRot = setLocalPlayerTurn(45, 90);
console.log("Player Rotation Set: " + didSetRot);
```

**注意事项**: 自`v7.0.3`版本后更改，原函数名称`setLocalPlayerRot`

---

### setCameraRotation

**描述**: 设置相机的旋转角度，允许用户指定俯仰、偏航和滚转角度。

**参数**:
- `pitch` - `number` - 俯仰角，控制相机的上下视角。
- `yaw` - `number` - 偏航角，控制相机的左右视角。
- `roll` - `number` - 滚转角，控制相机的旋转角度。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setCameraRotation(30.0, 45.0, 10.0);
```

**注意事项**: 确保提供合理的角度值，以避免相机视角异常。

---

### getCameraRotation

**描述**: 获取当前相机的旋转角度，返回包含俯仰、偏航和滚转角的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `pitch` - `number` - 当前相机的俯仰角。
- `yaw` - `number` - 当前相机的偏航角。
- `roll` - `number` - 当前相机的滚转角。

**示例代码**:
```javascript
let cameraRotation = getCameraRotation();
console.log(`Camera Rotation - Pitch: ${cameraRotation.pitch}, Yaw: ${cameraRotation.yaw}, Roll: ${cameraRotation.roll}`);
```

**注意事项**: 返回的角度值可用于设置相机的旋转角度或进一步的计算。

---

### setCameraPos

**描述**: 设置相机的位置，通过指定 x、y、z 坐标来定义相机的空间位置。

**参数**:
- `x` - `number` - 相机的 X 轴位置。
- `y` - `number` - 相机的 Y 轴位置。
- `z` - `number` - 相机的 Z 轴位置。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setCameraPos(10.0, 20.0, 5.0);
```

**注意事项**: 确保提供合理的坐标值，以避免相机位置异常。

---

### getCameraPos

**描述**: 获取当前相机的位置，返回包含 x、y、z 坐标的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `x` - `number` - 相机的 X 轴位置。
- `y` - `number` - 相机的 Y 轴位置。
- `z` - `number` - 相机的 Z 轴位置。

**示例代码**:
```javascript
let cameraPosition = getCameraPos();
console.log(`Camera Position - X: ${cameraPosition.x}, Y: ${cameraPosition.y}, Z: ${cameraPosition.z}`);
```

**注意事项**: 返回的位置数据可用于设置相机的新位置或其他位置计算。

---

### setCameraOffset

**描述**: 设置相机的偏移量，通过指定相对于当前相机位置的 x、y、z 偏移值来调整相机位置。

**参数**:
- `x` - `number` - 相对于当前 X 轴的偏移量。
- `y` - `number` - 相对于当前 Y 轴的偏移量。
- `z` - `number` - 相对于当前 Z 轴的偏移量。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setCameraOffset(5.0, 10.0, 2.0);
```

**注意事项**: 偏移量将基于当前相机位置进行调整，且不会改变相机的旋转角度。

---

### getCameraOffset

**描述**: 获取当前相机的偏移量，返回包含 x、y、z 偏移值的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `x` - `number` - 当前相机的 X 轴偏移量。
- `y` - `number` - 当前相机的 Y 轴偏移量。
- `z` - `number` - 当前相机的 Z 轴偏移量。

**示例代码**:
```javascript
let cameraOffset = getCameraOffset();
console.log(`Camera Offset - X: ${cameraOffset.x}, Y: ${cameraOffset.y}, Z: ${cameraOffset.z}`);
```

**注意事项**: 偏移值通常用于在当前相机位置的基础上进一步调整相机位置。

---

### getCameraPitchLimit

**描述**: 获取当前相机的俯仰角限制范围，返回包含最小和最大俯仰角度的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `x` - `number` - 相机俯仰角的最小限制。
- `y` - `number` - 相机俯仰角的最大限制。

**示例代码**:
```javascript
let pitchLimit = getCameraPitchLimit();
console.log(`Camera Pitch Limit - Min: ${pitchLimit.x}, Max: ${pitchLimit.y}`);
```

**注意事项**: 俯仰角限制用于定义相机的上下视角范围，有助于防止视角的过度倾斜。

---

### setCameraPitchLimit

**描述**: 设置相机的俯仰角度限制，通过指定最小和最大俯仰角来限制相机的上下视角范围。

**参数**:
- `x` - `number` - 相机俯仰角的最小限制。
- `y` - `number` - 相机俯仰角的最大限制。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setCameraPitchLimit(-45.0, 45.0);
```

**注意事项**: 提供合理的俯仰角限制，以确保相机视角不会出现过度倾斜。

---

### setCameraAnchor

**描述**: 设置相机的锚点，通过指定 x、y、z 坐标来定义相机的固定参考点。

**参数**:
- `x` - `number` - 相机锚点的 X 轴坐标。
- `y` - `number` - 相机锚点的 Y 轴坐标。
- `z` - `number` - 相机锚点的 Z 轴坐标。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setCameraAnchor(0.0, 5.0, 10.0);
```

**注意事项**: 确保提供合理的锚点坐标，以便在进行相机移动或旋转时保持稳定的参考点。

---

### getCameraAnchor

**描述**: 获取当前相机的锚点位置，返回包含 x、y、z 坐标的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `x` - `number` - 当前相机锚点的 X 轴坐标。
- `y` - `number` - 当前相机锚点的 Y 轴坐标。
- `z` - `number` - 当前相机锚点的 Z 轴坐标。

**示例代码**:
```javascript
let cameraAnchor = getCameraAnchor();
console.log(`Camera Anchor - X: ${cameraAnchor.x}, Y: ${cameraAnchor.y}, Z: ${cameraAnchor.z}`);
```

**注意事项**: 锚点坐标可用于计算相机移动或调整相机行为的基准位置。

---

### resetCamera

**描述**: 重置相机的位置和角度，将其恢复到默认状态。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
resetCamera();
console.log("Camera has been reset to default position and rotation.");
```

**注意事项**: 此操作将清除所有自定义的相机设置，包括位置、旋转和偏移量。

---

### lockCamera

**描述**: 锁定相机的当前视角和位置，防止其被移动或旋转。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
lockCamera();
console.log("Camera is now locked in its current position and rotation.");
```

**注意事项**: 锁定相机后，所有相关的相机控制功能将失效，直到相机被解锁。

---

### departCamera

**描述**: 解锁相机并使其恢复到可移动状态，允许用户重新控制相机。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
departCamera();
console.log("Camera is now unlocked and can be moved or rotated.");
```

**注意事项**: 在解锁相机后，用户可以自由调整相机的位置和旋转角度。

---

### swingArm

**描述**: 使手臂进行一次摆动。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
swingArm();
```

**注意事项**: 无。

---

### setPlayerViewPerspective

**描述**: 设置玩家的视角模式，以控制摄像机的视角和视图表现。

**参数**:
- `perspective` - `number` - 玩家视角模式的整数值，通常为以下之一：
  - `0` - 第一人称视角
  - `1` - 第三人称视角
  - `2` - 前视第三人称视角

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setPlayerViewPerspective(0); // 设置为第一人称视角
```

**注意事项**: 确保提供有效的视角模式值，以避免无效的视角设置。视角模式的具体定义可能因游戏或应用程序的不同而有所不同。

---

### getPlayerViewPerspective

**描述**: 获取当前玩家的视角模式，返回一个整数值，表示摄像机的视角类型。

**返回值**: `number` - 当前玩家视角模式的整数值，值包括：
- `0` - 第一人称视角
- `1` - 第三人称视角
- `2` - 前视第三人称视角

**示例代码**:
```javascript
let perspective = getPlayerViewPerspective();
if (perspective === 0) {
    console.log("Current Perspective: First Person");
} else if (perspective === 1) {
    console.log("Current Perspective: Third Person");
} else if (perspective === 2) {
    console.log("Current Perspective: Front Third Person");
}
```

**注意事项**: 返回的视角模式值依赖于游戏或应用程序的具体实现，确保根据需要处理的视角类型。

---

### openInventory

**描述**: 打开背包。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
openInventory();
```

**注意事项**: 打开背包之后不可立即操作。

---

### closeInventory

**描述**: 关闭背包。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
closeInventory();
```

**注意事项**: 无

---

### moveInventoryItem

**描述**: 移动背包物品。

**参数**:
- `fromSlot` - `number` - 物品所在格数
- `toSlot` - `number` - 目标物品所在格数

**返回值**: 无

**示例代码**:
```javascript
moveInventoryItem(1,2);
```

**注意事项**: 打开背包后才能移动，否则移动无效。

---

### moveContainerItem  

**描述**:  
移动容器内的物品，可在不同容器之间转移或在同一容器内调整物品位置。  

**参数**:  
- `items` - `Array<Object>` - 需要移动的物品列表，每个对象包含以下字段：  
  - `fromSlot` - `number` - 源物品所在的格索引  
  - `fromNetId` - `number` - 源物品的网络 ID  
  - `fromContainerId` - `ContainerID` - 源容器的 ID  
  - `toSlot` - `number` - 目标格索引  
  - `toNetId` - `number` - 目标物品的网络 ID（若目标格已有物品）  
  - `toContainerId` - `ContainerID` - 目标容器的 ID  
  - `count` - `number` - 要移动的物品数量  

**返回值**: 无  

**示例代码**:  
```javascript
const id = getLocalPlayerUniqueID();
const item1 = getPlayerInventoryItem(id,0);
const item2 = getPlayerInventoryItem(id,1);
// 假设 item1 和 item2 已经被解析为物品对象
const netid1 = item1.ExtraData.netId;
const netid2 = item2.ExtraData.netId;

moveContainerItem([
    {
        fromSlot:0,fromNetId:netid1,fromContainerId:7,
        toSlot:1,toNetId:netid2,toContainerId:7,count:1
    }
])
```  

**注意事项**:  
- 确保源容器和目标容器均已打开，否则操作无效。  
- `count` 不应超过 `fromSlot` 位置的物品数量，否则可能导致异常行为。  
- 若 `toSlot` 已有物品，可能进行交换、合并或覆盖，具体行为取决于实现逻辑。  

---  

### swapContainerItem

**描述**:  
交换两个容器内的物品。  

**参数**:
- `items` - `Array<Object>` - 需要移动的物品列表，每个对象包含以下字段：
    - `fromSlot` - `number` - 源物品所在的格索引
    - `fromNetId` - `number` - 源物品的网络 ID
    - `fromContainerId` - `ContainerID` - 源容器的 ID
    - `toSlot` - `number` - 目标格索引
    - `toNetId` - `number` - 目标物品的网络 ID（若目标格已有物品）
    - `toContainerId` - `ContainerID` - 目标容器的 ID
    - `count` - `number` - 要移动的物品数量

**返回值**: 无

**示例代码**:
```javascript
const id = getLocalPlayerUniqueID();
const item1 = getPlayerInventoryItem(id,0);
const item2 = getPlayerInventoryItem(id,1);
// 假设 item1 和 item2 已经被解析为物品对象
const netid1 = item1.ExtraData.netId;
const netid2 = item2.ExtraData.netId;

swapContainerItem([
    {
        fromSlot:0,fromNetId:netid1,fromContainerId:7,
        toSlot:1,toNetId:netid2,toContainerId:7,count:1
    }
])
```

**注意事项**:
- 确保源容器和目标容器均已打开，否则操作无效。
- `count` 不应超过 `fromSlot` 位置的物品数量，否则可能导致异常行为。
- 若 `toSlot` 已有物品，可能进行交换、合并或覆盖，具体行为取决于实现逻辑。

---

### getPlayerInventoryItem

**描述**: 获取玩家背包指定格数物品数据。

**参数**:
- `id` - `string` - 玩家唯一标识
- `slot` - `number` - 背包格数

**返回值**: `string` - 物品NBT数据

**示例代码**:
```javascript
let item = getPlayerInventoryItem("player123", 5);
console.log("Inventory Item: ", item);
```

**注意事项**: 无

---

### getPlayerInventorySize

**描述**: 获取玩家背包容量。

**参数**:
- `id` - `string` - 玩家唯一标识

**返回值**: `number` - 背包容量

**示例代码**:
```javascript
let inventorySize = getPlayerInventorySize("player123");
console.log("Inventory Size: " + inventorySize);
```

**注意事项**: 无

---

### getPlayerSelectItemSlot

**描述**: 获取玩家当前选择的格子。

**参数**:
- `id` - `string` - 玩家唯一标识

**返回值**: `number` - 目标格子

**示例代码**:
```javascript
let slot = getPlayerSelectItemSlot("player123");
console.log("Inventory Slot: " + slot);
```

**注意事项**: 无

---

### getPlayerHotBarSize

**描述**: 获取玩家快捷栏容量。

**参数**:
- `id` - `string` - 玩家唯一标识

**返回值**: `number` - 快捷栏容量

**示例代码**:
```javascript
let hotBarSize = getPlayerHotBarSize("player123");
console.log("Hot Bar Size: " + hotBarSize);
```

**注意事项**: 无

---

### selectPlayerInventorySlot

**描述**: 选择玩家物品栏栏位。

**参数**:
- `id` - `string` - 玩家唯一标识
- `slot` - `number` - 物品栏栏位

**返回值**: `boolean` - 选择成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didSelectSlot = selectPlayerInventorySlot("player123", 5);
console.log("Inventory Slot Selected: " + didSelectSlot);
```

**注意事项**: 无

---

### dropPlayerInventorySlot

**描述**: 丢弃玩家物品栏栏位物品。

**参数**:
- `id` - `string` - 玩家唯一标识
- `slot` - `number` - 物品栏栏位
- `onlyClearContainer` - `boolean` - 是否仅清空容器，默认为 `false`（可选）
- `dropAll` `boolean` - 是否丢弃所有物品，默认为 `true`（可选）

**返回值**: `boolean` - 丢弃成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didDropItem = dropPlayerInventorySlot("player123", 5);
console.log("Item Dropped: " + didDropItem);
```

**注意事项**: 无

---

### addInventoryItem

**描述**: 添加新物品到背包。

**参数**:
- `name` - `string` - 物品名称
- `count` - `number` - 物品数量
- `aux` - `number` - 附加数据

**返回值**: `boolean` - 添加成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didAddItem = addInventoryItem("diamond", 10, 0);
console.log("Item Added: " + didAddItem);
```

**注意事项**: 无

---

### addInventoryItemByNBT

**描述**: 通过 NBT 添加新物品到背包。

**参数**:
- `mojangson` - `string` - NBT 数据的字符串表示

**返回值**: `boolean` - 添加成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let didAddItemByNBT = addInventoryItemByNBT("{Name:\"diamond\",Count:10}");
console.log("Item Added By NBT: " + didAddItemByNBT);
```

**注意事项**: 确保传入的 NBT 数据字符串格式正确。

---

### getPlayerArmorItem

**描述**: 获取玩家护甲栏 NBT 数据。

**参数**:
- `id` - `string` - 玩家唯一标识
- `slot` - `number` - 护甲栏栏位

**返回值**: `string` - NBT数据

**示例代码**:
```javascript
let nbt = getPlayerArmorItem("123",0);
console.log("NBT: " + nbt);
```

**注意事项**: 无

---

### setPlayerArmorItem

**描述**: 通过 NBT 设置物品到护甲栏。

**参数**:
- `id` - `string` - 玩家唯一标识
- `mojangson` - `string` - NBT 数据的字符串表示

**返回值**: `boolean` - 添加成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let status = setPlayerArmorItem("123","{Name:\"diamond\",Count:10}");
console.log("status: " + status);
```

**注意事项**: 确保传入的 NBT 数据字符串格式正确。

---

### setLocalPlayerGameType

**描述**:
设置当前本地玩家的游戏模式类型。

**参数**:

* `gameType` (`number`) - 要设置的游戏模式类型，常用取值如下：

  * `0`：生存模式（Survival）
  * `1`：创造模式（Creative）
  * `2`：冒险模式（Adventure）
  * `3`：旁观者模式（Spectator）

**返回值**:
无返回值。

**示例代码**:

```javascript
setLocalPlayerGameType(1); // 将玩家设置为创造模式
```

**注意事项**:

* 请确保传入的数值在合法范围内，否则可能导致行为异常或无效。
* 该设置仅影响本地玩家。

---

### getLocalPlayerGameType

**描述**:
获取当前本地玩家的游戏模式类型。

**参数**:
无

**返回值**:
`number` - 返回玩家的游戏模式类型，通常对应以下数值：

* `0`：生存模式（Survival）
* `1`：创造模式（Creative）
* `2`：冒险模式（Adventure）
* `3`：旁观者模式（Spectator）
* `-1`：获取失败或玩家不存在

**示例代码**:

```javascript
let gameType = getLocalPlayerGameType();
console.log("当前游戏模式类型为:", gameType);
```

**注意事项**:

* 当玩家对象不存在时，将返回 `-1`。

---

### deleteContainer

**描述**:
清除本地玩家的容器管理器（Container Manager）。

**参数**:
无

**返回值**:
无返回值。

**示例代码**:

```javascript
deleteContainer();
```

**注意事项**:

* 该操作不可逆，请确保不再需要当前容器数据后再调用此函数。
* 仅对本地玩家有效。
