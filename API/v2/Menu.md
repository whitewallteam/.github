`menu` 模块提供菜单管理相关 API，包括菜单加载、移除、显示、隐藏以及注册菜单功能等操作。

通过 `require` 获取：

```javascript
const menu = require("menu");
```

---

### load

加载一个菜单。

#### 语法

```javascript
menu.load(name, root);
```

#### 参数

| 参数 | 类型   | 必填 | 说明           |
|------|--------|------|----------------|
| name | string | 是   | 菜单名称       |
| root | string | 是   | 菜单根目录路径 |

#### 返回值

返回菜单加载结果。

#### 示例

```javascript
const menu = require("menu");

const result = menu.load("test", "/sdcard/menu");

console.log(result);
```

---

### remove

移除一个已加载的菜单。

#### 语法

```javascript
menu.remove(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 菜单名称 |

#### 返回值

返回菜单移除结果。

#### 示例

```javascript
const menu = require("menu");

const result = menu.remove("test");

console.log(result);
```

---

### show

显示指定菜单。

#### 语法

```javascript
menu.show(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 菜单名称 |

#### 返回值

返回菜单显示结果。

#### 示例

```javascript
const menu = require("menu");

const result = menu.show("test");

console.log(result);
```

---

### hide

隐藏指定菜单。

#### 语法

```javascript
menu.hide(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 菜单名称 |

#### 返回值

返回菜单隐藏结果。

#### 示例

```javascript
const menu = require("menu");

const result = menu.hide("test");

console.log(result);
```

---

### regFun

注册菜单功能。

#### 语法

```javascript
menu.regFun(name);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| name | string | 是   | 功能名称 |

#### 返回值

返回功能注册结果。

#### 示例

```javascript
const menu = require("menu");

const result = menu.regFun("myFunction");

console.log(result);
```
