`fs` 模块提供文件系统相关 API，包括文件与目录操作、路径处理、权限管理、文件状态查询、目录遍历以及文件读写等功能。

通过 `require` 获取：

```javascript
const fs = require("fs");
```

---

### absolute

获取指定路径的绝对路径。

#### 语法

```javascript
fs.absolute(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型   | 说明       |
|--------|------------|
| string | 绝对路径。 |

#### 示例

```javascript
const fs = require("fs");

const path = fs.absolute("./test.txt");
```

---

### canonical

获取规范化后的路径（解析符号链接）。

#### 语法

```javascript
fs.canonical(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| string | 规范化后的路径。 |

#### 示例

```javascript
const path = fs.canonical("./test.txt");
```

---

### copy

复制文件或目录。

#### 语法

```javascript
fs.copy(from, to, options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                                             |
|---------|--------|------|--------------------------------------------------|
| from    | string | 是   | 源路径                                           |
| to      | string | 是   | 目标路径                                         |
| options | number | 否   | 复制选项（对应 `std::filesystem::copy_options`） |

#### 返回值

无。

#### 示例

```javascript
fs.copy("./source", "./target");
```

指定复制选项：

```javascript
fs.copy("./source", "./target", 1);
```

---

### copyFile

复制文件。

#### 语法

```javascript
fs.copyFile(from, to, options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                                             |
|---------|--------|------|--------------------------------------------------|
| from    | string | 是   | 源文件路径                                       |
| to      | string | 是   | 目标文件路径                                     |
| options | number | 否   | 复制选项（对应 `std::filesystem::copy_options`） |

#### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 复制是否成功。 |

#### 示例

```javascript
const success = fs.copyFile("./a.txt", "./b.txt");
```

---

### copySymlink

复制符号链接。

#### 语法

```javascript
fs.copySymlink(from, to);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| from | string | 是   | 源符号链接     |
| to   | string | 是   | 新符号链接路径 |

#### 返回值

无。

#### 示例

```javascript
fs.copySymlink("./link", "./link_copy");
```

---

### createDirectories

递归创建目录。

#### 语法

```javascript
fs.createDirectories(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明         |
|------|--------|------|--------------|
| path | string | 是   | 要创建的目录 |

#### 返回值

| 类型    | 说明                 |
|---------|----------------------|
| boolean | 是否创建了新的目录。 |

#### 示例

```javascript
fs.createDirectories("./a/b/c");
```

---

### createDirectory

创建目录。

#### 语法

```javascript
fs.createDirectory(path);
fs.createDirectory(path, attributes);
```

#### 参数

| 参数       | 类型   | 必填 | 说明                   |
|------------|--------|------|------------------------|
| path       | string | 是   | 目录路径               |
| attributes | string | 否   | 用于复制属性的参考目录 |

#### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 是否创建成功。 |

#### 示例

```javascript
fs.createDirectory("./logs");
```

---

### createDirectorySymlink

创建目录符号链接。

#### 语法

```javascript
fs.createDirectorySymlink(target, symlink);
```

#### 参数

| 参数    | 类型   | 必填 | 说明           |
|---------|--------|------|----------------|
| target  | string | 是   | 目标目录       |
| symlink | string | 是   | 新符号链接路径 |

#### 返回值

无。

#### 示例

```javascript
fs.createDirectorySymlink("./data", "./data_link");
```

---

### currentPath

获取或设置当前工作目录。

#### 语法

```javascript
fs.currentPath();
fs.currentPath(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明             |
|------|--------|------|------------------|
| path | string | 否   | 要设置的工作目录 |

#### 返回值

| 调用方式               | 返回值   |
|------------------------|----------|
| `fs.currentPath()`     | `string` |
| `fs.currentPath(path)` | 无       |

#### 示例

获取当前目录：

```javascript
const cwd = fs.currentPath();
```

设置当前目录：

```javascript
fs.currentPath("./workspace");
```

---

### exists

检查路径是否存在。

#### 语法

```javascript
fs.exists(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 路径是否存在。 |

#### 示例

```javascript
const exists = fs.exists("./config.json");

if (exists) {
    console.log("文件存在");
}
```

---

### equivalent

判断两个路径是否指向同一个文件或目录。

#### 语法

```javascript
fs.equivalent(path1, path2);
```

#### 参数

| 参数  | 类型   | 必填 | 说明       |
|-------|--------|------|------------|
| path1 | string | 是   | 第一个路径 |
| path2 | string | 是   | 第二个路径 |

#### 返回值

| 类型    | 说明                             |
|---------|----------------------------------|
| boolean | 两个路径是否表示同一文件或目录。 |

#### 示例

```javascript
const same = fs.equivalent("./a.txt", "./b.txt");
```

---

### fileSize

获取文件大小。

#### 语法

```javascript
fs.fileSize(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型   | 说明               |
|--------|--------------------|
| bigint | 文件大小（字节）。 |

#### 示例

```javascript
const size = fs.fileSize("./data.bin");

console.log(size);
```

---

### isBlockFile

判断路径是否为块设备文件。

#### 语法

```javascript
fs.isBlockFile(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明               |
|---------|--------------------|
| boolean | 是否为块设备文件。 |

#### 示例

```javascript
if (fs.isBlockFile("/dev/device")) {
    console.log("块设备");
}
```

---

### isCharacterFile

判断路径是否为字符设备文件。

#### 语法

```javascript
fs.isCharacterFile(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明                 |
|---------|----------------------|
| boolean | 是否为字符设备文件。 |

#### 示例

```javascript
const result = fs.isCharacterFile(path);
```

---

### isDirectory

判断路径是否为目录。

#### 语法

```javascript
fs.isDirectory(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型    | 说明         |
|---------|--------------|
| boolean | 是否为目录。 |

#### 示例

```javascript
if (fs.isDirectory("./plugins")) {
    console.log("这是一个目录");
}
```

---

### isEmpty

判断文件或目录是否为空。

#### 语法

```javascript
fs.isEmpty(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型    | 说明       |
|---------|------------|
| boolean | 是否为空。 |

#### 示例

```javascript
const empty = fs.isEmpty("./cache");
```

---

### isFifo

判断路径是否为 FIFO 管道文件。

#### 语法

```javascript
fs.isFifo(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明               |
|---------|--------------------|
| boolean | 是否为 FIFO 文件。 |

#### 示例

```javascript
const fifo = fs.isFifo("./pipe");
```

---

### isOther

判断路径是否为其他类型文件。

#### 语法

```javascript
fs.isOther(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明                 |
|---------|----------------------|
| boolean | 是否为其他类型文件。 |

#### 示例

```javascript
const result = fs.isOther("./file");
```

---

### isRegularFile

判断路径是否为普通文件。

#### 语法

```javascript
fs.isRegularFile(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明             |
|---------|------------------|
| boolean | 是否为普通文件。 |

#### 示例

```javascript
if (fs.isRegularFile("./config.json")) {
    console.log("普通文件");
}
```

---

### isSocket

判断路径是否为 Socket 文件。

#### 语法

```javascript
fs.isSocket(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |

#### 返回值

| 类型    | 说明                 |
|---------|----------------------|
| boolean | 是否为 Socket 文件。 |

#### 示例

```javascript
const socket = fs.isSocket("./socket");
```

---

### isSymlink

判断路径是否为符号链接。

#### 语法

```javascript
fs.isSymlink(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型    | 说明             |
|---------|------------------|
| boolean | 是否为符号链接。 |

#### 示例

```javascript
if (fs.isSymlink("./link")) {
    console.log("符号链接");
}
```

---

### lastWriteTime

获取或设置文件最后修改时间。

#### 语法

```javascript
fs.lastWriteTime(path);
fs.lastWriteTime(path, time);
```

#### 参数

| 参数 | 类型   | 必填 | 说明       |
|------|--------|------|------------|
| path | string | 是   | 文件路径   |
| time | bigint | 否   | 修改时间戳 |

#### 返回值

| 类型   | 说明                               |
|--------|------------------------------------|
| bigint | 文件最后修改时间（内部时间单位）。 |

#### 示例

获取修改时间：

```javascript
const time = fs.lastWriteTime("./config.json");
```

设置修改时间：

```javascript
fs.lastWriteTime("./config.json", 123456789n);
```

---

### permissions

修改文件或目录权限。

#### 语法

```javascript
fs.permissions(path, perms, options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                                                 |
|---------|--------|------|------------------------------------------------------|
| path    | string | 是   | 文件或目录路径                                       |
| perms   | number | 是   | 权限标志（对应 `std::filesystem::perms`）            |
| options | number | 否   | 权限修改选项（对应 `std::filesystem::perm_options`） |

#### 返回值

无。

#### 示例

```javascript
const fs = require("fs");

fs.permissions("./file.txt", 420);
```

---

### proximate

获取相对于指定基准路径的路径。

#### 语法

```javascript
fs.proximate(path);
fs.proximate(path, base);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 目标路径 |
| base | string | 否   | 基准路径 |

#### 返回值

| 类型   | 说明                 |
|--------|----------------------|
| string | 相对基准路径的路径。 |

#### 示例

```javascript
const result = fs.proximate("/home/user/file.txt");
```

指定基准路径：

```javascript
const result = fs.proximate(
    "/home/user/file.txt",
    "/home"
);
```

---

### readSymlink

读取符号链接指向的目标路径。

#### 语法

```javascript
fs.readSymlink(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明         |
|------|--------|------|--------------|
| path | string | 是   | 符号链接路径 |

#### 返回值

| 类型   | 说明               |
|--------|--------------------|
| string | 符号链接目标路径。 |

#### 示例

```javascript
const target = fs.readSymlink("./link");

console.log(target);
```

---

### relative

计算两个路径之间的相对路径。

#### 语法

```javascript
fs.relative(path);
fs.relative(path, base);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 目标路径 |
| base | string | 否   | 基准路径 |

#### 返回值

| 类型   | 说明       |
|--------|------------|
| string | 相对路径。 |

#### 示例

```javascript
const path = fs.relative("/home/user/file.txt");
```

指定基准路径：

```javascript
const path = fs.relative(
    "/home/user/file.txt",
    "/home"
);
```

---

### remove

删除文件或空目录。

#### 语法

```javascript
fs.remove(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明               |
|------|--------|------|--------------------|
| path | string | 是   | 要删除的文件或目录 |

#### 返回值

| 类型    | 说明           |
|---------|----------------|
| boolean | 是否成功删除。 |

#### 示例

```javascript
const removed = fs.remove("./temp.txt");
```

---

### removeAll

递归删除文件或目录。

#### 语法

```javascript
fs.removeAll(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明         |
|------|--------|------|--------------|
| path | string | 是   | 要删除的路径 |

#### 返回值

| 类型   | 说明                   |
|--------|------------------------|
| bigint | 删除的文件和目录数量。 |

#### 示例

```javascript
const count = fs.removeAll("./cache");

console.log(count);
```

---

### rename

重命名文件或目录。

#### 语法

```javascript
fs.rename(from, to);
```

#### 参数

| 参数 | 类型   | 必填 | 说明   |
|------|--------|------|--------|
| from | string | 是   | 原路径 |
| to   | string | 是   | 新路径 |

#### 返回值

无。

#### 示例

```javascript
fs.rename(
    "./old.txt",
    "./new.txt"
);
```

---

### resizeFile

调整文件大小。

#### 语法

```javascript
fs.resizeFile(path, size);
```

#### 参数

| 参数 | 类型   | 必填 | 说明               |
|------|--------|------|--------------------|
| path | string | 是   | 文件路径           |
| size | bigint | 是   | 新文件大小（字节） |

#### 返回值

无。

#### 示例

```javascript
fs.resizeFile(
    "./data.bin",
    1024n
);
```

---

### space

获取磁盘空间信息。

#### 语法

```javascript
fs.space(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

返回对象：

| 属性      | 类型   | 说明         |
|-----------|--------|--------------|
| capacity  | bigint | 磁盘总容量   |
| free      | bigint | 可用空间     |
| available | bigint | 用户可用空间 |

#### 示例

```javascript
const info = fs.space("./");

console.log(info.capacity);
console.log(info.free);
```

---

### status

获取文件状态信息。

#### 语法

```javascript
fs.status(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

返回对象：

| 属性        | 类型   | 说明     |
|-------------|--------|----------|
| type        | number | 文件类型 |
| permissions | number | 文件权限 |

#### 示例

```javascript
const status = fs.status("./file.txt");

console.log(status.type);
```

---

### symlinkStatus

获取符号链接自身状态信息。

#### 语法

```javascript
fs.symlinkStatus(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明               |
|------|--------|------|--------------------|
| path | string | 是   | 文件或符号链接路径 |

#### 返回值

返回对象：

| 属性        | 类型   | 说明     |
|-------------|--------|----------|
| type        | number | 文件类型 |
| permissions | number | 文件权限 |

#### 示例

```javascript
const status = fs.symlinkStatus("./link");
```

---

### tempDirectoryPath

获取系统临时目录路径。

#### 语法

```javascript
fs.tempDirectoryPath();
```

#### 参数

无。

#### 返回值

| 类型   | 说明           |
|--------|----------------|
| string | 临时目录路径。 |

#### 示例

```javascript
const temp = fs.tempDirectoryPath();

console.log(temp);
```

---

### weaklyCanonical

获取弱规范化路径。

与 `canonical` 不同，`weaklyCanonical` 允许路径中包含不存在的文件或目录。

#### 语法

```javascript
fs.weaklyCanonical(path);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| path | string | 是   | 文件或目录路径 |

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| string | 规范化后的路径。 |

#### 示例

```javascript
const path = fs.weaklyCanonical("./data/config.json");

console.log(path);
```

---

### list

遍历目录中的所有文件和目录。

#### 语法

```javascript
fs.list(path);
fs.list(path, options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明                                                  |
|---------|--------|------|-------------------------------------------------------|
| path    | string | 是   | 要遍历的目录路径                                      |
| options | number | 否   | 遍历选项（对应 `std::filesystem::directory_options`） |

#### 返回值

返回数组，每个元素包含：

| 属性        | 类型   | 说明                   |
|-------------|--------|------------------------|
| type        | number | 文件类型               |
| permissions | number | 文件权限               |
| size        | bigint | 文件大小（目录为 `0`） |
| time        | number | 最后修改时间           |
| name        | string | 文件名                 |
| path        | string | 完整路径               |

#### 示例

```javascript
const files = fs.list("./plugins");

for (const file of files) {
    console.log(file.name);
    console.log(file.path);
}
```

---

### read

读取文件内容。

#### 语法

```javascript
fs.read(path);
fs.read(path, encoding);
```

#### 参数

| 参数     | 类型   | 必填 | 说明         |
|----------|--------|------|--------------|
| path     | string | 是   | 文件路径     |
| encoding | string | 否   | 文件编码格式 |

支持编码：

| 编码             | 返回类型    | 说明           |
|------------------|-------------|----------------|
| `utf8` / `utf-8` | string      | 读取文本       |
| `binary` / `bin` | ArrayBuffer | 读取二进制数据 |

#### 返回值

| 类型                 | 说明       |
|----------------------|------------|
| string / ArrayBuffer | 文件内容。 |

#### 示例

读取文本：

```javascript
const content = fs.read("./config.json");

console.log(content);
```

读取二进制：

```javascript
const buffer = fs.read("./image.png", "binary");
```

---

### write

写入文件内容。

#### 语法

```javascript
fs.write(path, data);
fs.write(path, data, append);
```

#### 参数

| 参数   | 类型                                   | 必填 | 说明         |
|--------|----------------------------------------|------|--------------|
| path   | string                                 | 是   | 文件路径     |
| data   | string / ArrayBuffer / ArrayBufferView | 是   | 要写入的数据 |
| append | boolean                                | 否   | 是否追加写入 |

#### 返回值

无。

#### 示例

写入文本：

```javascript
fs.write(
    "./test.txt",
    "Hello World"
);
```

追加内容：

```javascript
fs.write(
    "./test.txt",
    "New Line",
    true
);
```

写入二进制：

```javascript
const buffer = new ArrayBuffer(8);

fs.write("./data.bin", buffer);
```

---

### chmod

修改文件权限。

#### 语法

```javascript
fs.chmod(path, mode);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| path | string | 是   | 文件路径 |
| mode | number | 是   | 权限模式 |

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| number | 系统调用返回值。 |

#### 示例

```javascript
const result = fs.chmod(
    "./script.sh",
    755
);
```

---

### chown

修改文件所有者。

#### 语法

```javascript
fs.chown(path, owner, group);
```

#### 参数

| 参数  | 类型   | 必填 | 说明      |
|-------|--------|------|-----------|
| path  | string | 是   | 文件路径  |
| owner | number | 是   | 用户 ID   |
| group | number | 是   | 用户组 ID |

#### 返回值

| 类型   | 说明             |
|--------|------------------|
| number | 系统调用返回值。 |

#### 示例

```javascript
const result = fs.chown(
    "./file.txt",
    1000,
    1000
);
```
