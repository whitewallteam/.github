
### file_list

**描述**: 获取文件列表。

**参数**:
- `path` - `string` - 文件夹路径

**返回值**: `array(File)` - 文件列表

**示例代码**:
```javascript
let fileList = file_list("/path/to/directory");
console.log("File List: ", fileList);
```

**注意事项**: 无

---

### file_exist

**描述**: 判断文件/文件夹存在。

**参数**:
- `path` - `string` - 文件或文件夹路径

**返回值**: `boolean` - 存在返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let doesExist = file_exist("/path/to/file");
console.log("File Exists: " + doesExist);
```

**注意事项**: 无

---

### file_delete

**描述**: 删除文件/文件夹。

**参数**:
- `path` - `string` - 文件或文件夹路径

**返回值**: `boolean` - 删除成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isDeleted = file_delete("/path/to/file");
console.log("File Deleted: " + isDeleted);
```

**注意事项**: 无

---

### file_rename

**描述**: 重命名文件/文件夹。

**参数**:
- `path` - `string` - 原文件或文件夹路径
- `new_path` - `string` - 新文件或文件夹路径

**返回值**: `boolean` - 重命名成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isRenamed = file_rename("/path/to/file", "/path/to/new_file");
console.log("File Renamed: " + isRenamed);
```

**注意事项**: 无

---

### file_create_dir

**描述**: 创建文件夹。

**参数**:
- `path` - `string` - 文件夹路径

**返回值**: `boolean` - 创建成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isDirCreated = file_create_dir("/path/to/new_directory");
console.log("Directory Created: " + isDirCreated);
```

**注意事项**: 无

---

### read_file

**描述**: 读取文件内容。

**参数**:
- `path` - `string` - 文件路径

**返回值**: `string` - 文件内容

**示例代码**:
```javascript
let fileContent = read_file("/path/to/file");
console.log("File Content: " + fileContent);
```

**注意事项**: 无

---

### write_file

**描述**: 写入文件内容。

**参数**:
- `path` - `string` - 文件路径
- `data` - `string` - 要写入的数据

**返回值**: `boolean` - 写入成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isFileWritten = write_file("/path/to/file", "File content");
console.log("File Written: " + isFileWritten);
```

**注意事项**: 无

---

### File.list

**描述**:  
获取指定路径下的文件列表。

**参数**:  
- `path` - `string` - 目录路径。

**返回值**:  
`array<File>` - 该目录下的文件数组。

**示例代码**:  
```javascript
let files = File.list("path/to/directory");
console.log(files);
```

**注意事项**:  
- 仅适用于目录路径，若 `path` 指向文件，则可能返回空数组或错误。  

---

### File.exist

**描述**:  
检查指定路径的文件或目录是否存在。

**参数**:  
- `path` - `string` - 文件或目录路径。

**返回值**:  
`boolean` - 存在返回 `true`，否则返回 `false`。

**示例代码**:  
```javascript
if (File.exist("path/to/file.txt")) {
    console.log("File exists.");
}
```

**注意事项**:  
- 适用于文件和目录。

---

### File.delete

**描述**:  
删除指定路径的文件或目录。

**参数**:  
- `path...` - `string` - 需要删除的文件或目录路径（可变参数）。

**返回值**:  
`void`

**示例代码**:  
```javascript
File.delete("path/to/file.txt", "path/to/another_file.txt");
```

**注意事项**:  
- 删除目录时，需确保目录为空或支持递归删除。  

---

### File.rename

**描述**:  
重命名或移动文件/目录。

**参数**:  
- `path` - `string` - 需要重命名或移动的文件/目录路径。  
- `newPath` - `string` - 新文件/目录路径。  

**返回值**:  
`void`

**示例代码**:  
```javascript
File.rename("old_name.txt", "new_name.txt");
```

**注意事项**:  
- 若 `newPath` 已存在，可能会覆盖或导致错误。  

---

### File.createDir

**描述**:  
创建单级目录。

**参数**:  
- `path` - `string` - 需要创建的目录路径。

**返回值**:  
`void`

**示例代码**:  
```javascript
File.createDir("path/to/directory");
```

**注意事项**:  
- 仅能创建单级目录，若上级目录不存在，则可能失败。  

---

### File.mkdirs

**描述**:  
创建多级目录。

**参数**:  
- `path` - `string` - 需要创建的目录路径。

**返回值**:  
`void`

**示例代码**:  
```javascript
File.mkdirs("path/to/multiple/directories");
```

**注意事项**:  
- 可递归创建不存在的父目录。  

---

### File.read

**描述**:  
读取指定路径的文本文件内容。

**参数**:  
- `path` - `string` - 需要读取的文件路径。

**返回值**:  
`string` - 文件内容。

**示例代码**:  
```javascript
let content = File.read("path/to/file.txt");
console.log(content);
```

**注意事项**:  
- 适用于文本文件，二进制文件可能导致乱码。  

---

### File.readBinary

**描述**:  
以二进制方式读取指定文件内容。

**参数**:  
- `path` - `string` - 需要读取的文件路径。

**返回值**:  
`ArrayBuffer` - 二进制数据。

**示例代码**:  
```javascript
let binaryData = File.readBinary("path/to/file.bin");
console.log(binaryData);
```

**注意事项**:  
- 适用于二进制文件，如图片、音频、视频等。  

---

### File.write

**描述**:  
将文本内容写入指定路径的文件。

**参数**:  
- `path` - `string` - 需要写入的文件路径。  
- `content` - `string` - 需要写入的文本内容。  

**返回值**:  
`void`

**示例代码**:  
```javascript
File.write("path/to/file.txt", "Hello, World!");
```

**注意事项**:  
- 如果文件已存在，将覆盖原内容。  

---

### File.writeBinary

**描述**:  
以二进制方式写入文件。

**参数**:  
- `path` - `string` - 需要写入的文件路径。  
- `content` - `ArrayBuffer` - 需要写入的二进制数据。  

**返回值**:  
`void`

**示例代码**:  
```javascript
let buffer = new ArrayBuffer(8);
File.writeBinary("path/to/file.bin", buffer);
```

**注意事项**:  
- 适用于二进制数据存储，如图片、音频等。  

