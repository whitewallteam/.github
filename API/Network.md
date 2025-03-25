
### curl_get

**描述**: 发起 GET 请求。

**参数**:
- `url` - `string` - 请求的 URL
- `headers` - `object` - 请求头信息
- `callback` - `function` - 回调函数

**返回值**: `boolean` - 请求成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isGetRequestSent = curl_get("https://api.example.com", { "Authorization": "Bearer token" }, function(code,response) {
    console.log("GET Response: ", response);
});
console.log("GET Request Sent: " + isGetRequestSent);
```

**注意事项**: 无

---

### curl_post

**描述**: 发起 POST 请求。

**参数**:
- `url` - `string` - 请求的 URL
- `headers` - `object` - 请求头信息
- `data` - `string` - 请求数据
- `callback` - `function` - 回调函数

**返回值**: `boolean` - 请求成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isPostRequestSent = curl_post("https://api.example.com", { "Authorization": "Bearer token" }, '{"key":"value"}', function(code,response) {
    console.log("POST Response: ", response);
});
console.log("POST Request Sent: " + isPostRequestSent);
```

**注意事项**: 无

---

### curl_put

**描述**: 发起 PUT 请求。

**参数**:
- `url` - `string` - 请求的 URL
- `headers` - `object` - 请求头信息
- `data` - `string` - 请求数据
- `callback` - `function` - 回调函数

**返回值**: `boolean` - 请求成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isPutRequestSent = curl_put("https://api.example.com", { "Authorization": "Bearer token" }, '{"key":"value"}', function(code,response) {
    console.log("PUT Response: ", response);
});
console.log("PUT Request Sent: " + isPutRequestSent);
```

**注意事项**: 无

---

### curl_get_game_api

**描述**: 发起游戏API GET 请求。

**参数**:
- `url` - `string` - 请求的 URL
- `callback` - `function` - 回调函数

**返回值**: 无

**示例代码**:
```javascript
curl_get_game_api("https://api.example.com", function(code,response) {
    console.log("Response: ", response);
});
```

**注意事项**: 无

---

### curl_post_game_api

**描述**: 发起游戏API POST 请求。

**参数**:
- `url` - `string` - 请求的 URL
- `body` - `string` - 请求体信息
- `callback` - `function` - 回调函数

**返回值**: 无

**示例代码**:
```javascript
curl_post_game_api("https://api.example.com", '{"key":"value"}', function(code,response) {
    console.log("Response: ", response);
});
```

**注意事项**: 无

