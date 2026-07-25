`thread` 模块提供线程相关 API，包括获取当前线程信息、切换线程执行代码以及创建新线程执行任务等功能。

通过 `require` 获取：

```javascript
const thread = require("thread");
````

---

### getCurrentThreadId

获取当前线程 ID。

#### 语法

```javascript
thread.getCurrentThreadId();
```

#### 参数

无。

#### 返回值

| 类型   | 说明        |
|--------|-------------|
| string | 当前线程 ID |

#### 示例

```javascript
const thread = require("thread");

const id = thread.getCurrentThreadId();

console.log("当前线程 ID:", id);
```

---

### getCurrentThreadName

获取当前线程名称。

#### 语法

```javascript
thread.getCurrentThreadName();
```

#### 参数

无。

#### 返回值

| 类型   | 说明         |
|--------|--------------|
| string | 当前线程名称 |

#### 示例

```javascript
const thread = require("thread");

const name = thread.getCurrentThreadName();

console.log("当前线程:", name);
```

---

### setCurrentThreadName

设置当前线程名称。

#### 语法

```javascript
thread.setCurrentThreadName(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明             |
|------|--------|------|------------------|
| name | string | 是   | 要设置的线程名称 |

#### 返回值

无。

#### 示例

```javascript
const thread = require("thread");

thread.setCurrentThreadName("MyScriptThread");
```

---

### runOnUiThread

在 UI 线程中执行回调函数。

该方法会将任务提交到应用 UI 线程执行，适用于需要操作 UI 或必须在 UI 线程执行的代码。

#### 语法

```javascript
thread.runOnUiThread(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明              |
|----------|----------|------|-------------------|
| callback | function | 是   | UI 线程执行的回调 |

#### 返回值

无。

#### 示例

```javascript
const thread = require("thread");

thread.runOnUiThread(() => {
    console.log("当前运行在 UI 线程");
});
```

---

### runOnGameThread

在游戏主线程中执行回调函数。

该方法会将任务提交到游戏线程执行，适用于需要访问游戏数据或调用只能在游戏线程执行的 API。

#### 语法

```javascript
thread.runOnGameThread(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明                   |
|----------|----------|------|------------------------|
| callback | function | 是   | 游戏线程执行的回调函数 |

#### 返回值

无。

#### 示例

```javascript
const thread = require("thread");

thread.runOnGameThread(() => {
    console.log("当前运行在游戏线程");
});
```

---

### runOnNewThread

创建一个新的线程执行回调函数。

该方法会创建独立线程运行任务，任务执行完成后线程自动退出。

#### 语法

```javascript
thread.runOnNewThread(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明             |
|----------|----------|------|------------------|
| callback | function | 是   | 新线程执行的回调 |

#### 返回值

无。

#### 示例

```javascript
const thread = require("thread");

thread.runOnNewThread(() => {
    console.log("运行在新线程中");
});
```

#### 注意事项

* 新线程为异步执行，不会阻塞当前脚本线程。
* 回调函数中的代码不会立即执行，需要等待线程调度。
* 如果需要访问游戏相关 API，请使用 `runOnGameThread`。
* 如果需要执行 UI 相关操作，请使用 `runOnUiThread`。
