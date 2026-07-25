`item` 模块提供 Minecraft 物品堆栈（ItemStack）相关 API，用于创建、读取以及修改物品的属性，包括物品 ID、数量、附加值、耐久度、NBT
数据以及方块物品信息等。

通过 `require` 获取：

```javascript
const {ItemStack} = require("item");
````

---

## ItemStack

表示一个 Minecraft 物品堆栈。

#### 构造方法

##### 语法

```javascript
new ItemStack();
```

##### 示例

创建一个空物品：

```javascript
const {ItemStack} = require("item");

const item = new ItemStack();
```

---

## isNull

判断当前物品是否为空。

#### 语法

```javascript
item.isNull();
```

#### 返回值

| 类型    | 说明         |
|---------|--------------|
| boolean | 是否为空物品 |

#### 示例

```javascript
if (item.isNull()) {
    console.log("物品为空");
}
```

---

## getName

获取物品名称。

#### 语法

```javascript
item.getName();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| string | 物品名称 |

#### 示例

```javascript
console.log(item.getName());
```

---

## getDamage

获取物品当前耐久值。

#### 语法

```javascript
item.getDamage();
```

#### 返回值

| 类型   | 说明       |
|--------|------------|
| number | 当前耐久值 |

---

## getMaxDamage

获取物品最大耐久值。

#### 语法

```javascript
item.getMaxDamage();
```

#### 返回值

| 类型   | 说明       |
|--------|------------|
| number | 最大耐久值 |

---

## getAttackDamage

获取物品攻击伤害。

#### 语法

```javascript
item.getAttackDamage();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 攻击伤害 |

---

## getId

获取物品 ID。

#### 语法

```javascript
item.getId();
```

#### 返回值

| 类型   | 说明    |
|--------|---------|
| number | 物品 ID |

---

## setId

设置物品 ID。

#### 语法

```javascript
item.setId(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 物品 ID |

#### 返回值

无。

#### 示例

```javascript
item.setId(1);
```

---

## getAux

获取物品附加值（Aux）。

#### 语法

```javascript
item.getAux();
```

#### 返回值

| 类型   | 说明   |
|--------|--------|
| number | 附加值 |

---

## setAux

设置物品附加值。

#### 语法

```javascript
item.setAux(aux);
```

#### 参数

| 参数 | 类型   | 必填 | 说明   |
|------|--------|------|--------|
| aux  | number | 是   | 附加值 |

#### 返回值

无。

---

## getCount

获取物品数量。

#### 语法

```javascript
item.getCount();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| number | 物品数量 |

---

## setCount

设置物品数量。

#### 语法

```javascript
item.setCount(count);
```

#### 参数

| 参数  | 类型   | 必填 | 说明 |
|-------|--------|------|------|
| count | number | 是   | 数量 |

#### 返回值

无。

---

## getMaxStackSize

获取物品最大堆叠数量。

#### 语法

```javascript
item.getMaxStackSize();
```

#### 返回值

| 类型   | 说明         |
|--------|--------------|
| number | 最大堆叠数量 |

---

## getMaxUseDuration

获取物品最大使用时间。

#### 语法

```javascript
item.getMaxUseDuration();
```

#### 返回值

| 类型   | 说明         |
|--------|--------------|
| number | 最大使用时间 |

---

## getNetId

获取物品网络 ID。

#### 语法

```javascript
item.getNetId();
```

#### 返回值

| 类型   | 说明    |
|--------|---------|
| number | 网络 ID |

---

## isBlock

判断物品是否为方块。

#### 语法

```javascript
item.isBlock();
```

#### 返回值

| 类型    | 说明       |
|---------|------------|
| boolean | 是否为方块 |

---

## getBlock

获取物品对应的方块对象。

仅当物品为方块时可调用。

#### 语法

```javascript
item.getBlock();
```

#### 返回值

| 类型  | 说明         |
|-------|--------------|
| Block | 对应方块对象 |

#### 异常

如果物品不是方块，将抛出异常。

#### 示例

```javascript
if (item.isBlock()) {
    const block = item.getBlock();
}
```

---

## getBlockRuntimeId

获取方块运行时 ID。

仅当物品为方块时可调用。

#### 语法

```javascript
item.getBlockRuntimeId();
```

#### 返回值

| 类型   | 说明            |
|--------|-----------------|
| number | 方块 Runtime ID |

---

## getUserData

获取物品用户数据（NBT）。

返回 Mojangson 格式字符串。

#### 语法

```javascript
item.getUserData();
```

#### 返回值

| 类型   | 说明     |
|--------|----------|
| string | NBT 数据 |

#### 异常

如果物品没有用户数据，将抛出异常。

---

## setUserData

设置物品用户数据（NBT）。

#### 语法

```javascript
item.setUserData(nbt);
```

#### 参数

| 参数 | 类型   | 必填 | 说明               |
|------|--------|------|--------------------|
| nbt  | string | 是   | Mojangson 格式 NBT |

#### 返回值

无。

#### 示例

```javascript
item.setUserData('{display:{Name:"测试物品"}}');
```

---

## getNBT

获取完整物品 NBT 数据。

#### 语法

```javascript
item.getNBT();
```

#### 返回值

| 类型   | 说明               |
|--------|--------------------|
| string | Mojangson 格式 NBT |

#### 示例

```javascript
console.log(item.getNBT());
```

---

## setNBT

通过 NBT 设置完整物品数据。

#### 语法

```javascript
item.setNBT(nbt);
```

#### 参数

| 参数 | 类型   | 必填 | 说明               |
|------|--------|------|--------------------|
| nbt  | string | 是   | Mojangson 格式 NBT |

#### 返回值

无。

#### 示例

```javascript
item.setNBT('{Count:1,id:"minecraft:diamond"}');
```
