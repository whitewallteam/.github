`minecraft` 模块提供 Minecraft 客户端相关 API，包括执行游戏命令、发送聊天消息、显示提示信息以及修改标题等功能。

通过 `require` 获取：

```javascript
const minecraft = require("minecraft");
````

---

### requestExecuteCommand

请求执行 Minecraft 命令，并通过回调获取执行结果。

该接口会等待命令执行完成后调用回调函数。

#### 语法

```javascript
minecraft.requestExecuteCommand(command, callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明                     |
|----------|----------|------|--------------------------|
| command  | string   | 是   | 要执行的 Minecraft 命令  |
| callback | function | 是   | 命令执行完成后的回调函数 |

#### callback 参数

回调函数接收一个执行结果对象：

| 属性          | 类型    | 说明                       |
|---------------|---------|----------------------------|
| type          | string  | 命令输出类型               |
| successCount  | number  | 命令成功执行数量           |
| hasPlayerText | boolean | 是否包含玩家文本           |
| bag           | object  | 数据变化信息（可能不存在） |
| messages      | array   | 命令输出消息列表           |

#### bag 对象

| 属性      | 类型   | 说明      |
|-----------|--------|-----------|
| jsonValue | string | JSON 数据 |
| version   | number | 数据版本  |

#### messages 元素

| 属性      | 类型   | 说明     |
|-----------|--------|----------|
| type      | string | 消息类型 |
| messageId | string | 消息 ID  |
| params    | array  | 消息参数 |

#### 返回值

无。

#### 示例

```javascript
const minecraft = require("minecraft");

minecraft.requestExecuteCommand("say Hello", (result) => {
    console.log("执行结果:", result);

    for (const message of result.messages) {
        console.log(message.messageId);
    }
});
```

---

### queueExecuteCommand

将 Minecraft 命令加入执行队列。

该接口不会等待命令执行结果。

#### 语法

```javascript
minecraft.queueExecuteCommand(command);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                    |
|---------|--------|------|-------------------------|
| command | string | 是   | 要执行的 Minecraft 命令 |

#### 返回值

无。

#### 示例

```javascript
const minecraft = require("minecraft");

minecraft.queueExecuteCommand("say Hello World");
```

---

### showTipMessage

显示游戏提示信息。

#### 语法

```javascript
minecraft.showTipMessage(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| message | string | 是   | 提示内容 |

#### 返回值

无。

#### 示例

```javascript
const minecraft = require("minecraft");

minecraft.showTipMessage("任务完成！");
```

---

### setTitle

设置游戏标题文本。

#### 语法

```javascript
minecraft.setTitle(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| message | string | 是   | 标题内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.setTitle("欢迎进入游戏");
```

---

### setSubtitle

设置游戏副标题文本。

#### 语法

```javascript
minecraft.setSubtitle(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明       |
|---------|--------|------|------------|
| message | string | 是   | 副标题内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.setSubtitle("祝你游戏愉快");
```

---

### clientMessage

发送客户端本地消息。

#### 语法

```javascript
minecraft.clientMessage(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| message | string | 是   | 消息内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.clientMessage("这是一条客户端消息");
```

---

### sendChatMessage

发送聊天栏消息。

#### 语法

```javascript
minecraft.sendChatMessage(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| message | string | 是   | 聊天内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.sendChatMessage("Hello Minecraft");
```

---

### whisperMessage

向指定玩家发送私聊消息。

#### 语法

```javascript
minecraft.whisperMessage(player, message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| player  | string | 是   | 玩家名称 |
| message | string | 是   | 私聊内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.whisperMessage("Steve", "你好！");
```

---

### chatMessage

向指定玩家发送聊天消息。

#### 语法

```javascript
minecraft.chatMessage(player, message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明     |
|---------|--------|------|----------|
| player  | string | 是   | 玩家名称 |
| message | string | 是   | 消息内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.chatMessage("Steve", "欢迎加入服务器");
```

---

### toast

显示 Toast 通知。

#### 语法

```javascript
minecraft.toast(title, message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明       |
|---------|--------|------|------------|
| title   | string | 是   | Toast 标题 |
| message | string | 是   | Toast 内容 |

#### 返回值

无。

#### 示例

```javascript
minecraft.toast("提示", "加载完成");
```
