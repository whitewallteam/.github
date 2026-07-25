`options` 模块提供 Minecraft 游戏选项相关 API，可以读取和修改客户端配置，包括布尔、整数、浮点数、字符串选项，以及不同输入模式下的选项配置和玩家视角设置。

通过 `require` 获取：

```javascript
const options = require("options");
````

---

### getBoolean

获取布尔类型选项。

#### 语法

```javascript
options.getBoolean(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性         | 类型    | 说明   |
|--------------|---------|--------|
| value        | boolean | 当前值 |
| defaultValue | boolean | 默认值 |

#### 示例

```javascript
const options = require("options");

const value = options.getBoolean(1);

console.log(value.value);
```

---

### setBoolean

设置布尔类型选项。

#### 语法

```javascript
options.setBoolean(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

`value` 对象支持：

| 属性         | 类型    | 说明   |
|--------------|---------|--------|
| value        | boolean | 当前值 |
| defaultValue | boolean | 默认值 |

#### 示例

```javascript
options.setBoolean(1, {
    value: true
});
```

---

### getInt

获取整数类型选项。

#### 语法

```javascript
options.getInt(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| minValue     | number | 最小值 |
| maxValue     | number | 最大值 |
| currentValue | number | 当前值 |
| defaultValue | number | 默认值 |

#### 示例

```javascript
const option = options.getInt(2);

console.log(option.currentValue);
```

---

### setInt

设置整数类型选项。

#### 语法

```javascript
options.setInt(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

`value` 对象支持：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| minValue     | number | 最小值 |
| maxValue     | number | 最大值 |
| currentValue | number | 当前值 |
| defaultValue | number | 默认值 |

#### 示例

```javascript
options.setInt(2, {
    currentValue: 10
});
```

---

### getFloat

获取浮点类型选项。

#### 语法

```javascript
options.getFloat(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| minValue     | number | 最小值 |
| maxValue     | number | 最大值 |
| currentValue | number | 当前值 |
| defaultValue | number | 默认值 |

#### 示例

```javascript
const option = options.getFloat(3);

console.log(option.currentValue);
```

---

### setFloat

设置浮点类型选项。

#### 语法

```javascript
options.setFloat(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

`value` 对象支持：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| minValue     | number | 最小值 |
| maxValue     | number | 最大值 |
| currentValue | number | 当前值 |
| defaultValue | number | 默认值 |

#### 示例

```javascript
options.setFloat(3, {
    currentValue: 0.5
});
```

---

### getString

获取字符串类型选项。

#### 语法

```javascript
options.getString(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| value        | string | 当前值 |
| defaultValue | string | 默认值 |

#### 示例

```javascript
const option = options.getString(4);

console.log(option.value);
```

---

### setString

设置字符串类型选项。

#### 语法

```javascript
options.setString(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

`value` 对象支持：

| 属性         | 类型   | 说明   |
|--------------|--------|--------|
| value        | string | 当前值 |
| defaultValue | string | 默认值 |

#### 示例

```javascript
options.setString(4, {
    value: "example"
});
```

---

### getInputModeBool

获取输入模式布尔选项。

#### 语法

```javascript
options.getInputModeBool(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性          | 类型  | 说明           |
|---------------|-------|----------------|
| values        | array | 当前输入模式值 |
| defaultValues | array | 默认输入模式值 |

数组元素结构：

| 属性  | 类型    | 说明         |
|-------|---------|--------------|
| name  | string  | 输入模式名称 |
| id    | number  | 输入模式 ID  |
| value | boolean | 对应值       |

---

### setInputModeBool

设置输入模式布尔选项。

#### 语法

```javascript
options.setInputModeBool(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

支持属性：

| 属性          | 类型  | 说明           |
|---------------|-------|----------------|
| values        | array | 当前输入模式值 |
| defaultValues | array | 默认输入模式值 |

示例：

```javascript
options.setInputModeBool(5, {
    values: [
        {
            id: 0,
            value: true
        }
    ]
});
```

---

### getInputModeFloat

获取输入模式浮点选项。

#### 语法

```javascript
options.getInputModeFloat(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明    |
|------|--------|------|---------|
| id   | number | 是   | 选项 ID |

#### 返回值

返回对象：

| 属性          | 类型   | 说明           |
|---------------|--------|----------------|
| values        | array  | 当前输入模式值 |
| defaultValues | array  | 默认输入模式值 |
| delta         | number | 调整步长       |
| minValue      | number | 最小值         |
| maxValue      | number | 最大值         |

数组元素：

| 属性  | 类型   | 说明         |
|-------|--------|--------------|
| name  | string | 输入模式名称 |
| id    | number | 输入模式 ID  |
| value | number | 对应值       |

---

### setInputModeFloat

设置输入模式浮点选项。

#### 语法

```javascript
options.setInputModeFloat(id, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| id    | number | 是   | 选项 ID  |
| value | object | 是   | 设置内容 |

支持属性：

| 属性          | 类型   | 说明           |
|---------------|--------|----------------|
| values        | array  | 当前输入模式值 |
| defaultValues | array  | 默认输入模式值 |
| delta         | number | 调整步长       |
| minValue      | number | 最小值         |
| maxValue      | number | 最大值         |

示例：

```javascript
options.setInputModeFloat(6, {
    minValue: 0,
    maxValue: 1,
    delta: 0.1
});
```

---

### getPlayerViewPerspective

获取玩家当前视角模式。

#### 语法

```javascript
options.getPlayerViewPerspective();
```

#### 返回值

返回 `number`。

视角值由游戏内部定义。

#### 示例

```javascript
const perspective = options.getPlayerViewPerspective();

console.log(perspective);
```

---

### setPlayerViewPerspective

设置玩家视角模式。

#### 语法

```javascript
options.setPlayerViewPerspective(value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明        |
|-------|--------|------|-------------|
| value | number | 是   | 视角模式 ID |

#### 返回值

无。

#### 示例

```javascript
options.setPlayerViewPerspective(1);
```
