`sp` 模块提供持久化键值存储 API，用于保存和读取插件数据。

通过 `require` 获取：

```javascript
const sp = require("sp");
```

---

### getString

获取字符串类型的数据。

#### 语法

```javascript
sp.getString(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`string`

返回存储的字符串值。

#### 示例

```javascript
const sp = require("sp");

let name = sp.getString("name");

console.log(name);
```

---

### getInt

获取整数类型的数据。

#### 语法

```javascript
sp.getInt(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`number`

返回存储的整数值。

#### 示例

```javascript
const sp = require("sp");

let count = sp.getInt("count");

console.log(count);
```

---

### getLong

获取长整数类型的数据。

#### 语法

```javascript
sp.getLong(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`bigint`

返回存储的 64 位整数值。

#### 示例

```javascript
const sp = require("sp");

let timestamp = sp.getLong("timestamp");

console.log(timestamp);
```

---

### getFloat

获取浮点数类型的数据。

#### 语法

```javascript
sp.getFloat(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`number`

返回存储的浮点数值。

#### 示例

```javascript
const sp = require("sp");

let progress = sp.getFloat("progress");

console.log(progress);
```

---

### getBoolean

获取布尔类型的数据。

#### 语法

```javascript
sp.getBoolean(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`boolean`

返回存储的布尔值。

#### 示例

```javascript
const sp = require("sp");

let enabled = sp.getBoolean("enabled");

console.log(enabled);
```

---

### putString

保存字符串类型的数据。

#### 语法

```javascript
sp.putString(key, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明           |
|-------|--------|------|----------------|
| key   | string | 是   | 数据键名       |
| value | string | 是   | 要保存的字符串 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.putString("name", "Steve");
```

---

### putInt

保存整数类型的数据。

#### 语法

```javascript
sp.putInt(key, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明         |
|-------|--------|------|--------------|
| key   | string | 是   | 数据键名     |
| value | number | 是   | 要保存的整数 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.putInt("count", 100);
```

---

### putLong

保存长整数类型的数据。

#### 语法

```javascript
sp.putLong(key, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明               |
|-------|--------|------|--------------------|
| key   | string | 是   | 数据键名           |
| value | bigint | 是   | 要保存的 64 位整数 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.putLong("timestamp", 123456789012345n);
```

---

### putFloat

保存浮点数类型的数据。

#### 语法

```javascript
sp.putFloat(key, value);
```

#### 参数

| 参数  | 类型   | 必填 | 说明           |
|-------|--------|------|----------------|
| key   | string | 是   | 数据键名       |
| value | number | 是   | 要保存的浮点数 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.putFloat("speed", 1.5);
```

---

### putBoolean

保存布尔类型的数据。

#### 语法

```javascript
sp.putBoolean(key, value);
```

#### 参数

| 参数  | 类型    | 必填 | 说明           |
|-------|---------|------|----------------|
| key   | string  | 是   | 数据键名       |
| value | boolean | 是   | 要保存的布尔值 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.putBoolean("enabled", true);
```

---

### contains

判断是否存在指定键。

#### 语法

```javascript
sp.contains(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

`boolean`

如果存在对应键返回 `true`，否则返回 `false`。

#### 示例

```javascript
const sp = require("sp");

if (sp.contains("username")) {
    console.log("数据存在");
}
```

---

### remove

删除指定键的数据。

#### 语法

```javascript
sp.remove(key);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| key  | string | 是   | 数据键名 |

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.remove("username");
```

---

### clear

清空所有存储的数据。

#### 语法

```javascript
sp.clear();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
const sp = require("sp");

sp.clear();
```
