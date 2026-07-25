# Actor

实体对象。

---

### getUniqueID

获取实体的唯一 ID（Unique ID）。

#### 语法

```javascript
const uniqueId = actor.getUniqueID();
```

#### 返回值

| 类型     | 说明                                                                                              |
|----------|---------------------------------------------------------------------------------------------------|
| `string` | 实体唯一 ID。该值在不同实体之间唯一，可用于唯一标识一个实体。由于数值较大，因此以字符串形式返回。 |

#### 示例

```javascript
const uniqueId = actor.getUniqueID();

console.log(uniqueId);
```

---

### getRuntimeID

获取实体的运行时 ID（Runtime ID）。

#### 语法

```javascript
const runtimeId = actor.getRuntimeID();
```

#### 返回值

| 类型     | 说明                                                                                                  |
|----------|-------------------------------------------------------------------------------------------------------|
| `string` | 实体运行时 ID。该 ID 在实体存活期间唯一，通常用于运行时识别实体。由于数值较大，因此以字符串形式返回。 |

#### 示例

```javascript
const runtimeId = actor.getRuntimeID();

console.log(runtimeId);
```

#### 注意

- Runtime ID 仅在当前游戏运行期间有效，不应作为持久化数据保存。
- 如需持久唯一标识实体，请使用 `getUniqueID()`。

---

### getEffectList

获取实体当前拥有的所有状态效果列表。

#### 语法

```javascript
const effects = actor.getEffectList();
```

#### 返回值

| 类型            | 说明                                                       |
|-----------------|------------------------------------------------------------|
| `Array<Object>` | 状态效果对象数组。如果实体没有任何状态效果，则返回空数组。 |

#### Effect 对象结构

| 属性                              | 类型      | 说明                     |
|-----------------------------------|-----------|--------------------------|
| `id`                              | `number`  | 状态效果 ID              |
| `duration`                        | `number`  | 当前难度下的效果持续时间 |
| `durationEasy`                    | `number`  | 简单难度下的效果持续时间 |
| `durationNormal`                  | `number`  | 普通难度下的效果持续时间 |
| `durationHard`                    | `number`  | 困难难度下的效果持续时间 |
| `amplifier`                       | `number`  | 效果等级倍率             |
| `displayOnScreenTextureAnimation` | `boolean` | 是否显示屏幕上的效果动画 |
| `ambient`                         | `boolean` | 是否为环境效果           |
| `noCounter`                       | `boolean` | 是否隐藏持续时间计数器   |
| `effectVisible`                   | `boolean` | 是否显示效果图标         |

#### 示例

```javascript
const effects = actor.getEffectList();

for (const effect of effects) {
    console.log(
        `Effect ${effect.id}, Level ${effect.amplifier}, Duration ${effect.duration}`
    );
}
```

---

### getEffect

获取指定状态效果。

#### 语法

```javascript
const effect = actor.getEffect(id);
```

#### 参数

| 参数 | 类型     | 说明        |
|------|----------|-------------|
| `id` | `number` | 状态效果 ID |

#### 返回值

| 类型     | 说明                                             |
|----------|--------------------------------------------------|
| `Object` | 状态效果对象。如果实体不存在该效果，则无返回值。 |

#### Effect 对象结构

| 属性                              | 类型      | 说明                     |
|-----------------------------------|-----------|--------------------------|
| `id`                              | `number`  | 状态效果 ID              |
| `duration`                        | `number`  | 当前难度下的效果持续时间 |
| `durationEasy`                    | `number`  | 简单难度下的效果持续时间 |
| `durationNormal`                  | `number`  | 普通难度下的效果持续时间 |
| `durationHard`                    | `number`  | 困难难度下的效果持续时间 |
| `amplifier`                       | `number`  | 效果等级倍率             |
| `displayOnScreenTextureAnimation` | `boolean` | 是否显示屏幕上的效果动画 |
| `ambient`                         | `boolean` | 是否为环境效果           |
| `noCounter`                       | `boolean` | 是否隐藏持续时间计数器   |
| `effectVisible`                   | `boolean` | 是否显示效果图标         |

#### 示例

```javascript
const speed = actor.getEffect(1);

if (speed) {
    console.log(`Speed amplifier: ${speed.amplifier}`);
}
```

---

### addEffect

给实体添加状态效果。

#### 语法

```javascript
actor.addEffect(effect);
```

#### 参数

| 参数     | 类型     | 说明             |
|----------|----------|------------------|
| `effect` | `Object` | 状态效果配置对象 |

#### Effect 参数结构

| 属性                              | 类型      | 必填 | 说明                 |
|-----------------------------------|-----------|------|----------------------|
| `id`                              | `number`  | 是   | 状态效果 ID          |
| `duration`                        | `number`  | 否   | 当前难度持续时间     |
| `durationEasy`                    | `number`  | 否   | 简单难度持续时间     |
| `durationNormal`                  | `number`  | 否   | 普通难度持续时间     |
| `durationHard`                    | `number`  | 否   | 困难难度持续时间     |
| `amplifier`                       | `number`  | 否   | 效果等级倍率         |
| `displayOnScreenTextureAnimation` | `boolean` | 否   | 是否显示屏幕效果动画 |
| `ambient`                         | `boolean` | 否   | 是否为环境效果       |
| `noCounter`                       | `boolean` | 否   | 是否隐藏计时器       |
| `effectVisible`                   | `boolean` | 否   | 是否显示效果图标     |

#### 示例

```javascript
actor.addEffect({
    id: 1,
    duration: 600,
    amplifier: 2,
    effectVisible: true
});
```

#### 注意

- `id` 必须有效，否则会抛出异常。
- 未填写的参数将使用默认值。
- `duration` 单位为游戏 Tick。

---

### removeEffect

移除实体指定状态效果。

#### 语法

```javascript
const result = actor.removeEffect(id);
```

#### 参数

| 参数 | 类型     | 说明        |
|------|----------|-------------|
| `id` | `number` | 状态效果 ID |

#### 返回值

| 类型      | 说明               |
|-----------|--------------------|
| `boolean` | 是否成功移除效果。 |

#### 示例

```javascript
const removed = actor.removeEffect(1);

if (removed) {
    console.log("Effect removed");
}
```

---

### getStatusFlag

获取实体指定状态标志（Status Flag）的当前状态。

#### 语法

```javascript
const result = actor.getStatusFlag(flags);
```

#### 参数

| 参数    | 类型     | 说明                             |
|---------|----------|----------------------------------|
| `flags` | `number` | 状态标志枚举值（`ActorFlags`）。 |

#### 返回值

| 类型      | 说明                       |
|-----------|----------------------------|
| `boolean` | 返回指定状态标志是否启用。 |

#### 示例

```javascript
// 检查实体是否具有指定状态
const result = actor.getStatusFlag(1);

if (result) {
    console.log("状态已启用");
} else {
    console.log("状态未启用");
}
```

#### 异常

当参数错误或底层调用失败时会抛出异常：

```text
Error: Invalid arguments
```

#### 注意

- `flags` 参数需要传入有效的 `EntityFlag` 枚举值。
- 不同状态标志对应不同实体行为，请参考 `EntityFlag` 定义。

---

### setStatusFlag

设置实体指定状态标志。

#### 语法

```javascript
actor.setStatusFlag(flags, value);
```

#### 参数

| 参数    | 类型      | 说明                                            |
|---------|-----------|-------------------------------------------------|
| `flags` | `number`  | 状态标志枚举值（`EntityFlag`）。                |
| `value` | `boolean` | 是否启用该状态。`true` 为启用，`false` 为关闭。 |

#### 返回值

无返回值。

#### 示例

```javascript
// 开启指定状态
actor.setStatusFlag(1, true);

// 关闭指定状态
actor.setStatusFlag(1, false);
```

#### 异常

当参数错误或底层调用失败时会抛出异常：

```text
Error: Invalid arguments
```

#### 注意

- `setStatusFlag` 会立即修改实体状态。
- 使用前请确保目标状态标志适用于当前实体类型。
- `flags` 参数需要传入有效的 `EntityFlag` 枚举值。

---

### getCarriedItem

获取实体当前主手持有的物品。

#### 语法

```javascript
const item = actor.getCarriedItem();
```

#### 返回值

| 类型        | 说明                   |
|-------------|------------------------|
| `ItemStack` | 当前主手中的物品对象。 |

#### 示例

```javascript
const item = actor.getCarriedItem();

console.log(item.getName());
```

#### 注意

- 返回的是新的 `ItemStack` 对象。
- 修改返回的 `ItemStack` 不会自动同步到实体手中，需要使用 `setCarriedItem()` 设置回去。

---

### setCarriedItem

设置实体主手中的物品。

#### 语法

```javascript
actor.setCarriedItem(item);
```

#### 参数

| 参数   | 类型        | 说明                 |
|--------|-------------|----------------------|
| `item` | `ItemStack` | 要设置到主手的物品。 |

#### 示例

```javascript
const itemStack = new item.ItemStack();

actor.setCarriedItem(itemStack);
```

#### 异常

当传入参数不是 `ItemStack` 类型时会抛出异常。


---

### getOffhandItem

获取实体副手持有的物品。

#### 语法

```javascript
const item = actor.getOffhandItem();
```

#### 返回值

| 类型        | 说明                     |
|-------------|--------------------------|
| `ItemStack` | 当前副手中的物品堆对象。 |

#### 示例

```javascript
const item = actor.getOffhandItem();

console.log(item.getName());
```

---

### setOffhandItem

设置实体副手中的物品。

#### 语法

```javascript
actor.setOffhandItem(item);
```

#### 参数

| 参数   | 类型        | 说明                 |
|--------|-------------|----------------------|
| `item` | `ItemStack` | 要设置到副手的物品。 |

#### 示例

```javascript
const itemStack = new item.ItemStack();

actor.setOffhandItem(itemStack);
```

#### 异常

当传入参数不是 `ItemStack` 类型时会抛出异常。


---

### getArmorItem

获取实体指定装备栏中的装备。

#### 语法

```javascript
const item = actor.getArmorItem(slot);
```

#### 参数

| 参数   | 类型     | 说明                                  |
|--------|----------|---------------------------------------|
| `slot` | `number` | 装备栏位置，对应 `ArmorSlot` 枚举值。 |

#### 返回值

| 类型        | 说明                 |
|-------------|----------------------|
| `ItemStack` | 指定装备栏中的物品。 |

#### 示例

```javascript
const helmet = actor.getArmorItem(0);

console.log(helmet.getName());
```

#### ArmorSlot

| 值  | 说明 |
|-----|------|
| `0` | 头盔 |
| `1` | 胸甲 |
| `2` | 护腿 |
| `3` | 靴子 |

---

### setArmorItem

设置实体指定装备栏中的装备。

#### 语法

```javascript
actor.setArmorItem(slot, item);
```

#### 参数

| 参数   | 类型        | 说明                                  |
|--------|-------------|---------------------------------------|
| `slot` | `number`    | 装备栏位置，对应 `ArmorSlot` 枚举值。 |
| `item` | `ItemStack` | 要设置的装备物品。                    |

#### 示例

```javascript
const helmet = new item.ItemStack();

actor.setArmorItem(0, helmet);
```

#### 异常

以下情况会抛出异常：

- `slot` 不是数字类型。
- `item` 不是 `ItemStack` 类型。

---

### getAttribute

获取实体属性信息。

#### 语法

```javascript
const attribute = actor.getAttribute(name);
```

#### 参数

| 参数   | 类型     | 说明     |
|--------|----------|----------|
| `name` | `string` | 属性名称 |

#### 返回值

| 类型     | 说明         |
|----------|--------------|
| `object` | 属性信息对象 |

返回对象结构：

```txt
{
    current: number, // 当前值
    max: number,     // 最大值
    min: number      // 最小值
}
```

#### 示例

```javascript
const health = actor.getAttribute("minecraft:health");

console.log("当前生命值:", health.current);
console.log("最大生命值:", health.max);
console.log("最小生命值:", health.min);
```

#### 异常

当参数错误或属性不存在时会抛出异常：

```text
Invalid arguments
```

或：

```text
Invalid attribute
```

---

### setAttribute

设置实体属性值。

#### 语法

```javascript
actor.setAttribute(name, value);
```

#### 参数

| 参数    | 类型     | 说明           |
|---------|----------|----------------|
| `name`  | `string` | 属性名称       |
| `value` | `object` | 要修改的属性值 |

`value` 对象结构：

```text
{
    current: number, // 设置当前值
    max: number,     // 设置最大值
    min: number      // 设置最小值
}
```

其中所有字段均为可选，只会修改传入的字段。

#### 示例

#### 修改当前值

```javascript
actor.setAttribute("minecraft:health", {
    current: 20
});
```

#### 修改最大值

```javascript
actor.setAttribute("minecraft:health", {
    max: 100
});
```

#### 同时修改多个值

```javascript
actor.setAttribute("minecraft:health", {
    current: 80,
    max: 100,
    min: 0
});
```

#### 注意事项

- 未传入的字段不会被修改。
- 属性名称必须是实体已有属性，否则会抛出异常。
- 属性值必须为数字类型。
- 修改属性不会自动限制到 `min` 和 `max` 范围内，请自行确保数值合法。

#### 异常

当参数错误或属性不存在时会抛出异常：

```text
Invalid arguments
```

或：

```text
Invalid attribute
```

---

### getRotation

获取实体当前旋转角度。

#### 语法

```javascript
const rotation = actor.getRotation();
````

#### 返回值

| 属性    | 类型     | 说明                 |
|---------|----------|----------------------|
| `yaw`   | `number` | 水平旋转角（偏航角） |
| `pitch` | `number` | 垂直旋转角（俯仰角） |

#### 示例

```javascript
const rotation = actor.getRotation();

console.log(`Yaw: ${rotation.yaw}`);
console.log(`Pitch: ${rotation.pitch}`);
```

---

### getRotationPrev

获取实体上一帧的旋转角度。

#### 语法

```javascript
const rotation = actor.getRotationPrev();
```

#### 返回值

| 属性    | 类型     | 说明                 |
|---------|----------|----------------------|
| `yaw`   | `number` | 水平旋转角（偏航角） |
| `pitch` | `number` | 垂直旋转角（俯仰角） |

#### 示例

```javascript
const previousRotation = actor.getRotationPrev();

console.log(previousRotation);
```

---

### setRotation

设置实体当前旋转角度。

#### 语法

```javascript
actor.setRotation(rotation);
```

#### 参数

| 属性    | 类型     | 说明       |
|---------|----------|------------|
| `yaw`   | `number` | 水平旋转角 |
| `pitch` | `number` | 垂直旋转角 |

#### 示例

```javascript
actor.setRotation({
    yaw: 90,
    pitch: 0
});
```

#### 异常

当参数不是对象或无法转换为有效旋转数据时，会抛出异常：

```text
Invalid arguments
```

---

### setRotationPrev

设置实体上一帧旋转角度。

#### 语法

```javascript
actor.setRotationPrev(rotation);
```

#### 参数

| 属性    | 类型     | 说明       |
|---------|----------|------------|
| `yaw`   | `number` | 水平旋转角 |
| `pitch` | `number` | 垂直旋转角 |

#### 示例

```javascript
actor.setRotationPrev({
    yaw: 45,
    pitch: 10
});
```

#### 异常

当参数不是对象或无法转换为有效旋转数据时，会抛出异常：

```text
Invalid arguments
```

---

### getYBodyRotation

获取实体当前身体 Y 轴旋转角度。

#### 语法

```javascript
const rotation = actor.getYBodyRotation();
````

#### 返回值

| 类型     | 说明                                |
|----------|-------------------------------------|
| `number` | 实体当前身体在 Y 轴方向的旋转角度。 |

#### 示例

```javascript
const rotation = actor.getYBodyRotation();

console.log(`当前身体旋转角度: ${rotation}`);
```

---

### getYBodyRotationPrev

获取实体上一帧身体 Y 轴旋转角度。

#### 语法

```javascript
const rotation = actor.getYBodyRotationPrev();
```

#### 返回值

| 类型     | 说明                                  |
|----------|---------------------------------------|
| `number` | 实体上一帧身体在 Y 轴方向的旋转角度。 |

#### 示例

```javascript
const previousRotation = actor.getYBodyRotationPrev();

console.log(`上一帧身体旋转角度: ${previousRotation}`);
```

---

### setYBodyRotation

设置实体身体 Y 轴旋转角度。

#### 语法

```javascript
actor.setYBodyRotation(rotation);
```

#### 参数

| 参数       | 类型     | 说明                        |
|------------|----------|-----------------------------|
| `rotation` | `number` | 要设置的身体 Y 轴旋转角度。 |

#### 返回值

无。

#### 示例

```javascript
// 设置实体身体朝向 90 度
actor.setYBodyRotation(90);
```

#### 异常

当参数缺失或类型不是 `number` 时会抛出异常：

```text
Invalid arguments
```

---

### setYBodyRotationPrev

设置实体上一帧身体 Y 轴旋转角度。

#### 语法

```javascript
actor.setYBodyRotationPrev(rotation);
```

#### 参数

| 参数       | 类型     | 说明                              |
|------------|----------|-----------------------------------|
| `rotation` | `number` | 要设置的上一帧身体 Y 轴旋转角度。 |

#### 返回值

无。

#### 示例

```javascript
// 设置上一帧身体旋转角度
actor.setYBodyRotationPrev(45);
```

#### 异常

当参数缺失或类型不是 `number` 时会抛出异常：

```text
Invalid arguments
```

#### 注意

* `getYBodyRotation()` 与 `getYBodyRotationPrev()` 通常用于获取实体当前帧和上一帧的身体旋转状态。
* 修改 `setYBodyRotation()` 会影响实体当前身体朝向。
* 修改 `setYBodyRotationPrev()` 会影响上一帧旋转数据，主要用于动画插值或渲染相关逻辑。

---

### getYHeadRotation

获取实体头部 Y 轴旋转角度。

#### 语法

```javascript
const rotation = actor.getYHeadRotation();
```

#### 返回值

| 类型     | 说明                                              |
|----------|---------------------------------------------------|
| `number` | 当前实体头部在 Y 轴方向上的旋转角度。单位为角度。 |

#### 示例

```javascript
const rotation = actor.getYHeadRotation();

console.log(`Head rotation: ${rotation}`);
```

---

### getYHeadRotationPrev

获取实体上一帧头部 Y 轴旋转角度。

#### 语法

```javascript
const rotation = actor.getYHeadRotationPrev();
```

#### 返回值

| 类型     | 说明                                                |
|----------|-----------------------------------------------------|
| `number` | 上一帧实体头部在 Y 轴方向上的旋转角度。单位为角度。 |

#### 示例

```javascript
const prevRotation = actor.getYHeadRotationPrev();

console.log(`Previous head rotation: ${prevRotation}`);
```

---

### setYHeadRotation

设置实体头部 Y 轴旋转角度。

#### 语法

```javascript
actor.setYHeadRotation(rotation);
```

#### 参数

| 参数       | 类型     | 说明                                    |
|------------|----------|-----------------------------------------|
| `rotation` | `number` | 要设置的头部 Y 轴旋转角度，单位为角度。 |

#### 返回值

无。

#### 示例

```javascript
// 设置实体头部朝向 90 度方向
actor.setYHeadRotation(90);
```

#### 异常

当参数缺失或类型错误时，会抛出异常：

```text
Invalid arguments
```

---

### setYHeadRotationPrev

设置实体上一帧头部 Y 轴旋转角度。

#### 语法

```javascript
actor.setYHeadRotationPrev(rotation);
```

#### 参数

| 参数       | 类型     | 说明                                          |
|------------|----------|-----------------------------------------------|
| `rotation` | `number` | 要设置的上一帧头部 Y 轴旋转角度，单位为角度。 |

#### 返回值

无。

#### 示例

```javascript
// 设置上一帧头部旋转角度
actor.setYHeadRotationPrev(45);
```

#### 异常

当参数缺失或类型错误时，会抛出异常：

```text
Invalid arguments
```

---

### getPos

获取实体当前位置。

#### 语法

```javascript
const pos = actor.getPos();
```

#### 返回值

| 类型     | 说明             |
|----------|------------------|
| `object` | 实体当前位置坐标 |

返回对象：

| 属性 | 类型     | 说明   |
|------|----------|--------|
| `x`  | `number` | X 坐标 |
| `y`  | `number` | Y 坐标 |
| `z`  | `number` | Z 坐标 |

#### 示例

```javascript
const pos = actor.getPos();

console.log(`位置: ${pos.x}, ${pos.y}, ${pos.z}`);
```

---

### getPosPrev

获取实体上一帧的位置。

#### 语法

```javascript
const pos = actor.getPosPrev();
```

#### 返回值

| 类型     | 说明                 |
|----------|----------------------|
| `object` | 实体上一帧的位置坐标 |

返回对象：

| 属性 | 类型     | 说明   |
|------|----------|--------|
| `x`  | `number` | X 坐标 |
| `y`  | `number` | Y 坐标 |
| `z`  | `number` | Z 坐标 |

#### 示例

```javascript
const oldPos = actor.getPosPrev();

console.log(`上一帧位置: ${oldPos.x}, ${oldPos.y}, ${oldPos.z}`);
```

---

### setPos

设置实体当前位置。

#### 语法

```javascript
actor.setPos(pos);
```

#### 参数

| 参数  | 类型     | 说明         |
|-------|----------|--------------|
| `pos` | `object` | 目标位置坐标 |

`pos` 对象格式：

| 属性 | 类型     | 说明   |
|------|----------|--------|
| `x`  | `number` | X 坐标 |
| `y`  | `number` | Y 坐标 |
| `z`  | `number` | Z 坐标 |

#### 示例

```javascript
actor.setPos({
    x: 100,
    y: 64,
    z: 100
});
```

#### 异常

当参数格式错误时会抛出：

```text
Invalid arguments
```

---

### setPosPrev

设置实体上一帧位置。

#### 语法

```javascript
actor.setPosPrev(pos);
```

#### 参数

| 参数  | 类型     | 说明           |
|-------|----------|----------------|
| `pos` | `object` | 上一帧位置坐标 |

`pos` 对象格式：

| 属性 | 类型     | 说明   |
|------|----------|--------|
| `x`  | `number` | X 坐标 |
| `y`  | `number` | Y 坐标 |
| `z`  | `number` | Z 坐标 |

#### 示例

```javascript
actor.setPosPrev({
    x: 0,
    y: 70,
    z: 0
});
```

#### 注意

修改上一帧位置可能会影响实体移动插值效果。

---

### getMotion

获取实体当前运动速度。

#### 语法

```javascript
const motion = actor.getMotion();
```

#### 返回值

| 类型     | 说明             |
|----------|------------------|
| `object` | 实体当前速度向量 |

返回对象：

| 属性 | 类型     | 说明       |
|------|----------|------------|
| `x`  | `number` | X 方向速度 |
| `y`  | `number` | Y 方向速度 |
| `z`  | `number` | Z 方向速度 |

#### 示例

```javascript
const motion = actor.getMotion();

console.log(`速度: ${motion.x}, ${motion.y}, ${motion.z}`);
```

---

### setMotion

设置实体运动速度。

#### 语法

```javascript
actor.setMotion(motion);
```

#### 参数

| 参数     | 类型     | 说明     |
|----------|----------|----------|
| `motion` | `object` | 速度向量 |

`motion` 对象格式：

| 属性 | 类型     | 说明       |
|------|----------|------------|
| `x`  | `number` | X 方向速度 |
| `y`  | `number` | Y 方向速度 |
| `z`  | `number` | Z 方向速度 |

#### 示例

```javascript
// 设置向前移动
actor.setMotion({
    x: 0,
    y: 0.5,
    z: 1
});
```

#### 异常

当参数格式错误时会抛出：

```text
Invalid arguments
```

---

### getTypeId

获取实体类型 ID。

#### 语法

```javascript
const typeId = actor.getTypeId();
```

#### 返回值

| 类型     | 说明                                  |
|----------|---------------------------------------|
| `number` | 实体类型 ID。用于区分不同类型的实体。 |

#### 示例

```javascript
const typeId = actor.getTypeId();

console.log(typeId);
```

---

### getIdentifier

获取实体标识信息。

#### 语法

```javascript
const identifier = actor.getIdentifier();
```

#### 返回值

| 类型     | 说明           |
|----------|----------------|
| `object` | 实体标识对象。 |

返回对象结构：

| 属性            | 类型     | 说明             |
|-----------------|----------|------------------|
| `namespace`     | `string` | 命名空间。       |
| `identifier`    | `string` | 实体标识名称。   |
| `initEvent`     | `string` | 初始化事件名称。 |
| `fullName`      | `string` | 完整名称。       |
| `canonicalName` | `string` | 标准名称。       |

#### 示例

```javascript
const identifier = actor.getIdentifier();

console.log(identifier.namespace);
console.log(identifier.identifier);
console.log(identifier.fullName);
```

返回示例：

```json
{
  "namespace": "minecraft",
  "identifier": "zombie",
  "initEvent": "",
  "fullName": "minecraft:zombie",
  "canonicalName": "minecraft:zombie"
}
```

---

### getName

获取实体名称。

#### 语法

```javascript
const name = actor.getName();
```

#### 返回值

| 类型     | 说明           |
|----------|----------------|
| `string` | 实体当前名称。 |

#### 示例

```javascript
const name = actor.getName();

console.log(name);
```

---

### setName

设置实体显示名称。

#### 语法

```javascript
actor.setName(name);
```

#### 参数

| 参数   | 类型     | 说明               |
|--------|----------|--------------------|
| `name` | `string` | 要设置的实体名称。 |

#### 示例

```javascript
actor.setName("测试实体");
```

#### 注意

- 设置的名称会作为实体名称标签显示。
- 参数必须为字符串类型，否则会抛出异常。

---

### getSize

获取实体尺寸。

#### 语法

```javascript
const size = actor.getSize();
```

#### 返回值

| 类型     | 说明           |
|----------|----------------|
| `object` | 实体尺寸信息。 |

返回对象结构：

| 属性 | 类型     | 说明       |
|------|----------|------------|
| `x`  | `number` | 实体宽度。 |
| `y`  | `number` | 实体高度。 |

#### 示例

```javascript
const size = actor.getSize();

console.log(size.x);
console.log(size.y);
```

返回示例：

```json
{
  "x": 0.6,
  "y": 1.8
}
```

---

### setSize

设置实体尺寸。

#### 语法

```javascript
actor.setSize(size);
```

#### 参数

| 参数   | 类型     | 说明       |
|--------|----------|------------|
| `size` | `object` | 尺寸对象。 |

`size` 对象结构：

| 属性 | 类型     | 说明       |
|------|----------|------------|
| `x`  | `number` | 实体宽度。 |
| `y`  | `number` | 实体高度。 |

#### 示例

```javascript
actor.setSize({
    x: 1,
    y: 2
});
```

#### 注意

- `size` 必须为对象类型。
- 对象必须包含有效的 `x` 和 `y` 数值。
- 设置尺寸可能影响实体碰撞箱。

---

### getAABB

获取实体的轴对齐包围盒（Axis-Aligned Bounding Box, AABB）。

#### 语法

```javascript
const aabb = actor.getAABB();
```

#### 返回值

| 类型     | 说明                   |
|----------|------------------------|
| `object` | 实体的轴对齐包围盒信息 |

返回对象结构：

```text
{
    lower: {
        x: number,
        y: number,
        z: number
    },
    upper: {
        x: number,
        y: number,
        z: number
    }
}
```

| 字段    | 类型     | 说明           |
|---------|----------|----------------|
| `lower` | `object` | 包围盒最小坐标 |
| `upper` | `object` | 包围盒最大坐标 |
| `x`     | `number` | X 轴坐标       |
| `y`     | `number` | Y 轴坐标       |
| `z`     | `number` | Z 轴坐标       |

#### 示例

```javascript
const aabb = actor.getAABB();

console.log(
    `实体范围: (${aabb.lower.x}, ${aabb.lower.y}, ${aabb.lower.z}) ~ (${aabb.upper.x}, ${aabb.upper.y}, ${aabb.upper.z})`
);
```

---

### getAdditionalSaveData

获取实体额外保存数据（Additional Save Data）。

该接口返回实体通过 `addAdditionalSaveData` 写入的 NBT 数据。

#### 语法

```javascript
const nbt = actor.getAdditionalSaveData();
```

#### 返回值

| 类型     | 说明                      |
|----------|---------------------------|
| `string` | Mojangson 格式的 NBT 数据 |

#### 示例

```javascript
const data = actor.getAdditionalSaveData();

console.log(data);
```

#### 注意

- 返回内容为 Mojangson 格式字符串。
- 该数据仅包含实体额外保存数据，不包含完整实体 NBT。
- 如需获取完整实体 NBT，请使用 `getNBT()`。

---

### setNBT

设置实体 NBT 数据。

#### 语法

```javascript
actor.setNBT(nbt);
```

#### 参数

| 参数  | 类型     | 必填 | 说明                      |
|-------|----------|------|---------------------------|
| `nbt` | `string` | 是   | Mojangson 格式的 NBT 数据 |

#### 示例

```javascript
actor.setNBT(`
{
    Pos: [0.0, 100.0, 0.0],
    Health: 20.0
}
`);
```

#### 异常

当参数无效时会抛出异常：

```text
Error: Invalid arguments
```

当 NBT 数据无法解析时会抛出异常：

```text
Error: Invalid NBT
```

#### 注意

- 修改 NBT 可能影响实体状态，请谨慎使用。
- 传入的数据必须符合 Mojangson 格式。

---

### getNBT

获取实体完整 NBT 数据。

#### 语法

```javascript
const nbt = actor.getNBT();
```

#### 返回值

| 类型     | 说明                              |
|----------|-----------------------------------|
| `string` | Mojangson 格式的完整实体 NBT 数据 |

#### 示例

```javascript
const nbt = actor.getNBT();

console.log(nbt);
```

#### 注意

- 返回的数据包含实体保存所需的完整 NBT 信息。
- 可配合 `setNBT()` 实现实体数据复制或修改。
- 返回格式为 Mojangson 字符串。

---

### isOnGround

判断实体当前是否在地面上。

#### 语法

```javascript
const result = actor.isOnGround();
```

#### 返回值

| 类型      | 说明                                                              |
|-----------|-------------------------------------------------------------------|
| `boolean` | 实体是否处于地面状态。`true` 表示在地面，`false` 表示未接触地面。 |

#### 示例

```javascript
if (actor.isOnGround()) {
    console.log("实体正在地面上");
}
```

---

### setIsOnGround

设置实体的地面状态。

#### 语法

```javascript
actor.setIsOnGround(value);
```

#### 参数

| 名称    | 类型      | 说明                   |
|---------|-----------|------------------------|
| `value` | `boolean` | 是否设置为在地面状态。 |

#### 返回值

无。

#### 示例

```javascript
// 设置实体为在地面状态
actor.setIsOnGround(true);
```

#### 异常

当参数缺失或类型不是 `boolean` 时，会抛出异常：

```
Invalid arguments
```

---

### wasOnGroundFlag

获取实体上一 tick 的地面状态。

#### 语法

```javascript
const result = actor.wasOnGroundFlag();
```

#### 返回值

| 类型      | 说明                         |
|-----------|------------------------------|
| `boolean` | 实体上一帧是否处于地面状态。 |

#### 示例

```javascript
if (actor.wasOnGroundFlag()) {
    console.log("实体上一帧在地面");
}
```

---

### setWasOnGroundFlag

设置实体上一 tick 的地面状态。

#### 语法

```javascript
actor.setWasOnGroundFlag(value);
```

#### 参数

| 名称    | 类型      | 说明                       |
|---------|-----------|----------------------------|
| `value` | `boolean` | 是否设置上一帧为地面状态。 |

#### 返回值

无。

#### 示例

```javascript
actor.setWasOnGroundFlag(false);
```

#### 异常

当参数缺失或类型不是 `boolean` 时，会抛出异常：

```
Invalid arguments
```

---

### isInWater

判断实体是否位于水中。

#### 语法

```javascript
const result = actor.isInWater();
```

#### 返回值

| 类型      | 说明                                |
|-----------|-------------------------------------|
| `boolean` | 实体是否在水中。`true` 表示在水中。 |

#### 示例

```javascript
if (actor.isInWater()) {
    console.log("实体正在水中");
}
```

---

### isInLava

判断实体是否位于岩浆中。

#### 语法

```javascript
const result = actor.isInLava();
```

#### 返回值

| 类型      | 说明                                    |
|-----------|-----------------------------------------|
| `boolean` | 实体是否在岩浆中。`true` 表示在岩浆中。 |

#### 示例

```javascript
if (actor.isInLava()) {
    console.log("实体正在岩浆中");
}
```

---

### remove

移除当前实体。

#### 语法

```javascript
actor.remove();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
const actor = getActor();

actor.remove();
```

#### 注意

- 调用后实体将被移除。
- 该操作为同步执行，会直接调用底层实体的 `remove()` 方法。
- 移除后的实体不应继续使用。

---

### removeAsync

异步移除当前实体。

#### 语法

```javascript
actor.removeAsync();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
const actor = getActor();

actor.removeAsync();
```

#### 注意

- 与 `remove()` 不同，该方法通过实体列表管理模块异步处理实体移除。
- 适用于需要延迟处理或避免直接操作实体生命周期的场景。
- 移除操作不会立即完成。

---

### isRemoved

判断实体是否已经被移除。

#### 语法

```javascript
const removed = actor.isRemoved();
```

#### 返回值

| 类型      | 说明                                              |
|-----------|---------------------------------------------------|
| `boolean` | `true` 表示实体已被移除，`false` 表示实体仍存在。 |

#### 示例

```javascript
if (actor.isRemoved()) {
    console.log("实体已移除");
}
```

---

### isAlive

判断实体是否仍然存活。

#### 语法

```javascript
const alive = actor.isAlive();
```

#### 返回值

| 类型      | 说明                                                  |
|-----------|-------------------------------------------------------|
| `boolean` | `true` 表示实体存活，`false` 表示实体不存在或已死亡。 |

#### 示例

```javascript
if (actor.isAlive()) {
    console.log("实体正在存活");
}
```

---

### getCategory

获取实体类别。

#### 语法

```javascript
const category = actor.getCategory();
```

#### 返回值

| 类型     | 说明                                     |
|----------|------------------------------------------|
| `string` | 实体类别标识。返回类别数值对应的字符串。 |

#### 示例

```javascript
const category = actor.getCategory();

console.log(category);
```

#### 注意

- 返回值为字符串类型，即使底层数据为整数。

---

### setModelName

设置实体模型名称。

该接口会向游戏发送模型修改数据，使指定实体切换到指定模型。

#### 语法

```javascript
actor.setModelName(name);
````

#### 参数

| 参数   | 类型     | 说明       |
|--------|----------|------------|
| `name` | `string` | 模型名称。 |

#### 返回值

无。

#### 示例

```javascript
// 设置实体模型为指定模型
actor.setModelName("minecraft:custom_model");
```

#### 注意

* 参数必须为字符串类型。
* 调用后会发送模型修改数据包。
* 修改效果取决于客户端是否存在对应模型资源。

---

### setModelTexture

设置实体模型贴图。

该接口会向游戏发送贴图修改数据，使指定实体使用指定纹理。

#### 语法

```javascript
actor.setModelTexture(texture);
```

#### 参数

| 参数      | 类型     | 说明           |
|-----------|----------|----------------|
| `texture` | `string` | 模型贴图名称。 |

#### 返回值

无。

#### 示例

```javascript
// 设置实体贴图
actor.setModelTexture("textures/entity/custom_texture");
```

#### 注意

* 参数必须为字符串类型。
* 贴图资源需要客户端已加载，否则可能无法正常显示。

---

### setTarget

设置实体目标。

#### 语法

```javascript
actor.setTarget(target);
```

#### 参数

| 参数     | 类型    | 说明                     |
|----------|---------|--------------------------|
| `target` | `Actor` | 要设置为目标的实体对象。 |

#### 返回值

无。

#### 示例

```javascript
const player = world.getPlayer();

actor.setTarget(player);
```

#### 注意

* 参数必须为 `Actor` 类型对象。
* 目标实体需要有效。

---

### getTarget

获取实体当前目标。

#### 语法

```javascript
const target = actor.getTarget();
```

#### 返回值

| 类型    | 说明                                                         |
|---------|--------------------------------------------------------------|
| `Actor` | 当前目标实体。如果没有目标或目标不存在，则返回 `undefined`。 |

#### 示例

```javascript
const target = actor.getTarget();

if (target) {
    console.log(target.getUniqueID());
}
```

#### 注意

* 返回的对象为新的 `Actor` API 实例。
* 如果目标实体已经不存在，则不会返回对象。

---

### startRiding

让实体骑乘指定目标实体。

#### 语法

```javascript
actor.startRiding(target);
````

#### 参数

| 参数   | 类型    | 说明               |
|--------|---------|--------------------|
| target | `Actor` | 要骑乘的目标实体。 |

#### 返回值

无。

#### 示例

```javascript
const vehicle = world.getPlayers()[0];

player.startRiding(vehicle);
```

#### 注意

* 调用后当前实体会尝试骑乘目标实体。
* 目标实体必须为有效的 `Actor` 对象。
* 如果参数类型错误，将抛出异常。

---

### stopRiding

停止当前实体的骑乘状态。

#### 语法

```javascript
actor.stopRiding();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
player.stopRiding();
```

---

### getVehicle

获取当前实体正在骑乘的载具或目标实体。

#### 语法

```javascript
const vehicle = actor.getVehicle();
```

#### 返回值

| 类型    | 说明                                                         |
|---------|--------------------------------------------------------------|
| `Actor` | 当前骑乘的实体。如果当前未骑乘任何实体，则返回 `undefined`。 |

#### 示例

```javascript
const vehicle = player.getVehicle();

if (vehicle) {
    console.log("正在骑乘实体:", vehicle.getUniqueID());
}
```

#### 注意

* 返回的对象为新的 `Actor` 实例引用。
* 如果实体当前没有骑乘目标，则不会返回对象。

---

### swing

执行实体挥手动作。

#### 语法

```javascript
actor.swing();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
player.swing();
```

---

### getFallDistance

获取实体当前记录的摔落距离。

#### 语法

```javascript
const distance = actor.getFallDistance();
```

#### 返回值

| 类型     | 说明               |
|----------|--------------------|
| `number` | 实体当前摔落距离。 |

#### 示例

```javascript
const distance = player.getFallDistance();

console.log("摔落距离:", distance);
```

---

### setFallDistance

设置实体的摔落距离。

#### 语法

```javascript
actor.setFallDistance(distance);
```

#### 参数

| 参数     | 类型     | 说明             |
|----------|----------|------------------|
| distance | `number` | 设置的摔落距离。 |

#### 返回值

无。

#### 示例

```javascript
player.setFallDistance(0);
```

#### 注意

* 设置为 `0` 可以清除当前摔落距离记录。
* 参数必须为数字类型，否则会抛出异常。

---

### isSneaking

获取实体是否正在潜行。

#### 语法

```javascript
const sneaking = actor.isSneaking();
```

#### 返回值

| 类型      | 说明                                          |
|-----------|-----------------------------------------------|
| `boolean` | `true` 表示实体正在潜行，`false` 表示未潜行。 |

#### 示例

```javascript
if (player.isSneaking()) {
    console.log("玩家正在潜行");
}
```

---

### setSneaking

设置实体潜行状态。

#### 语法

```javascript
actor.setSneaking(value);
```

#### 参数

| 参数  | 类型      | 说明               |
|-------|-----------|--------------------|
| value | `boolean` | 是否开启潜行状态。 |

#### 返回值

无。

#### 示例

```javascript
// 开启潜行
player.setSneaking(true);

// 关闭潜行
player.setSneaking(false);
```

#### 注意

* 参数必须为布尔类型，否则会抛出异常。

---

### isGliding

判断生物是否正在滑翔。

#### 语法

```javascript
const gliding = mob.isGliding();
````

#### 返回值

| 类型      | 说明                                            |
|-----------|-------------------------------------------------|
| `boolean` | 如果实体正在滑翔返回 `true`，否则返回 `false`。 |

#### 示例

```javascript
if (mob.isGliding()) {
    console.log("实体正在滑翔");
}
```

---

### isEating

判断生物是否正在进食。

#### 语法

```javascript
const eating = mob.isEating();
```

#### 返回值

| 类型      | 说明                                            |
|-----------|-------------------------------------------------|
| `boolean` | 如果实体正在进食返回 `true`，否则返回 `false`。 |

#### 示例

```javascript
if (mob.isEating()) {
    console.log("实体正在吃东西");
}
```

---

### isUsingItem

判断生物是否正在使用物品。

#### 语法

```javascript
const using = mob.isUsingItem();
```

#### 返回值

| 类型      | 说明                                                |
|-----------|-----------------------------------------------------|
| `boolean` | 如果实体正在使用物品返回 `true`，否则返回 `false`。 |

#### 示例

```javascript
if (mob.isUsingItem()) {
    console.log("实体正在使用物品");
}
```

---

### setSprinting

设置生物是否处于疾跑状态。

#### 语法

```javascript
mob.setSprinting(value);
```

#### 参数

| 参数    | 类型      | 说明               |
|---------|-----------|--------------------|
| `value` | `boolean` | 是否开启疾跑状态。 |

#### 返回值

无。

#### 示例

```javascript
// 开启疾跑
mob.setSprinting(true);

// 关闭疾跑
mob.setSprinting(false);
```

#### 异常

如果参数不是 `boolean` 类型，将抛出异常：

```text
Invalid arguments
```

---

### isSprinting

判断生物是否正在疾跑。

#### 语法

```javascript
const sprinting = mob.isSprinting();
```

#### 返回值

| 类型      | 说明                                            |
|-----------|-------------------------------------------------|
| `boolean` | 如果实体正在疾跑返回 `true`，否则返回 `false`。 |

#### 示例

```javascript
if (mob.isSprinting()) {
    console.log("实体正在疾跑");
}
```

---

### getItemUseDuration

获取生物当前使用物品的持续时间。

#### 语法

```javascript
const duration = mob.getItemUseDuration();
```

#### 返回值

| 类型     | 说明                   |
|----------|------------------------|
| `number` | 当前物品使用持续时间。 |

#### 示例

```javascript
const duration = mob.getItemUseDuration();

console.log(`使用时间: ${duration}`);
```

---

### getDimensionId

获取实体所在维度 ID。

#### 语法

```javascript
const dimensionId = actor.getDimensionId();
```

#### 返回值

| 类型     | 说明                    |
|----------|-------------------------|
| `number` | 实体当前所在维度的 ID。 |

#### 示例

```javascript
console.log(actor.getDimensionId());
```

---

### jumpFromGround

使生物执行跳跃动作。

#### 语法

```javascript
mob.jumpFromGround();
```

#### 返回值

无。

#### 示例

```javascript
mob.jumpFromGround();
```

---

### getDimension

获取实体所在的维度对象。

#### 语法

```javascript
const dimension = actor.getDimension();
```

#### 返回值

| 类型        | 说明                     |
|-------------|--------------------------|
| `Dimension` | 实体当前所在的维度对象。 |

#### 示例

```javascript
const dimension = actor.getDimension();

console.log(dimension);
```

#### 注意

* 返回对象为 `world` 模块中的 `Dimension` 实例。
* 可通过该对象调用维度相关 API。

---

### getWorld

获取实体所属的世界对象。

#### 语法

```javascript
const world = actor.getWorld();
```

#### 返回值

| 类型    | 说明               |
|---------|--------------------|
| `Level` | 实体所属世界对象。 |

#### 示例

```javascript
const world = actor.getWorld();

console.log(world);
```

#### 注意

* 返回对象为 `world` 模块中的 `Level` 实例。
* 可通过该对象访问世界相关 API。

---









