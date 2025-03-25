
### getPlayerList

**描述**: 获取玩家列表。

**参数**: 无

**返回值**: `array(string)` - 玩家ID列表

**示例代码**:
```javascript
let playerList = getPlayerList();
console.log("Player List: ", playerList);
```

**注意事项**: 无

---

### getWorldPlayerList

**描述**: 获取世界玩家列表。

**参数**: 无

**返回值**: `array(Player)` - 世界玩家列表

**示例代码**:
```javascript
let worldPlayerList = getWorldPlayerList();
console.log("World Player List: ", worldPlayerList);
```

**注意事项**: 无

---

### executeCommand

**描述**: 执行命令。

**参数**:
- `cmd` - `string` - 要执行的命令

**返回值**: `boolean` - 命令执行成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isCommandExecuted = executeCommand("/give @p diamond 1");
console.log("Command Executed: " + isCommandExecuted);
```

**注意事项**: 无

---

### addForm

**描述**: 添加表单。

**参数**:
- `json` - `string` - 表单的JSON表示
- `callback` - `function` - 表单提交时的回调函数

**返回值**: `boolean` - 添加成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
// 普通表单
const form = `
    {
        "type": "form",
        "title": "菜单标题",
        "content": "菜单内容",
        "buttons": [
            {
                "text": "菜单按钮0"
            },
            {
                "text": "菜单按钮1",
                "image": {
                    "type": "path",
                    "data": "textures/ui/anvil_icon.png"
                }
            },
            {
                "text": "菜单按钮2",
                "image": {
                    "type": "url",
                    "data": "https://xxx.png"
                }
            }
        ]
    }
`;
addForm(form, function (index) {
    clientMessage('当前选择的是第' + index + '个选项')
})

// 自定义表单
const custom_form = `
  {
    "type": "custom_form",
    "title": "菜单标题",
    "content": [
      {
        "type": "label",
        "text": "普通文本"
      },
      {
        "type": "input",
        "text": "输入框",
        "default": "默认文字",
        "placeholder": "提示文字"
      },
      {
        "type": "toggle",
        "text": "开关按钮",
        "default": false
      },
      {
        "type": "dropdown",
        "text": "多选",
        "options": ["选项1", "选项2", "选项3"]
      },
      {
        "type": "slider",
        "text": "进度条",
        "min": 1,
        "max": 10,
        "step": 1,
        "default": 2
      },
      {
        "type": "step_slider",
        "text": "滑动选择",
        "steps": ["选项1", "选项2", "选项3"],
        "default": 1
      }
    ]
  }
`;
addForm(custom_form, function (...args) {
    clientMessage('选择完成',args[1])
})
```

**注意事项**: 无

---

### removeEntity

**描述**: 从世界移除实体。

**参数**:
- `id` - `string` - 实体的唯一标识

**返回值**: `boolean` - 移除成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isEntityRemoved = removeEntity("entity123");
console.log("Entity Removed: " + isEntityRemoved);
```

**注意事项**: 无

---

### findStructure

**描述**: 寻找指定结构。

**参数**:
- `x` - `number` - X 坐标
- `y` - `number` - Y 坐标
- `z` - `number` - Z 坐标
- `name` - `string` - 结构名称

**返回值**: `WorldStruct` - 结构数据

**示例代码**:
```javascript
let structure = findStructure(100, 64, 100, "Village");
console.log("Found Structure: ", structure);
```

**注意事项**: 无

---

### addParticle

**描述**: 添加粒子。

**参数**:
- `type` - `number` - 粒子类型
- `start_x` - `number` - X坐标
- `start_y` - `number` - Y坐标
- `start_z` - `number` - Z坐标
- `offset_x` - `number` - 偏移X坐标
- `offset_y` - `number` - 偏移Y坐标
- `offset_z` - `number` - 偏移Z坐标
- `size` - `number` - 粒子大小
- `animation` - `boolean` - 动画`v7.0.5`

**返回值**: `boolean` - 添加成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isParticleAdded = addParticle(1, 100, 64, 100, 110, 65, 110, 1);
console.log("Particle Added: " + isParticleAdded);
```

**注意事项**: 无

---

### getWorldData

**描述**: 获取世界数据。

**参数**: 无

**返回值**: `WorldData` - 世界数据

**示例代码**:
```javascript
let worldData = getWorldData();
console.log("World Data: ", worldData);
```

**注意事项**: 无

---

### setWorldData

**描述**: 设置世界数据。

**参数**:
- `data` - `WorldData` - 要设置的世界数据

**返回值**: `boolean` - 设置成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let newWorldData = { difficulty:1 };
let isWorldDataSet = setWorldData(newWorldData);
console.log("World Data Set: " + isWorldDataSet);
```

**注意事项**: 确保传入的世界数据格式正确。

---

### leaveWorld

**描述**: 让玩家退出当前世界。

**参数**: 无

**返回值**: 无。

**示例代码**:
```javascript
leaveWorld();
```

**注意事项**:
- 在调用前确保已保存当前世界的进度，否则可能会导致数据丢失。
