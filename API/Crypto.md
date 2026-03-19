
## Crypto

**描述**:
提供加密、解密以及摘要（哈希）计算功能。

---

### Crypto.encrypt

**描述**:
使用指定加密算法对数据进行加密。

**参数**:

* `options` - `object`

    * `cipher` - `string` - 加密算法名称（如 `"aes-128-cbc"`）
    * `data` - `ArrayBuffer` - 待加密数据
    * `key` - `ArrayBuffer` *(可选)* - 密钥
    * `iv` - `ArrayBuffer` *(可选)* - 初始化向量

**返回值**: `ArrayBuffer` - 加密后的数据

**示例代码**:

```javascript
let data = encode("hello").buffer;

let encrypted = Crypto.encrypt({
    cipher: "aes-128-cbc",
    data: data,
    key: keyBuffer,
    iv: ivBuffer
});
```

**注意事项**:

* 必须提供 `cipher` 和 `data`。
* `cipher` 必须为有效算法名称，否则会抛出异常。
* `key` 和 `iv` 是否需要取决于具体算法。

---

### Crypto.decrypt

**描述**:
使用指定加密算法对数据进行解密。

**参数**:

* `options` - `object`

    * `cipher` - `string` - 加密算法名称
    * `data` - `ArrayBuffer` - 待解密数据
    * `key` - `ArrayBuffer` *(可选)* - 密钥
    * `iv` - `ArrayBuffer` *(可选)* - 初始化向量

**返回值**: `ArrayBuffer` - 解密后的数据

**示例代码**:

```javascript
let decrypted = Crypto.decrypt({
    cipher: "aes-128-cbc",
    data: encryptedBuffer,
    key: keyBuffer,
    iv: ivBuffer
});
```

**注意事项**:

* 参数必须与加密时保持一致，否则解密失败。
* 若算法不存在或参数错误，将抛出异常。

---

### Crypto.digest

**描述**:
计算数据的摘要（哈希值）。

**参数**:

* `algorithm` - `string` - 摘要算法名称（如 `"md5"`、`"sha256"`）
* `data` - `ArrayBuffer` - 输入数据

**返回值**: `ArrayBuffer` - 摘要结果

**示例代码**:

```javascript
let data = encode("hello").buffer;

let hash = Crypto.digest("sha256", data);
```

**注意事项**:

* 必须提供算法名称和数据。
* 算法不存在时会抛出异常。
* 返回结果为原始二进制数据，如需字符串需自行编码（如 hex）。
