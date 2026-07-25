# JS 脚本编写指南

跑路科技支持使用 JavaScript 编写自定义脚本，通过调用内置 JS API 实现自动化功能、游戏交互以及各种扩展功能。

本指南将帮助你快速了解如何创建、运行和调试 JS 脚本。

---

## 1. 创建第一个 JS 脚本

### 文件位置

将编写完成的 JavaScript 文件放入：

```

resources/script/

```

目录中。

例如：

```

resources
└── script
└── hello.js

````

---

## 2. 执行 JS 脚本

编辑`ui_definition.json`文件，在`script`中添加js文件名称

脚本会在游戏环境中加载，并可以调用跑路科技提供的 JS API。

---

# 3. JavaScript 基础

如果你没有 JavaScript 编程经验，建议先学习 JavaScript 基础语法。

推荐学习资料：

- JavaScript 教程（菜鸟教程）  
  https://www.runoob.com/js/js-tutorial.html

- MDN JavaScript 指南（推荐）  
  https://developer.mozilla.org/zh-CN/docs/Web/JavaScript

- JavaScript.info（深入学习）  
  https://zh.javascript.info/

建议先了解以下内容：

- 变量

```javascript
let name = "Steve";
const count = 10;
````

* 条件判断

```javascript
if (count > 5) {
    console.log("大于 5");
}
```

* 循环

```javascript
for (let i = 0; i < 10; i++) {
    console.log(i);
}
```

* 函数

```javascript
function hello() {
    console.log("Hello Minecraft");
}

hello();
```

* 对象和数组

```javascript
const player = {
    name: "Steve",
    level: 10
};

console.log(player.name);
```

---

# 4. 使用跑路科技 JS API

跑路科技提供了多个 JS 模块，用于访问游戏功能。

通过 `require` 加载模块：

```javascript
const player = require("player");
const world = require("world");
```

---

# 5. API 调用注意事项

部分 API 只能在 **游戏线程（Game Thread）** 或 **UI线程（UI Thread）** 中执行。

如果在其他线程中调用这些 API，可能导致：

* 游戏崩溃
* 闪退
* 数据异常
* 无响应

例如：

```
// 错误示例
const thread = require('thread');
const world = require('world');
thread.runOnUiThread(() => {
    world.getClientWorld();
});
```

某些涉及游戏状态修改的 API：

* 修改方块
* 修改实体
* 操作玩家
* 调用游戏 UI
* 执行游戏内部命令

通常需要在正确线程中执行。

---

## 推荐方式

如果 API 要求在游戏线程执行，请使用提供的线程切换接口：

```javascript
const thread = require("thread");

thread.runOnGameThread(() => {
    // 在游戏线程执行
});
```

> 不同版本提供的线程 API 可能有所不同，请以 API 文档为准。

---

# 6. 调试脚本

编写脚本时推荐使用 `clientMessage` 输出调试信息：

```javascript

const player = require("player");
const mc = require("minecraft");

mc.clientMessage("脚本开始执行");

mc.clientMessage(player.getLocalPlayer());
```

运行脚本后，可以通过日志查看输出。

---

# 7. 异常处理

建议对可能失败的操作添加异常捕获：

```javascript
try {
    const world = require("world");

    world.doSomething();

} catch (e) {
    console.log("执行失败:");
    console.log(e);
}
```

这样可以避免脚本错误导致整个脚本停止。

---

# 8. 编写建议

## 保持代码结构清晰

推荐：

```
script
├── main.js
├── utils.js
└── config.js
```

不要将所有代码写在一个文件中。

---

## 避免无限循环

错误：

```javascript
while (true) {
    doSomething();
}
```

无限循环会占用游戏线程，导致游戏卡死。

推荐：

```javascript
setInterval(() => {
    doSomething();
}, 1000);
```

---

## 注意 API 版本

跑路科技会持续更新 JS API。

更新版本后：

* 新 API 可能增加
* 部分 API 可能迁移
* 旧 API 可能废弃

请及时查看目录中的最新文档。

---

# 9. 示例脚本

创建：

```
resources/script/test.js
```

内容：

```javascript
const player = require("player");
const mc = require("minecraft");

function onTickEvent() {
    mc.clientMessage("当前玩家:", player.getLocalPlayer().getName());
}
```

进入游戏运行脚本后，如果显示玩家名称，则说明脚本运行成功。

---

# 10. 开始编写你的第一个脚本

学习流程推荐：

1. 学习 JavaScript 基础语法
2. 阅读 API 文档
3. 尝试调用简单查询 API
4. 编写游戏辅助功能
5. 学习事件监听和线程处理

祝你编写出属于自己的 Minecraft JS 脚本！
