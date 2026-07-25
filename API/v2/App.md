`app` 模块提供应用运行环境相关 API，包括应用提示、模块调用、文件路径获取、插件命令执行、版本信息查询以及 Python 脚本执行等功能。

通过 `require` 获取：

```javascript
const app = require("app");
````

---

### showToast

显示一个 Toast 提示消息。

#### 语法

```javascript
app.showToast(message, duration);
```

#### 参数

| 参数     | 类型   | 必填 | 说明             |
|----------|--------|------|------------------|
| message  | string | 是   | 要显示的提示内容 |
| duration | number | 否   | 显示时长         |

#### 返回值

无。

#### 示例

```javascript
const app = require("app");

app.showToast("Hello World");
```

指定显示时长：

```javascript
app.showToast("加载完成", 3000);
```

---

### callModule

调用原生模块接口。

#### 语法

```javascript
app.callModule(tag, json);
```

#### 参数

| 参数 | 类型   | 必填 | 说明          |
|------|--------|------|---------------|
| tag  | string | 是   | 模块标识      |
| json | string | 是   | JSON 格式参数 |

#### 返回值

根据目标模块返回结果。

#### 示例

```javascript
const app = require("app");

const result = app.callModule(
    "example",
    JSON.stringify({
        value: 123
    })
);
```

#### 注意

* `json` 参数必须是合法 JSON 字符串。
* 如果参数类型错误会抛出异常。

---

### isInGame

判断当前是否处于游戏内。

#### 语法

```javascript
app.isInGame();
```

#### 参数

无。

#### 返回值

| 类型    | 说明               |
|---------|--------------------|
| boolean | 当前是否正在游戏中 |

#### 示例

```javascript
const app = require("app");

if (app.isInGame()) {
    console.log("当前正在游戏");
}
```

---

### getResource

获取资源目录路径。

#### 语法

```javascript
app.getResource([path]);
```

#### 参数

| 参数 | 类型   | 必填 | 说明                 |
|------|--------|------|----------------------|
| path | string | 否   | 资源目录下的相对路径 |

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| string | 资源文件绝对路径 |

#### 示例

获取资源目录：

```javascript
const root = app.getResource();
```

获取指定资源：

```javascript
const file = app.getResource("config.json");
```

---

### getFilesDir

获取应用文件目录。

#### 语法

```javascript
app.getFilesDir();
```

#### 参数

无。

#### 返回值

| 类型   | 说明                 |
|--------|----------------------|
| string | 应用文件目录绝对路径 |

#### 示例

```javascript
const app = require("app");

console.log(app.getFilesDir());
```

---

### executePluginCommand

执行插件命令注册。

#### 语法

```javascript
app.executePluginCommand(command);
```

#### 参数

| 参数    | 类型   | 必填 | 说明         |
|---------|--------|------|--------------|
| command | string | 是   | 插件命令内容 |

#### 返回值

| 类型    | 说明         |
|---------|--------------|
| boolean | 是否成功执行 |

#### 示例

```javascript
const app = require("app");

const success = app.executePluginCommand("test command");

if (success) {
    console.log("命令执行成功");
}
```

#### 注意

如果当前环境不存在命令管理模块，将返回 `false`。

---

### getRuntimeVersion

获取运行环境版本信息。

#### 语法

```javascript
app.getRuntimeVersion();
```

#### 参数

无。

#### 返回值

返回一个对象：

| 字段              | 类型   | 说明         |
|-------------------|--------|--------------|
| pluginVersionCode | number | 插件版本号   |
| pluginVersionName | string | 插件版本名称 |
| gameVersionCode   | number | 游戏版本号   |
| gameVersionName   | string | 游戏版本名称 |

#### 示例

```javascript
const app = require("app");

const version = app.getRuntimeVersion();

console.log(version.pluginVersionName);
console.log(version.gameVersionName);
```

---

### execPython

执行 Python 文件。

#### 语法

```javascript
app.execPython(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明            |
|------|--------|------|-----------------|
| path | string | 是   | Python 文件路径 |

#### 返回值

Python 脚本执行结果。

#### 示例

```javascript
const app = require("app");

const result = app.execPython(
    "/sdcard/test.py"
);
```

#### 异常

如果 Python 执行失败，将抛出异常。

---

### evalPython

执行 Python 字符串代码。

#### 语法

```javascript
app.evalPython(code);
```

#### 参数

| 参数 | 类型   | 必填 | 说明        |
|------|--------|------|-------------|
| code | string | 是   | Python 代码 |

#### 返回值

Python 代码执行结果。

#### 示例

```javascript
const app = require("app");

const result = app.evalPython(
    "1 + 2"
);

console.log(result);
```

#### 异常

如果 Python 执行失败，将抛出异常。

---

#### 示例

```javascript
const app = require("app");

app.showToast("脚本启动");

const version = app.getRuntimeVersion();

console.log(
    `Plugin: ${version.pluginVersionName}`
);

if (app.isInGame()) {
    console.log("游戏运行中");
}
```
