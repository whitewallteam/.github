`os` 模块提供底层系统相关 API，包括系统调用、进程线程信息获取、动态库加载、符号查询以及内存地址读写等功能。

通过 `require` 获取：

```javascript
const os = require("os");
````

---

### syscall

调用动态库中的指定函数。

该 API 会自动加载并缓存动态库句柄，通过函数名称调用对应函数。

#### 语法

```
os.syscall(library, function, arg1, arg2, arg3, arg4, arg5, arg6);
```

#### 参数

| 参数     | 类型   | 必填 | 说明        |
|----------|--------|------|-------------|
| library  | string | 是   | 动态库路径  |
| function | string | 是   | 函数名称    |
| arg1     | number | 否   | 第 1 个参数 |
| arg2     | number | 否   | 第 2 个参数 |
| arg3     | number | 否   | 第 3 个参数 |
| arg4     | number | 否   | 第 4 个参数 |
| arg5     | number | 否   | 第 5 个参数 |
| arg6     | number | 否   | 第 6 个参数 |

#### 返回值

`bigint`

返回函数调用结果。

#### 示例

```javascript
const os = require("os");

// 调用动态库函数
let result = os.syscall(
    "libexample.so",
    "exampleFunction",
    1,
    2
);

console.log(result);
```

---

### readAddress

读取指定内存地址的数据。

#### 语法

```javascript
os.readAddress(address, size);
```

#### 参数

| 参数    | 类型   | 必填 | 说明         |
|---------|--------|------|--------------|
| address | bigint | 是   | 内存地址     |
| size    | number | 是   | 读取字节数量 |

#### 返回值

`ArrayBuffer`

返回读取到的内存数据。

#### 示例

```javascript
const os = require("os");

let buffer = os.readAddress(0x12345678n, 16);

console.log(buffer);
```

---

### writeAddress

向指定内存地址写入数据。

#### 语法

```javascript
os.writeAddress(address, size, buffer);
```

#### 参数

| 参数    | 类型        | 必填 | 说明         |
|---------|-------------|------|--------------|
| address | bigint      | 是   | 内存地址     |
| size    | number      | 是   | 写入字节数量 |
| buffer  | ArrayBuffer | 是   | 要写入的数据 |

#### 返回值

无。

#### 示例

```javascript
const os = require("os");

const buffer = new ArrayBuffer(4);

os.writeAddress(
    0x12345678n,
    4,
    buffer
);
```

---

### getPid

获取当前进程 ID。

#### 语法

```javascript
os.getPid();
```

#### 参数

无。

#### 返回值

`bigint`

返回当前进程 ID。

#### 示例

```javascript
const os = require("os");

console.log(os.getPid());
```

---

### getTid

获取当前线程 ID。

#### 语法

```javascript
os.getTid();
```

#### 参数

无。

#### 返回值

`bigint`

返回当前线程 ID。

#### 示例

```javascript
const os = require("os");

console.log(os.getTid());
```

---

### getUid

获取当前用户 ID。

#### 语法

```javascript
os.getUid();
```

#### 参数

无。

#### 返回值

`bigint`

返回当前用户 UID。

#### 示例

```javascript
const os = require("os");

console.log(os.getUid());
```

---

### getGid

获取当前用户组 ID。

#### 语法

```javascript
os.getGid();
```

#### 参数

无。

#### 返回值

`bigint`

返回当前用户组 GID。

#### 示例

```javascript
const os = require("os");

console.log(os.getGid());
```

---

### dlopen

加载动态链接库。

#### 语法

```javascript
os.dlopen(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明       |
|------|--------|------|------------|
| path | string | 是   | 动态库路径 |

#### 返回值

`External`

返回动态库句柄。

#### 示例

```javascript
const os = require("os");

const handle = os.dlopen("libexample.so");
```

---

### dlclose

关闭动态库。

#### 语法

```javascript
os.dlclose(handle);
```

#### 参数

| 参数   | 类型     | 必填 | 说明       |
|--------|----------|------|------------|
| handle | External | 是   | 动态库句柄 |

#### 返回值

无。

#### 示例

```javascript
const os = require("os");

const handle = os.dlopen("libexample.so");

os.dlclose(handle);
```

---

### dlsym

获取动态库中的函数地址。

#### 语法

```javascript
os.dlsym(handle, name);
```

#### 参数

| 参数   | 类型     | 必填 | 说明       |
|--------|----------|------|------------|
| handle | External | 是   | 动态库句柄 |
| name   | string   | 是   | 函数名称   |

#### 返回值

`bigint`

返回函数地址。

#### 示例

```javascript
const os = require("os");

const handle = os.dlopen("libexample.so");

const address = os.dlsym(handle, "exampleFunction");

console.log(address);
```

---

### dladdr

根据地址查询符号信息。

#### 语法

```javascript
os.dladdr(address);
```

#### 参数

| 参数    | 类型   | 必填 | 说明           |
|---------|--------|------|----------------|
| address | bigint | 是   | 函数或内存地址 |

#### 返回值

`object`

返回符号信息对象：

| 属性 | 类型   | 说明         |
|------|--------|--------------|
| name | string | 动态库名称   |
| base | bigint | 动态库基地址 |
| addr | bigint | 符号地址     |

#### 示例

```javascript
const os = require("os");

const info = os.dladdr(0x12345678n);

console.log(info.name);
console.log(info.base);
console.log(info.addr);
```

---

#### 注意事项

* `os` 模块提供底层系统访问能力，错误使用可能导致应用崩溃。
* `readAddress` 和 `writeAddress` 会直接操作进程内存，请确保目标地址有效。
* `syscall`、`dlsym` 等 API 依赖系统动态库环境。
* 地址相关参数统一使用 `bigint` 类型，例如：

```javascript
0x12345678n
```
