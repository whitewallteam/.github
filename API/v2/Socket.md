`socket` 模块提供 WebSocket 网络通信 API，用于创建 WebSocket 连接、发送和接收文本/二进制消息，以及监听连接状态变化事件。

通过 `require` 获取：

```javascript
const socket = require("socket");
```

---

### WebSocket

创建一个 WebSocket 客户端实例。

#### 构造方法

```javascript
const ws = new socket.WebSocket(url);
```

#### 参数

| 参数 | 类型   | 必填 | 说明                 |
|------|--------|------|----------------------|
| url  | string | 是   | WebSocket 服务器地址 |

#### 返回值

返回一个 `WebSocket` 对象。

#### 示例

```javascript
const socket = require("socket");

const ws = new socket.WebSocket("ws://localhost:8080");
```

---

### connect

连接 WebSocket 服务器。

#### 语法

```javascript
ws.connect();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
const socket = require("socket");

const ws = new socket.WebSocket("ws://localhost:8080");

ws.connect();
```

---

### setOnTextMessageListener

设置文本消息接收监听器。

当 WebSocket 收到文本消息时调用回调函数。

#### 语法

```javascript
ws.setOnTextMessageListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明             |
|----------|----------|------|------------------|
| callback | function | 是   | 文本消息回调函数 |

回调参数：

| 参数    | 类型   | 说明             |
|---------|--------|------------------|
| message | string | 接收到的文本消息 |

#### 返回值

无。

#### 示例

```javascript
ws.setOnTextMessageListener((message) => {
    console.log("收到消息:", message);
});
```

---

### setOnBytesMessageListener

设置二进制消息接收监听器。

当 WebSocket 收到二进制数据时调用回调函数。

#### 语法

```javascript
ws.setOnBytesMessageListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明               |
|----------|----------|------|--------------------|
| callback | function | 是   | 二进制消息回调函数 |

回调参数：

| 参数   | 类型        | 说明               |
|--------|-------------|--------------------|
| buffer | ArrayBuffer | 接收到的二进制数据 |

#### 返回值

无。

#### 示例

```javascript
ws.setOnBytesMessageListener((buffer) => {
    console.log("收到二进制数据:", buffer.byteLength);
});
```

---

### setOnOpenListener

设置 WebSocket 连接成功监听器。

连接建立成功后调用回调函数。

#### 语法

```javascript
ws.setOnOpenListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明             |
|----------|----------|------|------------------|
| callback | function | 是   | 连接成功回调函数 |

回调参数：

| 参数    | 类型   | 说明                 |
|---------|--------|----------------------|
| message | string | 服务器返回的连接信息 |

#### 返回值

无。

#### 示例

```javascript
ws.setOnOpenListener((message) => {
    console.log("连接成功:", message);
});
```

---

### setOnClosingListener

设置 WebSocket 正在关闭监听器。

当连接开始关闭时调用回调函数。

#### 语法

```javascript
ws.setOnClosingListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明           |
|----------|----------|------|----------------|
| callback | function | 是   | 关闭中回调函数 |

回调参数：

| 参数   | 类型   | 说明       |
|--------|--------|------------|
| code   | number | 关闭状态码 |
| reason | string | 关闭原因   |

#### 返回值

无。

#### 示例

```javascript
ws.setOnClosingListener((code, reason) => {
    console.log("正在关闭:", code, reason);
});
```

---

### setOnClosedListener

设置 WebSocket 已关闭监听器。

连接完全关闭后调用回调函数。

#### 语法

```javascript
ws.setOnClosedListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明             |
|----------|----------|------|------------------|
| callback | function | 是   | 关闭完成回调函数 |

回调参数：

| 参数   | 类型   | 说明       |
|--------|--------|------------|
| code   | number | 关闭状态码 |
| reason | string | 关闭原因   |

#### 返回值

无。

#### 示例

```javascript
ws.setOnClosedListener((code, reason) => {
    console.log("连接已关闭:", code, reason);
});
```

---

### setOnErrorListener

设置 WebSocket 错误监听器。

发生连接错误时调用回调函数。

#### 语法

```javascript
ws.setOnErrorListener(callback);
```

#### 参数

| 参数     | 类型     | 必填 | 说明         |
|----------|----------|------|--------------|
| callback | function | 是   | 错误回调函数 |

回调参数：

| 参数  | 类型   | 说明     |
|-------|--------|----------|
| error | string | 错误信息 |

#### 返回值

无。

#### 示例

```javascript
ws.setOnErrorListener((error) => {
    console.log("WebSocket错误:", error);
});
```

---

### sendMessage

发送文本消息。

#### 语法

```javascript
ws.sendMessage(message);
```

#### 参数

| 参数    | 类型   | 必填 | 说明             |
|---------|--------|------|------------------|
| message | string | 是   | 要发送的文本内容 |

#### 返回值

无。

#### 示例

```javascript
ws.sendMessage("Hello WebSocket");
```

---

### sendBytesMessage

发送二进制消息。

#### 语法

```javascript
ws.sendBytesMessage(buffer);
```

#### 参数

| 参数   | 类型        | 必填 | 说明               |
|--------|-------------|------|--------------------|
| buffer | ArrayBuffer | 是   | 要发送的二进制数据 |

#### 返回值

无。

#### 示例

```javascript
const buffer = new ArrayBuffer(4);

ws.sendBytesMessage(buffer);
```

---

### close

关闭 WebSocket 连接。

#### 语法

```javascript
ws.close();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
ws.close();
```

---

#### 完整示例

```javascript
const socket = require("socket");

const ws = new socket.WebSocket("ws://localhost:8080");

ws.setOnOpenListener(() => {
    console.log("WebSocket 已连接");

    ws.sendMessage("Hello Server");
});

ws.setOnTextMessageListener((message) => {
    console.log("收到文本:", message);
});

ws.setOnBytesMessageListener((buffer) => {
    console.log("收到二进制:", buffer.byteLength);
});

ws.setOnErrorListener((error) => {
    console.log("连接错误:", error);
});

ws.setOnClosedListener((code, reason) => {
    console.log("连接关闭:", code, reason);
});

ws.connect();
```
