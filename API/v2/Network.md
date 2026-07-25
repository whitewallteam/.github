`https` 模块提供 HTTP 网络请求相关 API，支持发送 GET、POST、PUT 请求，并支持自定义请求头、请求数据以及异步获取服务器响应。

通过 `require` 获取：

```javascript
const https = require("https");
````

---

## get

发送一个 HTTP GET 请求。

##### 语法

```javascript
https.get(url, headers, callback);
```

##### 参数

| 参数     | 类型     | 必填 | 说明                         |
|----------|----------|------|------------------------------|
| url      | string   | 是   | 请求地址                     |
| headers  | object   | 是   | 请求头对象，键和值均为字符串 |
| callback | function | 是   | 请求完成后的回调函数         |

#### callback 参数

```javascript
function callback(statusCode, body, headers) {
}
```

| 参数       | 类型   | 说明        |
|------------|--------|-------------|
| statusCode | number | HTTP 状态码 |
| body       | string | ArrayBuffer | 响应内容，二进制数据时返回 ArrayBuffer |
| headers    | object | 响应头对象  |

##### 返回值

无。

##### 示例

```javascript
const https = require("https");

https.get(
    "https://example.com",
    {
        "User-Agent": "MyScript"
    },
    (statusCode, body, headers) => {
        console.log("状态码:", statusCode);
        console.log("响应内容:", body);
    }
);
```

---

## post

发送一个 HTTP POST 请求。

#### 语法

```javascript
https.post(url, headers, body, callback);
```

#### 参数

| 参数     | 类型     | 必填        | 说明                         |
|----------|----------|-------------|------------------------------|
| url      | string   | 是          | 请求地址                     |
| headers  | object   | 是          | 请求头对象，键和值均为字符串 |
| body     | string   | ArrayBuffer | ArrayBufferView              | 是  | 请求体数据          |
| callback | function | 是          | 请求完成后的回调函数         |

#### callback 参数

```javascript
function callback(statusCode, body, headers) {
}
```

| 参数       | 类型   | 说明        |
|------------|--------|-------------|
| statusCode | number | HTTP 状态码 |
| body       | string | ArrayBuffer | 响应内容，二进制数据时返回 ArrayBuffer |
| headers    | object | 响应头对象  |

#### 返回值

无。

#### 示例

发送 JSON 数据：

```javascript
const https = require("https");

https.post(
    "https://example.com/api",
    {
        "Content-Type": "application/json"
    },
    JSON.stringify({
        name: "Steve"
    }),
    (statusCode, body) => {
        console.log(statusCode);
        console.log(body);
    }
);
```

发送二进制数据：

```javascript
const https = require("https");

const buffer = new ArrayBuffer(10);

https.post(
    "https://example.com/upload",
    {
        "Content-Type": "application/octet-stream"
    },
    buffer,
    (statusCode, body) => {
        console.log(statusCode);
    }
);
```

---

## put

发送一个 HTTP PUT 请求。

#### 语法

```javascript
https.put(url, headers, body, callback);
```

#### 参数

| 参数     | 类型     | 必填        | 说明                         |
|----------|----------|-------------|------------------------------|
| url      | string   | 是          | 请求地址                     |
| headers  | object   | 是          | 请求头对象，键和值均为字符串 |
| body     | string   | ArrayBuffer | ArrayBufferView              | 是  | 请求体数据          |
| callback | function | 是          | 请求完成后的回调函数         |

#### callback 参数

```javascript
function callback(statusCode, body, headers) {
}
```

| 参数       | 类型   | 说明        |
|------------|--------|-------------|
| statusCode | number | HTTP 状态码 |
| body       | string | ArrayBuffer | 响应内容，二进制数据时返回 ArrayBuffer |
| headers    | object | 响应头对象  |

#### 返回值

无。

#### 示例

```javascript
const https = require("https");

https.put(
    "https://example.com/api/user",
    {
        "Content-Type": "application/json"
    },
    JSON.stringify({
        id: 1,
        name: "Steve"
    }),
    (statusCode, body, headers) => {
        console.log("更新完成:", statusCode);
    }
);
```

---

#### 请求头说明

请求头参数使用对象表示：

```
{
    "Header-Name": "value"
}
```

例如：

```
{
    "Authorization": "Bearer token",
    "Content-Type": "application/json"
}
```

注意：

* 请求头名称和值必须为字符串。
* 非字符串类型的请求头会被忽略。

---

#### 响应数据说明

响应内容类型根据 `Content-Type` 自动判断：

| Content-Type               | 返回类型    |
|----------------------------|-------------|
| `application/octet-stream` | ArrayBuffer |
| `image/*`                  | ArrayBuffer |
| `audio/*`                  | ArrayBuffer |
| `video/*`                  | ArrayBuffer |
| 其他类型                   | string      |

例如下载图片：

```javascript
https.get(
    "https://example.com/image.png",
    {},
    (statusCode, data, headers) => {
        if (data instanceof ArrayBuffer) {
            console.log("收到二进制数据");
        }
    }
);
```
