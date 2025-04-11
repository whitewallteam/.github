
# 快照创建与使用

你可以使用 `createSnapshot()` 编译模块脚本，并通过 `loadSnapshot()` 加载运行。

---

## 📜 快照内容结构示例

```javascript
const snapshotCode = `
// 模块信息
const Module = {
    name: 'Snapshot',
    version: '1.0.0',
    description: 'Snapshot created by Snapshot.md',
    author: 'Snapshot',
}

// 声明变量（注意：不能调用 API）
let resourcePath

// 全局定义事件回调（不要写在 main 函数里）
function onCallModuleEvent(args) {
    console.log('Call Module Event:', args)
}

// 模块主入口
function main() {
    resourcePath = getResource('data') // 只能在 main 中调用 API
    console.log('Resource Path:', resourcePath)
}
`
```

---

## ❌ 常见错误用法

### 错误写法 1：事件函数写在 `main()` 里

```javascript
function main() {
    // ❌ 事件不能在 main 内部定义！
    function onCallModuleEvent(args) {
        console.log('This will NOT work')
    }
}
```

**原因**：事件函数在快照加载后会立即注册，如果写在 `main()` 内，加载时无法访问，导致失效。

---

### 错误写法 2：在全局作用域调用 API 初始化变量

```javascript
// ❌ 不允许在全局直接调用 API 函数
let resourcePath = getResource('data')
```

**原因**：API 函数只能在 `main()` 函数中调用。快照加载阶段只执行顶层语法，调用 API 会抛出异常。

---

## ✅ 正确做法

```javascript
// 在全局只声明变量
let resourcePath

// 事件函数写在全局作用域
function onCallModuleEvent(args) {
    console.log('Event received:', args)
}

// 在 main 函数中完成初始化
function main() {
    resourcePath = getResource('data')
    console.log('Resource Path:', resourcePath)
}
```

---

## 🔁 快照创建与加载流程

```javascript
try {
    const bin = createSnapshot(snapshotCode) // 编译为快照二进制
    const path = getResource('data')         // 获取写入路径
    File.writeBinary(`${path}/snapshot.bin`, bin)

    const snapshotBin = File.readBinary(`${path}/snapshot.bin`)
    loadSnapshot(snapshotBin)                // 加载快照
} catch (e) {
    console.log('快照创建或加载失败:', e)
}
```
