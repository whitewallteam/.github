`netease` 模块提供网易相关功能 API，包括登录信息获取以及 Token 加密处理等功能。

通过 `require` 获取：

```javascript
const netease = require("netease");
````

---

### encryptToken

加密网易接口请求 Token。

#### 语法

```javascript
netease.encryptToken(token, url, body);
```

#### 参数

| 参数  | 类型   | 必填 | 说明           |
|-------|--------|------|----------------|
| token | string | 是   | 登录 Token     |
| url   | string | 是   | 请求 URL       |
| body  | string | 是   | 请求 Body 内容 |

#### 返回值

| 类型   | 说明           |
|--------|----------------|
| string | 加密后的 Token |

#### 示例

```javascript
const netease = require("netease");

const token = netease.encryptToken(
    "login_token",
    "https://example.com/api/test",
    "{}"
);

console.log(token);
```

---

### getLoginToken

获取当前登录账号的 Token。

#### 语法

```javascript
netease.getLoginToken();
```

#### 参数

无。

#### 返回值

| 类型   | 说明           |
|--------|----------------|
| string | 当前登录 Token |

#### 示例

```javascript
const netease = require("netease");

const token = netease.getLoginToken();

console.log(token);
```

---

### getLoginUid

获取当前登录账号 UID。

#### 语法

```javascript
netease.getLoginUid();
```

#### 参数

无。

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| string | 当前登录账号 UID |

#### 示例

```javascript
const netease = require("netease");

const uid = netease.getLoginUid();

console.log(uid);
```

---

### getLoginAid

获取当前登录账号 Aid。

#### 语法

```javascript
netease.getLoginAid();
```

#### 参数

无。

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| string | 当前登录账号 Aid |

#### 示例

```javascript
const netease = require("netease");

const aid = netease.getLoginAid();

console.log(aid);
```

---

### getRoomSid

获取当前 Sid。

#### 语法

```javascript
netease.getRoomSid();
```

#### 参数

无。

#### 返回值

| 类型   | 说明     |
|--------|----------|
| string | 当前 Sid |

#### 示例

```javascript
const netease = require("netease");

const sid = netease.getRoomSid();

console.log(sid);
```
