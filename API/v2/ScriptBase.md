# Script Global API

Script Global API 提供脚本运行环境相关功能，包括模块加载、动态执行代码、加载其他脚本、定时器以及脚本退出等功能。

这些 API 直接挂载在全局对象上，无需 `require` 引入即可使用。

---

### require

加载 JavaScript 模块。

支持加载 JS 文件模块、V8 字节码模块以及 ArrayBuffer 类型模块。

#### 语法

```javascript
require(path);
````

#### 参数

| 参数 | 类型                                   | 必填 | 说明               |
|------|----------------------------------------|------|--------------------|
| path | string / ArrayBuffer / ArrayBufferView | 是   | 模块路径或模块数据 |

#### 返回值

返回模块导出的对象。

#### 示例

加载 JS 模块：

```javascript
const module = require("test.js");

module.main();
```

加载本地模块：

```javascript
const fs = require("./fs.js");
```

---

### exit

退出当前脚本执行。

调用后会立即终止当前 JavaScript 执行环境。

#### 语法

```javascript
exit();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
console.log("开始");

exit();

console.log("不会执行");
```

---

### eval

动态执行 JavaScript 代码。

#### 语法

```javascript
eval(code);
```

#### 参数

| 参数 | 类型   | 必填 | 说明                     |
|------|--------|------|--------------------------|
| code | string | 是   | 要执行的 JavaScript 代码 |

#### 返回值

返回脚本执行结果。

#### 示例

```javascript
const result = eval("1 + 2");

console.log(result); // 3
```

执行复杂代码：

```javascript
eval(`
    let value = 10;
    console.log(value);
`);
```

---

### runScript

加载并运行指定名称的脚本。

#### 语法

```javascript
runScript(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 脚本名称 |

#### 返回值

无。

#### 示例

```javascript
runScript("test");
```

---

### setTimeout

延迟执行一次回调函数。

#### 语法

```javascript
setTimeout(callback, delay);
```

#### 参数

| 参数     | 类型     | 必填 | 说明               |
|----------|----------|------|--------------------|
| callback | function | 是   | 延迟执行的回调函数 |
| delay    | number   | 是   | 延迟时间（毫秒）   |

#### 返回值

无。

#### 示例

```javascript
setTimeout(() => {
    console.log("3秒后执行");
}, 3000);
```

---

### setInterval

按照固定间隔重复执行回调函数。

#### 语法

```javascript
const id = setInterval(callback, delay);
```

#### 参数

| 参数     | 类型     | 必填 | 说明                 |
|----------|----------|------|----------------------|
| callback | function | 是   | 周期执行的回调函数   |
| delay    | number   | 是   | 执行间隔时间（毫秒） |

#### 返回值

返回定时器 ID。

#### 示例

```javascript
const timer = setInterval(() => {
    console.log("每秒执行一次");
}, 1000);
```

---

### clearInterval

取消通过 `setInterval` 创建的定时器。

#### 语法

```javascript
clearInterval(id);
```

#### 参数

| 参数 | 类型   | 必填 | 说明                          |
|------|--------|------|-------------------------------|
| id   | number | 是   | `setInterval` 返回的定时器 ID |

#### 返回值

无。

#### 示例

```javascript
const timer = setInterval(() => {
    console.log("运行中");
}, 1000);

clearInterval(timer);
```
