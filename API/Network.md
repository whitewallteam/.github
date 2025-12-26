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
