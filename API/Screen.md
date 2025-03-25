
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
