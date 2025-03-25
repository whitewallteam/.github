
### loadMenu

**描述**: 加载UI菜单。

**参数**:
- `name` - `string` - 菜单名称
- `json` - `string` - 菜单的JSON表示

**返回值**: `boolean` - 加载成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMenuLoaded = loadMenu("mainMenu", "{\"title\":\"Main Menu\"}");
console.log("Menu Loaded: " + isMenuLoaded);
```

**注意事项**: 无

---

### removeMenu

**描述**: 移除UI菜单。

**参数**:
- `name` - `string` - 菜单名称

**返回值**: `boolean` - 移除成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMenuRemoved = removeMenu("mainMenu");
console.log("Menu Removed: " + isMenuRemoved);
```

**注意事项**: 无

---

### showMenu

**描述**: 显示UI菜单。

**参数**:
- `name` - `string` - 菜单名称

**返回值**: `boolean` - 显示成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMenuShown = showMenu("mainMenu");
console.log("Menu Shown: " + isMenuShown);
```

**注意事项**: 无

---

### hideMenu

**描述**: 隐藏UI菜单。

**参数**:
- `name` - `string` - 菜单名称

**返回值**: `boolean` - 隐藏成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isMenuHidden = hideMenu("mainMenu");
console.log("Menu Hidden: " + isMenuHidden);
```

**注意事项**: 无

---

### regFun

**描述**: 注册功能。

**参数**:
- `fun` - `string` - 功能名称

**返回值**: `boolean` - 注册成功返回 `true`，否则返回 `false`

**示例代码**:
```javascript
let isFunctionRegistered = regFun("customFunction");
console.log("Function Registered: " + isFunctionRegistered);
```

**注意事项**: 无
