`crypto` 模块提供加密、解密、摘要计算以及数据压缩与解压缩等功能，支持 OpenSSL 对称加密算法、哈希算法、Zlib 压缩以及 Brotli
压缩。

通过 `require` 获取：

```javascript
const crypto = require("crypto");
```

---

### encrypt

使用指定的加密算法对数据进行加密。

#### 语法

```javascript
crypto.encrypt(options);
```

#### 参数

`options` 对象：

| 参数   | 类型        | 必填 | 说明                               |
|--------|-------------|------|------------------------------------|
| cipher | string      | 是   | 加密算法名称，例如 `"aes-256-cbc"` |
| data   | ArrayBuffer | 是   | 待加密的数据                       |
| key    | ArrayBuffer | 否   | 加密密钥                           |
| iv     | ArrayBuffer | 否   | 初始化向量（IV）                   |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 加密后的数据 |

#### 示例

```javascript
const crypto = require("crypto");

const encrypted = crypto.encrypt({
    cipher: "aes-256-cbc",
    data: buffer,
    key: key,
    iv: iv
});
```

---

### decrypt

使用指定的加密算法对数据进行解密。

#### 语法

```javascript
crypto.decrypt(options);
```

#### 参数

`options` 对象：

| 参数   | 类型        | 必填 | 说明             |
|--------|-------------|------|------------------|
| cipher | string      | 是   | 加密算法名称     |
| data   | ArrayBuffer | 是   | 待解密的数据     |
| key    | ArrayBuffer | 否   | 解密密钥         |
| iv     | ArrayBuffer | 否   | 初始化向量（IV） |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 解密后的数据 |

#### 示例

```javascript
const crypto = require("crypto");

const decrypted = crypto.decrypt({
    cipher: "aes-256-cbc",
    data: encrypted,
    key: key,
    iv: iv
});
```

---

### digest

计算数据摘要（Hash）。

#### 语法

```javascript
crypto.digest(algorithm, data);
```

#### 参数

| 参数      | 类型        | 必填 | 说明                                             |
|-----------|-------------|------|--------------------------------------------------|
| algorithm | string      | 是   | 摘要算法名称，例如 `"md5"`、`"sha1"`、`"sha256"` |
| data      | ArrayBuffer | 是   | 待计算摘要的数据                                 |

#### 返回值

| 类型        | 说明     |
|-------------|----------|
| ArrayBuffer | 摘要结果 |

#### 示例

```javascript
const crypto = require("crypto");

const hash = crypto.digest("sha256", buffer);
```

---

### compress

使用 Zlib 压缩数据。

#### 语法

```javascript
crypto.compress(data);
crypto.compress(data, level);
```

#### 参数

| 参数  | 类型   | 必填        | 说明                                 |
|-------|--------|-------------|--------------------------------------|
| data  | string | ArrayBuffer | ArrayBufferView                      | 是  | 待压缩的数据                |
| level | number | 否          | 压缩等级，默认使用 Zlib 默认压缩等级 |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 压缩后的数据 |

#### 示例

压缩字符串：

```javascript
const compressed = crypto.compress("Hello World");
```

压缩二进制数据：

```javascript
const compressed = crypto.compress(buffer, 9);
```

---

### uncompress

使用 Zlib 解压缩数据。

#### 语法

```javascript
crypto.uncompress(data);
```

#### 参数

| 参数 | 类型        | 必填            | 说明 |
|------|-------------|-----------------|------|
| data | ArrayBuffer | ArrayBufferView | 是   | 压缩后的数据 |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 解压后的数据 |

#### 示例

```javascript
const original = crypto.uncompress(compressed);
```

---

### brotliEncode

使用 Brotli 算法压缩数据。

#### 语法

```javascript
crypto.brotliEncode(data);
crypto.brotliEncode(data, level);
```

#### 参数

| 参数  | 类型   | 必填        | 说明                              |
|-------|--------|-------------|-----------------------------------|
| data  | string | ArrayBuffer | ArrayBufferView                   | 是  | 待压缩的数据                 |
| level | number | 否          | 压缩质量（Quality），默认值为 `5` |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 压缩后的数据 |

#### 示例

```javascript
const compressed = crypto.brotliEncode("Hello World");
```

指定压缩等级：

```javascript
const compressed = crypto.brotliEncode(buffer, 11);
```

---

### brotliDecode

使用 Brotli 算法解压数据。

#### 语法

```javascript
crypto.brotliDecode(data);
```

#### 参数

| 参数 | 类型   | 必填        | 说明            |
|------|--------|-------------|-----------------|
| data | string | ArrayBuffer | ArrayBufferView | 是  | Brotli 压缩后的数据 |

#### 返回值

| 类型        | 说明         |
|-------------|--------------|
| ArrayBuffer | 解压后的数据 |

#### 示例

```javascript
const data = crypto.brotliDecode(compressed);
```
