
### showTipMessage

**描述**: 显示提示信息。

**参数**:
- `s` - `string` - 提示信息内容

**返回值**: `boolean` - 显示成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isTipShown = showTipMessage("This is a tip message");
console.log("Tip Message Shown: " + isTipShown);
```

**注意事项**: 无

---

### setTitle

**描述**: 设置标题。

**参数**:
- `s` - `string` - 标题内容

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isTitleSet = setTitle("Game Title");
console.log("Title Set: " + isTitleSet);
```

**注意事项**: 无

---

### setSubtitle

**描述**: 设置子标题。

**参数**:
- `s` - `string` - 子标题内容

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isSubtitleSet = setSubtitle("Game Subtitle");
console.log("Subtitle Set: " + isSubtitleSet);
```

**注意事项**: 无

---

### clientMessage

**描述**: 客户端消息。

**参数**:
- `s` - `string` - 消息内容

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMessageSent = clientMessage("Hello Client");
console.log("Client Message Sent: " + isMessageSent);
```

**注意事项**: 无

---

### sendChatMessage

**描述**: 发送聊天消息。

**参数**:
- `s` - `string` - 聊天消息内容

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isChatMessageSent = sendChatMessage("Hello Chat");
console.log("Chat Message Sent: " + isChatMessageSent);
```

**注意事项**: 无

---

### whisperMessage

**描述**: 显示悄悄话消息。

**参数**:
- `user` - `string` - 用户昵称
- `message` - `string` - 聊天消息内容

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let status = whisperMessage("Steve","Hello Chat");
console.log("status: " + status);
```

**注意事项**: 无

---

### chatMessage

**描述**: 显示聊天消息。

**参数**:
- `user` - `string` - 用户昵称
- `message` - `string` - 聊天消息内容

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let status = chatMessage("Steve","Hello Chat");
console.log("status: " + status);
```

**注意事项**: 无

--

### showToast

**描述**: 发送系统提示。

**参数**:
- `message` - `string` - 内容

**返回值**: `boolean` - 发送成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let status = showToast("Hello Android");
console.log("status: " + status);
```

**注意事项**: 无

---

### getScreenSizeData

**描述**: 获取屏幕大小数据。

**参数**: 无

**返回值**: `SizeData`

**示例代码**:
```javascript
let data = getScreenSizeData();
console.log("ScreenSizeData: " + data);
```

**注意事项**: 无

---

### addCustomArrayList

**描述**: 添加自定义功能显示。

**参数**: 
- `functionId` - `string` - 功能唯一标识
- `longName` - `string` - 长名称
- `shortName` - `string` - 短名称
- `enabled` - `boolean` - 启用状态

**返回值**: `boolean` 状态

**示例代码**:
```javascript
let status = addCustomArrayList("func_test",'功能名称[Test] Value:123','功能名称',true);
console.log("status: " + status);
```

**注意事项**: 如果自定义功能已经添加，需要实现关闭请再次传入完整参数，并且把`enabled`设置为false

---

### removeCustomArrayList

**描述**: 移除自定义功能显示。

**参数**: 
- `functionId` - `string` - 功能唯一标识

**返回值**: `boolean` 状态

**示例代码**:
```javascript
let status = removeCustomArrayList("func_test");
console.log("status: " + status);
```

**注意事项**: 无

---

### createText

**描述**:  
创建一段文本并渲染到屏幕指定位置。

**参数**:
- `text` - `string` - 显示的文本内容
- `alignment` - `string` - 对齐方式，可为 `"Left"`、`"Center"`、`"Right"`
- `x` - `number` - 文本位置的 X 坐标
- `y` - `number` - 文本位置的 Y 坐标

**返回值**: `number` - 创建成功返回文本 ID（大于等于 0），失败返回 `-1`

**示例代码**:
```javascript
let id = createText("Hello World", "Center", 100, 200);
if (id >= 0) {
    console.log("Text created with ID:", id);
}
```

**注意事项**: 无

---

### updateTextContent

**描述**:  
更新指定文本对象的内容。

**参数**:
- `id` - `number` - 文本对象的 ID（由 `createText` 返回）
- `text` - `string` - 新的文本内容

**返回值**: 无

**示例代码**:
```javascript
updateTextContent(id, "Updated Text");
```

---

### updateTextPosition

**描述**:  
修改文本对象的位置坐标。

**参数**:
- `id` - `number` - 文本对象的 ID
- `x` - `number` - 新的 X 坐标
- `y` - `number` - 新的 Y 坐标

**返回值**: 无

**示例代码**:
```javascript
updateTextPosition(id, 150, 300);
```

---

### updateTextColor

**描述**:  
修改文本颜色（支持透明度）。

**参数**:
- `id` - `number` - 文本对象的 ID
- `r` - `number` - 红色通道 (0~1)
- `g` - `number` - 绿色通道 (0~1)
- `b` - `number` - 蓝色通道 (0~1)
- `a` - `number` - 透明度 (0~1)

**返回值**: 无

**示例代码**:
```javascript
updateTextColor(id, 1.0, 0.0, 0.0, 1.0); // 红色，不透明
```

---

### removeText

**描述**:  
移除指定 ID 的文本对象。

**参数**:
- `id` - `number` - 文本对象的 ID

**返回值**: 无

**示例代码**:
```javascript
removeText(id);
```

---

### updateTextScale

**描述**:
更新指定文本的缩放比例。

**参数**:

* `id` (`number`) - 文本标识符 ID。
* `scale` (`number`) - 缩放比例，通常为正浮点数，例如 `1.0` 表示原始大小，`1.5` 表示放大 1.5 倍。

**返回值**:
无返回值。

**示例代码**:

```javascript
updateTextScale(123, 1.2); // 将 ID 为 123 的文本缩放为原来的 1.2 倍
```

**注意事项**:

* 传入参数必须为数字类型，否则函数不会执行任何操作。
* 请确保 `id` 对应有效的文本元素。

---

### getScreenName

**描述**:
获取当前客户端正在显示的界面名称。

**参数**:
无

**返回值**:
`string` - 当前界面的名称，例如 `"start_screen"`、`"world_loading"` 等。

**示例代码**:

```javascript
let screen = getScreenName();
console.log("当前界面为:", screen);
```

**注意事项**:

* 仅返回当前客户端的顶层界面名称，可能用于调试或状态判断。

---

### simulateButtonDown

**描述**:
模拟玩家按下某个按钮的操作。

**参数**:

* `button` (`string`) - 要模拟按下的按钮名称，例如 `"attack"`, `"jump"` 等。

**返回值**:
无返回值。

**示例代码**:

```javascript
simulateButtonDown("jump");
```

**注意事项**:

* 需要确保传入的按钮名称合法，否则不会执行任何操作。

---

### simulateButtonUp

**描述**:
模拟玩家松开某个按钮的操作。

**参数**:

* `button` (`string`) - 要模拟松开的按钮名称，例如 `"attack"`, `"jump"` 等。

**返回值**:
无返回值。

**示例代码**:

```javascript
simulateButtonUp("jump");
```

**注意事项**:

* 需要确保传入的按钮名称合法，否则不会执行任何操作。
