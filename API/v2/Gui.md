`gui` 模块提供游戏界面相关 API，包括创建自定义文本渲染、添加 HUD ArrayList 项、获取屏幕尺寸、获取当前界面名称以及创建表单等功能。

通过 `require` 获取：

```javascript
const gui = require("gui");
````

---

## Text

创建一个可渲染到屏幕上的文本对象。

#### 构造函数

#### 语法

```javascript
new gui.Text(options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明         |
|---------|--------|------|--------------|
| options | object | 是   | 文本配置对象 |

`options` 对象：

| 参数       | 类型   | 必填 |                                                    |
|------------|--------|------|----------------------------------------------------|
| content    | string | 否   | 文本内容                                           |
| alignment  | string | 否   | 文本对齐方式，可选 `"Left"`、`"Center"`、`"Right"` |
| position   | object | 否`  | 文本位置                                           |
| position.x | number | 否   | X 坐标                                             |
| position.y | number | 否   | Y 坐标                                             |
| color      | object | 否   | 文本颜色                                           |
| color.r    | number | 否   | 红色通道                                           |
| color.g    | number | 否   | 绿色通道                                           |
| color.b    | number | 否   | 蓝色通道                                           |
| color.a    | number | 否   | Alpha 通道                                         |
| scale      | number | 否   | 文本缩放比例                                       |

#### 返回值

返回 `Text` 对象。

#### 示例

```javascript
const gui = require("gui");

const text = new gui.Text({
    content: "Hello World",
    position: {
        x: 100,
        y: 100
    },
    color: {
        r: 1,
        g: 1,
        b: 1,
        a: 1
    },
    scale: 1
});
```

---

#### 属性

### content

获取或设置文本内容。

类型：

```javascript
string
```

示例：

```javascript
text.content = "新的文本";
```

---

### alignment

获取或设置文本对齐方式。

类型：

```javascript
string
```

可选值：

| 值     | 说明     |
|--------|----------|
| Left   | 左对齐   |
| Center | 居中对齐 |
| Right  | 右对齐   |

示例：

```javascript
text.alignment = "Center";
```

---

### position

获取或设置文本位置。

类型：

```javascript
object
```

结构：

```
{
    x: number,
    y: number
}
```

示例：

```javascript
text.position = {
    x: 200,
    y: 300
};
```

---

### color

获取或设置文本颜色。

类型：

```javascript
object
```

结构：

```
{
    r: number,
    g: number,
    b: number,
    a: number
}
```

示例：

```javascript
text.color = {
    r: 1,
    g: 0,
    b: 0,
    a: 1
};
```

---

### scale

获取或设置文本缩放比例。

类型：

```javascript
number
```

示例：

```javascript
text.scale = 2;
```

---

### remove

移除文本对象。

#### 语法

```javascript
text.remove();
```

#### 返回值

无。

#### 示例

```javascript
text.remove();
```

---

## ArrayList

创建一个 HUD ArrayList 项。

#### 构造函数

#### 语法

```javascript
new gui.ArrayList(options);
```

#### 参数

| 参数    | 类型   | 必填 | 说明               |
|---------|--------|------|--------------------|
| options | object | 是   | ArrayList 配置对象 |

`options` 对象：

| 参数        | 类型    | 必填 | 默认值 | 说明         |
|-------------|---------|------|--------|--------------|
| function    | string  | 是   |        | 唯一标识名称 |
| name        | string  | 否   |        | 显示名称     |
| shortName   | string  | 否   |        | 简短名称     |
| enabled     | boolean | 否   | false  | 是否启用     |
| screenPos   | object  | 否   |        | 屏幕位置     |
| screenPos.x | number  | 否   | 0      | X 坐标       |
| screenPos.y | number  | 否   | 0      | Y 坐标       |

#### 返回值

返回 `ArrayList` 对象。

#### 示例

```javascript
const gui = require("gui");

const item = new gui.ArrayList({
    function: "test",
    name: "测试功能",
    shortName: "TEST",
    enabled: true,
    screenPos: {
        x: 10,
        y: 20
    }
});
```

---

#### 属性

### name

获取或设置显示名称。

类型：

```javascript
string
```

示例：

```javascript
item.name = "自动攻击";
```

---

### shortName

获取或设置简短名称。

类型：

```javascript
string
```

示例：

```javascript
item.shortName = "KillAura";
```

---

### enabled

获取或设置启用状态。

类型：

```javascript
boolean
```

示例：

```javascript
item.enabled = true;
```

---

### screenPos

获取或设置屏幕位置。

类型：

```javascript
object
```

结构：

```
{
    x: number,
    y: number
}
```

示例：

```javascript
item.screenPos = {
    x: 100,
    y: 50
};
```

---

### remove

移除 ArrayList 项。

#### 语法

```javascript
item.remove();
```

#### 返回值

无。

#### 示例

```javascript
item.remove();
```

---

## getSizeData

获取当前游戏 GUI 尺寸信息。

#### 语法

```javascript
gui.getSizeData();
```

#### 返回值

返回对象：

```
{
    totalScreenSizeWidth: number,
    totalScreenSizeHeight: number,
    clientUIScreenWidth: number,
    clientUIScreenHeight: number,
    clientScreenWidth: number,
    clientScreenHeight: number
}
```

| 属性                  | 类型   | 说明           |
|-----------------------|--------|----------------|
| totalScreenSizeWidth  | number | 总屏幕宽度     |
| totalScreenSizeHeight | number | 总屏幕高度     |
| clientUIScreenWidth   | number | UI 屏幕宽度    |
| clientUIScreenHeight  | number | UI 屏幕高度    |
| clientScreenWidth     | number | 客户端屏幕宽度 |
| clientScreenHeight    | number | 客户端屏幕高度 |

#### 示例

```javascript
const size = gui.getSizeData();

console.log(size.clientScreenWidth);
```

---

## getCurrentScreenName

获取当前打开的界面名称。

#### 语法

```javascript
gui.getCurrentScreenName();
```

#### 返回值

| 类型   | 说明         |
|--------|--------------|
| string | 当前界面名称 |

#### 示例

```javascript
const screen = gui.getCurrentScreenName();

console.log(screen);
```

---

## addForm

添加一个游戏表单。

#### 语法

```javascript
gui.addForm(json, callback, cancelCallback);
```

#### 参数

| 参数           | 类型     | 必填 | 说明                |
|----------------|----------|------|---------------------|
| json           | string   | 是   | JSON 格式的表单配置 |
| callback       | function | 是   | 表单提交后的回调    |
| cancelCallback | function | 否   | 取消表单后的回调    |

---

#### callback 参数

参数：

| 参数  | 类型           | 说明           |
|-------|----------------|----------------|
| value | number / array | 表单返回的数据 |

当表单返回多个数据时：

```
[
    value1,
    value2
]
```

---

#### 示例

```javascript
const gui = require("gui");

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
gui.addForm(form, (index) => {
    console.log('当前选择的是第' + index + '个选项')
}, () => {
    console.log("取消");
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
gui.addForm(custom_form, (input, toggle, dropdown, slider, step_slider) => {
    console.log('选择完成', input, toggle, dropdown, slider, step_slider)
}, () => {
    console.log("取消");
})
```

