`input` 模块提供模拟游戏输入相关 API，包括鼠标点击、按键按下以及按键释放等功能。

通过 `require` 获取：

```javascript
const input = require("input");
````

---

### click

模拟一次鼠标左键点击操作。

该 API 等价于执行一次 `buttonDown("button.build_or_attack")` 和 `buttonUp("button.build_or_attack")`。

#### 语法

```javascript
input.click();
```

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
const input = require("input");

input.click();
```

---

### buttonDown

模拟按下指定游戏按键。

#### 语法

```javascript
input.buttonDown(button);
```

#### 参数

| 参数   | 类型   | 必填 | 说明     |
|--------|--------|------|----------|
| button | string | 是   | 按键名称 |

#### 返回值

无。

#### 示例

模拟按下攻击/破坏键：

```javascript
const input = require("input");

input.buttonDown("button.build_or_attack");
```

---

### buttonUp

模拟释放指定游戏按键。

#### 语法

```javascript
input.buttonUp(button);
```

#### 参数

| 参数   | 类型   | 必填 | 说明     |
|--------|--------|------|----------|
| button | string | 是   | 按键名称 |

#### 返回值

无。

#### 示例

模拟释放攻击/破坏键：

```javascript
const input = require("input");

input.buttonUp("button.build_or_attack");
```

