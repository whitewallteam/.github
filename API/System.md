
### require

**描述**: 引入模块。

**参数**:
- `moduleName` - `string` - 模块名称

**返回值**: `any` - 模块的导出对象

**示例代码**:
```javascript
let myModule = require("myModule");
console.log(myModule.hello());
```

**注意事项**: 确保模块名称正确且模块存在。

---

### exit

**描述**: 退出脚本并且销毁实例。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
exit();
```

**注意事项**: 该方法将终止当前运行的脚本，使用时请确保已经保存所有必要的数据。

---

### getResource

**描述**: 获取资源路径。

**参数**: 无

**返回值**: `string` - 资源路径

**示例代码**:
```javascript
let resourcePath = getResource();
console.log("Resource Path: " + resourcePath);
```

**注意事项**: 无

---

### getFilesDir

**描述**: 获取游戏私有文件路径。

**参数**: 无

**返回值**: `string` - 游戏私有文件路径

**示例代码**:
```javascript
let filesDir = getFilesDir();
console.log("Files Directory: " + filesDir);
```

**注意事项**: 无

---

### gc

**描述**: 启动垃圾回收。

**参数**: 无

**返回值**: 无

**示例代码**:
```javascript
gc();
```

**注意事项**: 该方法请求启动垃圾回收，但不保证立即执行。

---

### getData

**描述**: 获取保存数据。

**参数**:
- `key` - `string` - 数据的键名
- `defValue` - `T` - 默认值 (T 为可变参数，只能为基本数据类型)

**返回值**: `T` - 保存的数据，类型为传入的默认值类型

**示例代码**:
```javascript
let score = getData("playerScore", 0);
console.log("Player Score: " + score);
```

**注意事项**: 确保传入的默认值类型与预期获取的数据类型一致。

---

### setData

**描述**: 设置保存数据。

**参数**:
- `key` - `string` - 数据的键名
- `value` - `T` - 数据的值 (T 为可变参数，只能为基本数据类型)

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isSet = setData("playerScore", 100);
console.log("Is Data Set: " + isSet);
```

**注意事项**: 如果返回 `false`，请检查是否有权限或存储空间问题。

---

### thread

**描述**: 创建新线程。

**参数**:
- `fun` - `function` - 线程执行的函数
- `milliseconds` - `number` - 延迟执行的时间，单位为毫秒

**返回值**: `number` - 线程 ID

**示例代码**:
```javascript
let threadId = thread(() => {
    console.log("This is running in a new thread!");
}, 1000);
console.log("Thread ID: " + threadId);
```

**注意事项**: 确保线程函数执行的代码是线程安全的。

---

### setTimeout

**描述**: 在指定的延迟时间后执行一次指定的函数。

**参数**:
- `callback` - `Function` - 要执行的函数。
- `delay` - `number` - 延迟的毫秒数。

**返回值**: `number` - 返回一个唯一的定时器 ID，用于取消定时器。

**示例代码**:
```javascript
let timerId = setTimeout(() => {
    console.log("Executed after 2 seconds");
}, 2000);
```

---

### setInterval

**描述**: 每隔指定的时间重复执行一次指定的函数。

**参数**:
- `callback` - `Function` - 要执行的函数。
- `interval` - `number` - 间隔的毫秒数。

**返回值**: `number` - 返回一个唯一的定时器 ID，用于取消定时器。

**示例代码**:
```javascript
let intervalId = setInterval(() => {
    console.log("Executed every 1 second");
}, 1000);
```
---

### clearInterval

**描述**: 取消通过 `setInterval` 创建的定时器。

**参数**:
- `intervalId` - `number` - `setInterval` 返回的定时器 ID。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
clearInterval(intervalId);
console.log("Interval cleared");
```

**注意事项**: `setTimeout` 和 `setInterval` 的延迟和间隔是以毫秒为单位。
使用 `clearTimeout` 取消由 `setTimeout` 创建的定时器。

---

### loadScript

**描述**: 加载脚本。

**参数**:
- `name` - `string` - 脚本名称

**返回值**: `boolean` - 加载成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isScriptLoaded = loadScript("exampleScript");
console.log("Is Script Loaded: " + isScriptLoaded);
```

**注意事项**: 确保脚本名称正确且脚本文件存在。

---

### eval

**描述**: 运行脚本代码。

**参数**:
- `code` - `string` - 脚本代码

**返回值**: `boolean` - 运行成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isEvalSuccess = eval("console.log('Hello World');");
console.log("Is Eval Success: " + isEvalSuccess);
```

**注意事项**: 确保脚本代码是合法的且无语法错误。

---

### executePluginCommand

**描述**: 执行插件命令。

**参数**:
- `cmd` - `string` - 插件命令

**返回值**: `boolean` - 执行成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isCommandExecuted = executePluginCommand("refresh");
console.log("Is Command Executed: " + isCommandExecuted);
```

**注意事项**: 确保插件命令正确且插件已加载。

---

### callModule

**描述**: 调用功能模块。

**参数**:
- `moduleId` - `number` - 模块 ID
- `json` - `string` - 传递给模块的 JSON 字符串

**返回值**: `boolean` - 调用成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isModuleCalled = callModule(1, "{\"action\":\"start\"}");
console.log("Is Module Called: " + isModuleCalled);
```

**注意事项**: 确保模块 ID 和 JSON 格式正确。

---

### execPython

**描述**: 执行指定路径的 Python 脚本文件。

**参数**:
- `path` - `string` - Python 脚本文件的路径。

**返回值**: `boolean` - 如果脚本成功执行，返回 `true`；否则返回 `false`。

**示例代码**:
```javascript
let isExecuted = execPython("path/to/script.py");
console.log("Python script executed: " + isExecuted);
```

**注意事项**:
- 确保 `path` 指向一个有效的 Python 脚本文件。
- Python 脚本的执行环境必须配置正确，支持脚本中使用的模块。
- 脚本运行时可能会抛出错误，建议捕获并处理异常。

---

### evalPython

**描述**: 执行一段 Python 代码字符串。

**参数**:
- `code` - `string` - 要执行的 Python 代码字符串。
**返回值**: `boolean` - 如果脚本成功执行，返回 `true`；否则返回 `false`。

**示例代码**:
```javascript
let result = evalPython("print('Hello from Python')");
console.log("Python eval result: " + result);
```

**注意事项**:
- 确保输入的 `code` 为有效的 Python 代码。
- 执行的代码将运行在当前 Python 环境中，可能会影响全局状态。
- 出于安全性考虑，避免直接执行来自用户输入的未验证代码。

---

### compress  

**描述**:  
对输入数据进行压缩并返回 `ArrayBuffer` 格式的压缩数据。  

**参数**:  
- `data` - `ArrayBuffer` - 需要压缩的字符串数据。  

**返回值**:  
`ArrayBuffer` - 压缩后的二进制数据。  

**示例代码**:  
```javascript
let bin;
let compressedData = compress(text);
console.log(compressedData);
```

**注意事项**:  
- 适用于需要减少数据大小的场景，如存储或网络传输。  
- 压缩算法可能影响解压缩的兼容性，请确保使用相同的算法进行解压。  

---

### uncompress  

**描述**:  
对压缩的 `ArrayBuffer` 数据进行解压，并返回原始字符串数据。  

**参数**:  
- `data` - `ArrayBuffer` - 需要解压缩的二进制数据。  

**返回值**:  
`string` - 解压后的原始字符串数据。  

**示例代码**:  
```javascript
let decompressedText = uncompress(compressedData);
console.log(decompressedText);  // 输出: "Hello, this is a test string."
```

**注意事项**:  
- `data` 需要是由 `compress` 生成的压缩数据，否则可能无法正确解压。  
- 确保解压时使用与压缩时相同的编码格式，以避免数据损坏。  

---

### createSnapshot  

**描述**:  
把javascript代码编译为字节码，并返回快照数据。  

**参数**:  
- `code` - `string` - javascript代码。  

**返回值**:  
`ArrayBuffer` - 编译后的快照二进制数据。  

**示例代码**:  
```javascript
let bin = createSnapshot('function main() { return 1}');
console.log(bin);
```

**注意事项**:  
- `code` 作为预加载数据不能直接调用API执行代码，请用函数调用方式使用。

---

### loadSnapshot  

**描述**:  
加载快照二进制数据。  

**参数**:  
- `bin` - `ArrayBuffer` - 快照二进制数据。  
- `code` - `string` - 进入函数(可选)。  

**返回值**:  
无。  

**示例代码**:  
```javascript
let bin
loadSnapshot(bin, 'main()');
```

**注意事项**:  
- `code` 用来调用快照中定义的函数。

---

### System.syscall

**描述**: 系统调用。

**参数**:
- `lib` - `string` - 库名称
- `func` - `string` - 函数名称
- `args` - `any[]` - 函数参数

**返回值**: `any` - 函数返回值指针

**示例代码**:
```javascript
let result = System.syscall('libc.so','malloc', 100);
console.log(result);
```

**注意事项**: 请谨慎使用系统调用，可能会导致程序崩溃或数据丢失。

---

### System.readAddress

**描述**: 读取指针指向的数据。

**参数**:
- `ptr` - `number` - 指针
- `size` - `number` - 读取字节数

**返回值**: `ArrayBuffer` - 读取的数据

**示例代码**:
```javascript
let ptr = System.syscall('libc.so','malloc', 100);
let data = System.readAddress(ptr, 100);
console.log(data);
```

**注意事项**: 请谨慎使用该方法，可能会导致程序崩溃或数据丢失。

### System.writeAddress

**描述**: 写入数据到指针指向的内存。

**参数**:
- `ptr` - `number` - 指针
- `size` - `number` - 写入字节数
- `data` - `ArrayBuffer` - 写入的数据

**返回值**: `void` - 无返回值

**示例代码**:
```javascript
let ptr = System.syscall('libc.so','malloc', 100);
let data = new ArrayBuffer(100);
System.writeAddress(ptr, 100, data);
```

**注意事项**: 请谨慎使用该方法，可能会导致程序崩溃或数据丢失。