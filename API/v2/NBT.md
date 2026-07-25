`nbt` 模块提供 Minecraft NBT（Named Binary Tag）数据相关 API，支持读取原版存档数据、Schematic 建筑文件、BDX 文件以及普通 NBT
文件，并支持将 NBT 数据保存为文件。

通过 `require` 获取：

```javascript
const nbt = require("nbt");
````

---

### loadVanillaData

读取 Minecraft 原版数据文件。

支持将 NBT 数据转换为 Mojangson 字符串或 JavaScript 对象。

#### 语法

```javascript
nbt.loadVanillaData(path, format);
```

#### 参数

| 参数   | 类型   | 必填 | 说明                                                           |
|--------|--------|------|----------------------------------------------------------------|
| path   | string | 是   | 原版数据文件路径                                               |
| format | string | 否   | 返回格式，可选 `"mojangson"` 或 `"object"`，默认 `"mojangson"` |

#### 返回值

| 类型   | 说明                                              |
|--------|---------------------------------------------------|
| string | `format` 为 `"mojangson"` 时返回 Mojangson 字符串 |
| object | `format` 为 `"object"` 时返回 JavaScript 对象     |

#### 示例

读取并转换为 Mojangson：

```javascript
const nbt = require("nbt");

const data = nbt.loadVanillaData("./level.dat");

console.log(data);
```

读取为对象：

```javascript
const data = nbt.loadVanillaData("./level.dat", "object");

console.log(data);
```

---

### loadSchematic

读取 `.schematic` 建筑文件。

支持将 Schematic 内的 NBT 数据转换为 Mojangson 或 JavaScript 对象。

#### 语法

```javascript
nbt.loadSchematic(path, format);
```

#### 参数

| 参数   | 类型   | 必填 | 说明                                                           |
|--------|--------|------|----------------------------------------------------------------|
| path   | string | 是   | Schematic 文件路径                                             |
| format | string | 否   | 返回格式，可选 `"mojangson"` 或 `"object"`，默认 `"mojangson"` |

#### 返回值

| 类型   | 说明            |
|--------|-----------------|
| string | Mojangson 数据  |
| object | JavaScript 对象 |

#### 示例

```javascript
const nbt = require("nbt");

const schematic = nbt.loadSchematic("./build.schematic", "object");

console.log(schematic);
```

---

### loadLiteSchematic

读取 LiteSchematic 文件。

#### 语法

```javascript
nbt.loadLiteSchematic(path, format);
```

#### 参数

| 参数   | 类型   | 必填 | 说明                                                           |
|--------|--------|------|----------------------------------------------------------------|
| path   | string | 是   | LiteSchematic 文件路径                                         |
| format | string | 否   | 返回格式，可选 `"mojangson"` 或 `"object"`，默认 `"mojangson"` |

#### 返回值

| 类型   | 说明            |
|--------|-----------------|
| string | Mojangson 数据  |
| object | JavaScript 对象 |

#### 示例

```javascript
const nbt = require("nbt");

const data = nbt.loadLiteSchematic("./build.litematic", "object");

console.log(data);
```

---

### loadBdx

读取 BDX 建筑文件，并转换为 JSON 数据。

#### 语法

```javascript
nbt.loadBdx(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明         |
|------|--------|------|--------------|
| path | string | 是   | BDX 文件路径 |

#### 返回值

| 类型   | 说明            |
|--------|-----------------|
| string | JSON 格式字符串 |

#### 示例

```javascript
const nbt = require("nbt");

const json = nbt.loadBdx("./build.bdx");

console.log(json);
```

---

### loadData

读取普通 NBT 文件。

支持转换为 Mojangson 字符串或 JavaScript 对象。

#### 语法

```javascript
nbt.loadData(path, format);
```

#### 参数

| 参数   | 类型   | 必填 | 说明                                                           |
|--------|--------|------|----------------------------------------------------------------|
| path   | string | 是   | NBT 文件路径                                                   |
| format | string | 否   | 返回格式，可选 `"mojangson"` 或 `"object"`，默认 `"mojangson"` |

#### 返回值

| 类型   | 说明            |
|--------|-----------------|
| string | Mojangson 数据  |
| object | JavaScript 对象 |

#### 示例

读取 NBT：

```javascript
const nbt = require("nbt");

const data = nbt.loadData("./data.nbt");

console.log(data);
```

读取为对象：

```javascript
const data = nbt.loadData("./data.nbt", "object");

console.log(data);
```

---

### saveToFile

将 Mojangson 数据保存为 NBT 文件。

#### 语法

```javascript
nbt.saveToFile(path, nbtData);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                    |
|---------|--------|------|-------------------------|
| path    | string | 是   | 输出文件路径            |
| nbtData | string | 是   | Mojangson 格式 NBT 数据 |

#### 返回值

无。

#### 示例

```javascript
const nbt = require("nbt");

const data = `
{
    name:"Example",
    value:1
}
`;

nbt.saveToFile("./output.nbt", data);
```

---

#### 格式说明

#### format 参数

| 值            | 说明                   |
|---------------|------------------------|
| `"mojangson"` | 返回 Mojangson 字符串  |
| `"object"`    | 转换为 JavaScript 对象 |

默认值：

```javascript
"mojangson"
```

---

#### 异常

当发生错误时会抛出异常：

| 错误                | 说明             |
|---------------------|------------------|
| Invalid arguments   | 参数错误         |
| File not found      | 文件不存在       |
| Failed to open file | 文件打开失败     |
| Invalid data        | NBT 数据无效     |
| Invalid data size   | 文件数据大小错误 |
| Invalid format      | 不支持的返回格式 |

