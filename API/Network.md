### curl_get

**描述**:  
发起 GET 请求。

**参数**:

- `url` (`string`) - 请求的 URL
- `headers` (`object`) - 请求头信息（键值对形式）
- `callback` (`function`) - 回调函数，格式为 `function(code, response, headers)`

**返回值**:  
无

**示例代码**:

```javascript
curl_get("https://api.example.com", {"Authorization": "Bearer token"}, function (code, response, headers) {
    // 若响应头包含以下 Content-Type，则 response 为二进制数据：
    // application/octet-stream, image, audio, video
    console.log("GET Response:", response);
});
```

---

### curl_post

**描述**:  
发起 POST 请求。

**参数**:

- `url` (`string`) - 请求的 URL
- `headers` (`object`) - 请求头信息（键值对形式）
- `data` (`string`|`arrayBuffer`) - 请求体内容
- `callback` (`function`) - 回调函数，格式为 `function(code, response, headers)`

**返回值**:  
无

**示例代码**:

```javascript
curl_post("https://api.example.com", {"Authorization": "Bearer token"}, '{"key":"value"}', function (code, response, headers) {
    // 同样根据 Content-Type 判断 response 类型
    console.log("POST Response:", response);
});
```

---

### curl_put

**描述**:  
发起 PUT 请求。

**参数**:

- `url` (`string`) - 请求的 URL
- `headers` (`object`) - 请求头信息
- `data` (`string`|`arrayBuffer`) - 请求体内容
- `callback` (`function`) - 回调函数，格式为 `function(code, response, headers)`

**返回值**:  
`boolean` - 请求发送成功返回 `true`，否则返回 `false`

**示例代码**:

```javascript
curl_put("https://api.example.com", {"Authorization": "Bearer token"}, '{"key":"value"}', function (code, response, headers) {
    console.log("PUT Response:", response);
});
```

---

### curl_get_game_api

**描述**:  
发起游戏相关的 GET 请求（无需自定义请求头）。

**参数**:

- `url` (`string`) - 请求的 URL
- `callback` (`function`) - 回调函数，格式为 `function(code, response, headers)`

**返回值**:  
无

**示例代码**:

```javascript
curl_get_game_api("https://api.example.com", function (code, response, headers) {
    console.log("Game API GET Response:", response);
});
```

---

### curl_post_game_api

**描述**:  
发起游戏相关的 POST 请求（无需自定义请求头）。

**参数**:

- `url` (`string`) - 请求的 URL
- `body` (`string`) - 请求体内容
- `callback` (`function`) - 回调函数，格式为 `function(code, response, headers)`

**返回值**:  
无

**示例代码**:

```javascript
curl_post_game_api("https://api.example.com", '{"key":"value"}', function (code, response, headers) {
    console.log("Game API POST Response:", response);
});
```

---

### 响应数据说明

所有请求中的 `callback` 回调函数都会返回以下参数：

- `code` (`number`) - HTTP 响应状态码
- `response` (`string` 或 `binary`) - 响应体内容
    - 若响应头包含以下任一 Content-Type：`application/octet-stream`、`image/*`、`audio/*`、`video/*`，则为二进制数据
    - 否则为字符串
- `headers` (`object`) - 响应头信息

---

## WebSocket

**描述**:
用于创建 WebSocket 客户端连接，并支持发送/接收文本和二进制消息，以及监听连接生命周期事件。

**构造方式**:

```javascript
let ws = new WebSocket("ws://example.com");
```

**参数**:

* `url` - `string` - WebSocket 服务器地址

**注意事项**:

* 必须使用 `new WebSocket()` 创建实例。
* URL 必须为字符串，否则会抛出异常。

---

### WebSocket.connect

**描述**:
连接到 WebSocket 服务器。

**参数**: 无

**返回值**: 无

**示例代码**:

```javascript
ws.connect();
```

**注意事项**:

* 创建实例后需要手动调用该方法才会建立连接。

---

### WebSocket.setOnTextMessageListener

**描述**:
设置接收文本消息时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(message: string) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnTextMessageListener((msg) => {
    console.log("收到文本消息:", msg);
});
```

**注意事项**:

* 回调参数为字符串。
* 回调执行异常会被抛出。

---

### WebSocket.setOnBytesMessageListener

**描述**:
设置接收二进制消息时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(buffer: ArrayBuffer) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnBytesMessageListener((buffer) => {
    let view = new Uint8Array(buffer);
    console.log("收到字节数据:", view);
});
```

**注意事项**:

* 接收到的数据为 `ArrayBuffer`。

---

### WebSocket.setOnOpenListener

**描述**:
设置连接成功时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(data: string) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnOpenListener((data) => {
    console.log("连接成功:", data);
});
```

**注意事项**:

* 回调参数为字符串（一般为 JSON 数据）。

---

### WebSocket.setOnClosingListener

**描述**:
设置连接正在关闭时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(code: number, reason: string) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnClosingListener((code, reason) => {
    console.log("连接关闭中:", code, reason);
});
```

**注意事项**: 无

---

### WebSocket.setOnClosedListener

**描述**:
设置连接已关闭时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(code: number, reason: string) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnClosedListener((code, reason) => {
    console.log("连接已关闭:", code, reason);
});
```

**注意事项**: 无

---

### WebSocket.setOnErrorListener

**描述**:
设置发生错误时的回调函数。

**参数**:

* `listener` - `function` - 回调函数 `(error: string) => void`

**返回值**: 无

**示例代码**:

```javascript
ws.setOnErrorListener((err) => {
    console.error("发生错误:", err);
});
```

**注意事项**:

* 错误信息以字符串形式传递。

---

### WebSocket.sendMessage

**描述**:
发送文本消息。

**参数**:

* `message` - `string` - 要发送的文本内容

**返回值**: 无

**示例代码**:

```javascript
ws.sendMessage("Hello Server");
```

**注意事项**:

* 必须在连接成功后调用。

---

### WebSocket.sendBytesMessage

**描述**:
发送二进制消息。

**参数**:

* `buffer` - `ArrayBuffer` - 要发送的字节数据

**返回值**: 无

**示例代码**:

```javascript
let buf = new ArrayBuffer(3);
let view = new Uint8Array(buf);
view[0] = 1;
view[1] = 2;
view[2] = 3;

ws.sendBytesMessage(buf);
```

**注意事项**:

* 数据会按原始字节发送。

---

### WebSocket.close

**描述**:
关闭 WebSocket 连接并释放资源。

**参数**: 无

**返回值**: 无

**示例代码**:

```javascript
ws.close();
```

**注意事项**:

* 调用后该实例将被销毁，不可再次使用。

