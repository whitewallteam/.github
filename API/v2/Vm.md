`vm` 模块提供 V8 虚拟机相关 API，包括 JavaScript 字节码编译、加载执行以及 V8 Snapshot 创建与加载功能。

通过 `require` 获取：

```javascript
const vm = require("vm");
````

---

### createBytecode

将 JavaScript 源代码编译为 V8 字节码。

生成的字节码可以通过 `loadBytecode` 加载执行。

#### 语法

```javascript
vm.createBytecode(source, options);
```

#### 参数

| 参数                  | 类型    | 必填 | 说明                                      |
|-----------------------|---------|------|-------------------------------------------|
| source                | string  | 是   | 要编译的 JavaScript 源代码                |
| options               | object  | 否   | 编译选项                                  |
| options.resource_name | string  | 否   | 设置脚本资源名称，默认为 `<Bytecode>`     |
| options.is_module     | boolean | 否   | 是否以 ES Module 模式编译，默认为 `false` |

#### 返回值

`ArrayBuffer`

返回包含 V8 字节码数据的 ArrayBuffer。

#### 示例

```javascript
const vm = require("vm");

const bytecode = vm.createBytecode(`
    function hello() {
        return "Hello World";
    }

    hello();
`);

console.log(bytecode);
```

指定编译选项：

```javascript
const bytecode = vm.createBytecode(`
    export default function test() {
        return 123;
    }
`, {
    resource_name: "test.js",
    is_module: true
});
```

---

### loadBytecode

加载并执行通过 `createBytecode` 创建的 V8 字节码。

#### 语法

```javascript
vm.loadBytecode(bytecode);
```

#### 参数

| 参数     | 类型        | 必填 | 说明                             |
|----------|-------------|------|----------------------------------|
| bytecode | ArrayBuffer | 是   | 由 `createBytecode` 生成的字节码 |

#### 返回值

`any`

返回脚本执行结果。

#### 示例

```javascript
const vm = require("vm");

const bytecode = vm.createBytecode(`
    1 + 2;
`);

const result = vm.loadBytecode(bytecode);

console.log(result); // 3
```

---

### createSnapshot

根据 JavaScript 源代码创建 V8 Snapshot。

Snapshot 可以保存预初始化的 JavaScript 环境，用于快速启动新的 V8 上下文。

#### 语法

```javascript
vm.createSnapshot(source);
```

#### 参数

| 参数   | 类型   | 必填 | 说明                                   |
|--------|--------|------|----------------------------------------|
| source | string | 是   | 用于创建 Snapshot 的 JavaScript 源代码 |

#### 返回值

`ArrayBuffer`

返回包含 V8 Snapshot 数据的 ArrayBuffer。

#### 示例

```javascript
const vm = require("vm");

const snapshot = vm.createSnapshot(`
    globalThis.version = "1.0";

    function main() {
        return version;
    }
`);
```

---

### loadSnapshot

加载 V8 Snapshot 并执行入口函数。

#### 语法

```javascript
vm.loadSnapshot(snapshot, entry);
```

#### 参数

| 参数     | 类型        | 必填 | 说明                                      |
|----------|-------------|------|-------------------------------------------|
| snapshot | ArrayBuffer | 是   | 由 `createSnapshot` 创建的 Snapshot 数据  |
| entry    | string      | 否   | 加载后执行的入口函数名称，默认为 `main()` |

#### 返回值

`any`

返回入口函数执行结果。

#### 示例

```javascript
const vm = require("vm");

const snapshot = vm.createSnapshot(`
    function main() {
        return "Snapshot Loaded";
    }
`);

const result = vm.loadSnapshot(snapshot);

console.log(result);
```

指定入口：

```javascript
const result = vm.loadSnapshot(snapshot, "start()");
```

---

#### 注意事项

* `createBytecode` 生成的字节码只能由相同 V8 版本环境加载执行。
* `loadBytecode` 会立即执行加载后的脚本。
* `createSnapshot` 创建 Snapshot 时会在独立 V8 Isolate 中执行初始化代码。
* `loadSnapshot` 默认执行 `main()` 函数。
* Snapshot 适用于需要快速初始化大量固定代码的场景。
