`ImGui` 模块提供 ImGui 渲染功能。

通过 `require` 获取：

```javascript
const ImGui = require("ImGui");
````

---

## AccessValue

用于创建一个可被 ImGui 控件直接读写的值对象。

由于 JavaScript 的基本类型（`boolean`、`number`、`string`）按值传递，因此当 ImGui 控件需要修改变量时，需要使用 `AccessValue`
包装对应的数据。

创建后的值可通过 `value` 属性进行读取或修改。

#### 构造函数

#### new AccessValue (value)

根据传入值自动推断数据类型。

#### 参数

| 类型                        | 名称  | 说明     |
|-----------------------------|-------|----------|
| boolean \| number \| string | value | 初始值。 |

#### 示例

```javascript
const boolValue = new ImGui.AccessValue(true);
const intValue = new ImGui.AccessValue(100);
const floatValue = new ImGui.AccessValue(3.14);
const stringValue = new ImGui.AccessValue("Hello");
```

---

#### new AccessValue (value, type)

根据指定类型创建一个值对象。

#### 参数

| 类型   | 名称  | 说明                                                         |
|--------|-------|--------------------------------------------------------------|
| any    | value | 初始值。                                                     |
| string | type  | 数据类型，可选值：`"bool"`、`"int"`、`"float"`、`"string"`。 |

#### 示例

```javascript
const value1 = new ImGui.AccessValue(1, "bool");
const value2 = new ImGui.AccessValue(10, "int");
const value3 = new ImGui.AccessValue(10, "float");
const value4 = new ImGui.AccessValue(123, "string");
```

### value

获取或修改当前保存的数据。

#### 类型

```typescript
boolean | number | string
```

#### 示例

```javascript
const value = new ImGui.AccessValue(false);

console.log(value.value);
// false

value.value = true;

console.log(value.value);
// true
```

```javascript
const text = new ImGui.AccessValue("Hello");

text.value = "World";

console.log(text.value);
// World
```

#### 类型推断规则

当未指定 `type` 参数时，会自动推断数据类型：

| JavaScript 值 | 保存类型 |
|---------------|----------|
| boolean       | bool     |
| string        | string   |
| 整数 number   | int      |
| 浮点数 number | float    |

例如：

```javascript
new ImGui.AccessValue(10);      // int
new ImGui.AccessValue(10.5);    // float
new ImGui.AccessValue(true);    // bool
new ImGui.AccessValue("abc");   // string
```

#### 注意事项

- 必须使用 `new` 创建对象，否则会抛出 `TypeError`。
- 不支持 `Object`、`Array`、`Function`、`null`、`undefined` 等类型。
- 指定 `type` 时，仅支持以下字符串：
    - `"bool"`
    - `"int"`
    - `"float"`
    - `"string"`
- 修改 `value` 属性时，会按照创建时的数据类型进行转换：
    - `bool`：转换为布尔值。
    - `int`：转换为 32 位整数。
    - `float`：转换为浮点数。
    - `string`：转换为字符串。
- `AccessValue` 主要用于需要引用传递的 ImGui API，例如 `Checkbox`、`InputText`、`SliderInt`、`SliderFloat` 等控件。

---

下面是根据代码整理出的文档，与前面的 `AccessValue` 保持同一风格。

---

````markdown
# ImGui.Vec2

用于创建一个二维向量对象，可用于 ImGui 中需要 `ImVec2` 参数的接口，例如窗口位置、窗口大小、按钮尺寸等。

## 构造函数

### new Vec2 (x, y)

根据坐标创建一个二维向量。

#### 参数

| 类型 | 名称 | 说明 |
|------|------|------|
| number | x | X 坐标。 |
| number | y | Y 坐标。 |

#### 示例

```javascript
const pos = new ImGui.Vec2(100, 200);
```

---

### new Vec2 (value)

根据对象创建二维向量。

#### 参数

| 类型 | 名称 | 说明 |
|------|------|------|
| object | value | 包含 `x`、`y` 属性的对象。 |

#### 示例

```javascript
const pos = new ImGui.Vec2({
    x: 100,
    y: 200
});
```

## 属性

### value

获取或设置整个向量。

#### 类型

```typescript
{
    x: number;
    y: number;
}
```

#### 示例

```javascript
const pos = new ImGui.Vec2(100, 200);

console.log(pos.value);

pos.value = {
    x: 300,
    y: 400
};
```

---

### x

X 坐标。

#### 类型

```typescript
number
```

#### 示例

```javascript
const pos = new ImGui.Vec2(10, 20);

pos.x = 50;

console.log(pos.x);
```

---

### y

Y 坐标。

#### 类型

```typescript
number
```

#### 示例

```javascript
const pos = new ImGui.Vec2(10, 20);

pos.y = 80;

console.log(pos.y);
```

## 注意事项

- 必须使用 `new` 创建对象。
- `value` 必须是包含 `x`、`y` 的对象。
- `x`、`y` 必须为数字类型。
````

---

## Vec4

用于创建一个四维向量对象，可用于 ImGui 中需要 `ImVec4` 参数的接口，例如颜色（RGBA）、矩形区域等。

#### 构造函数

#### new Vec4 (x, y, z, w)

根据四个坐标创建一个四维向量。

#### 参数

| 类型   | 名称 | 说明         |
|--------|------|--------------|
| number | x    | 第一个分量。 |
| number | y    | 第二个分量。 |
| number | z    | 第三个分量。 |
| number | w    | 第四个分量。 |

#### 示例

```javascript
const color = new ImGui.Vec4(1.0, 0.5, 0.2, 1.0);
```

---

#### new Vec4 (value)

根据对象创建四维向量。

#### 参数

| 类型   | 名称  | 说明                                 |
|--------|-------|--------------------------------------|
| object | value | 包含 `x`、`y`、`z`、`w` 属性的对象。 |

#### 示例

```javascript
const color = new ImGui.Vec4({
    x: 1,
    y: 0,
    z: 0,
    w: 1
});
```

### value

获取或设置整个四维向量。

#### 类型

```typescript
{
    x: number;
    y: number;
    z: number;
    w: number;
}
```

#### 示例

```javascript
const color = new ImGui.Vec4(1, 1, 1, 1);

color.value = {
    x: 0,
    y: 1,
    z: 0,
    w: 1
};
```

---

### x

第一个分量。

```typescript
number
```

---

### y

第二个分量。

```typescript
number
```

---

### z

第三个分量。

```typescript
number
```

---

### w

第四个分量。

```typescript
number
```

#### 示例

```javascript
const color = new ImGui.Vec4(1, 0, 0, 1);

color.z = 0.5;
color.w = 0.8;
```

#### 注意事项

- 必须使用 `new` 创建对象。
- `value` 必须包含 `x`、`y`、`z`、`w` 四个字段。
- 四个分量均为数字类型。

## Tuple

用于创建一个数值数组对象，可用于 ImGui 中需要多个连续数值参数的接口，例如多组件输入框、滑块等。

根据传入参数自动推断为整数数组或浮点数组。

#### 构造函数

#### new Tuple (...values)

创建一个数值数组。

#### 参数

| 类型   | 名称   | 说明             |
|--------|--------|------------------|
| number | values | 一个或多个数值。 |

#### 示例

整数数组：

```javascript
const tuple = new ImGui.Tuple(1, 2, 3);
```

浮点数组：

```javascript
const tuple = new ImGui.Tuple(1.0, 2.5, 3.8);
```

#### 类型推断

构造时根据第一个参数自动推断类型。

| 第一个参数 | 保存类型 |
|------------|----------|
| 整数       | int[]    |
| 浮点数     | float[]  |

后续参数会按照该类型进行收集。

例如：

```javascript
new ImGui.Tuple(1, 2, 3);        // int[]
new ImGui.Tuple(1.0, 2.0, 3.0);  // float[]
```

### value

获取或设置整个数组。

#### 类型

```
number[]
```

#### 示例

```javascript
const tuple = new ImGui.Tuple(1, 2, 3);

console.log(tuple.value);

tuple.value = [10, 20, 30];
```

浮点数组：

```javascript
const tuple = new ImGui.Tuple(1.5, 2.5);

tuple.value = [
    3.2,
    5.4
];
```

#### 注意事项

- 必须使用 `new` 创建对象。
- 至少需要传入一个数字参数。
- 第一个参数决定整个数组的数据类型。
- 设置 `value` 时必须传入数组。
- 当数组中存在非数值元素时，这些元素会被忽略。
- 如果设置后的数组为空，则不会修改原有数据。

---

## DrawList

用于访问 ImGui 的底层绘制列表。

`DrawList` 提供了直接绘制图形的能力，可以绘制线条、矩形、多边形、圆形、文本等内容。

通过 ImGui 内部 API 获取 `DrawList` 后使用。

---

### PushClipRect

设置裁剪区域。

#### 参数

| 类型    | 名称        | 说明                     |
|---------|-------------|--------------------------|
| Vector2 | clipRectMin | 裁剪区域左上角。         |
| Vector2 | clipRectMax | 裁剪区域右下角。         |
| boolean | intersect   | 是否与当前裁剪区域合并。 |

#### 示例

```javascript
drawList.PushClipRect(
    {x: 0, y: 0},
    {x: 100, y: 100},
    true
);
```

---

### PushClipRectFullScreen

设置裁剪区域为整个屏幕。

#### 示例

```javascript
drawList.PushClipRectFullScreen();
```

---

### PopClipRect

恢复之前的裁剪区域。

#### 示例

```javascript
drawList.PopClipRect();
```

---

### PushTexture

设置当前绘制纹理。

#### 参数

| 类型     | 名称    | 说明          |
|----------|---------|---------------|
| External | texture | ImTextureID。 |

#### 示例

```javascript
drawList.PushTexture(texture);
```

---

### PopTexture

恢复之前的纹理状态。

```javascript
drawList.PopTexture();
```

---

### GetClipRectMin

获取当前裁剪区域左上角。

#### 返回值

| 类型    | 说明   |
|---------|--------|
| Vector2 | 坐标。 |

---

### GetClipRectMax

获取当前裁剪区域右下角。

#### 返回值

| 类型    | 说明   |
|---------|--------|
| Vector2 | 坐标。 |

---

### AddLine

绘制一条线。

#### 参数

| 类型    | 名称      | 说明               |
|---------|-----------|--------------------|
| Vector2 | p1        | 起点。             |
| Vector2 | p2        | 终点。             |
| number  | color     | 颜色值。           |
| number  | thickness | 线宽，默认 `1.0`。 |

#### 示例

```javascript
drawList.AddLine(
    {x: 0, y: 0},
    {x: 100, y: 100},
    0xffffffff,
    2
);
```

---

### AddLineH

绘制水平线。

#### 参数

| 类型   | 名称      |
|--------|-----------|
| number | minX      |
| number | maxX      |
| number | y         |
| number | color     |
| number | thickness |

---

### AddLineV

绘制垂直线。

#### 参数

| 类型   | 名称      |
|--------|-----------|
| number | x         |
| number | minY      |
| number | maxY      |
| number | color     |
| number | thickness |

---

### AddRect

绘制矩形边框。

#### 参数

| 类型    | 名称      | 默认值 |
|---------|-----------|--------|
| Vector2 | min       |        |
| Vector2 | max       |        |
| number  | color     |        |
| number  | rounding  | 0      |
| number  | thickness | 1      |
| number  | flags     | 0      |

---

### AddRectFilled

绘制填充矩形。

#### 参数

| 类型    | 名称     |
|---------|----------|
| Vector2 | min      |
| Vector2 | max      |
| number  | color    |
| number  | rounding |
| number  | flags    |

---

### AddRectFilledMultiColor

绘制四角渐变矩形。

#### 参数

| 类型    | 名称             |
|---------|------------------|
| Vector2 | min              |
| Vector2 | max              |
| number  | colorTopLeft     |
| number  | colorTopRight    |
| number  | colorBottomRight |
| number  | colorBottomLeft  |

---

### AddQuad

绘制四边形边框。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | p1        |
| Vector2 | p2        |
| Vector2 | p3        |
| Vector2 | p4        |
| number  | color     |
| number  | thickness |

---

### AddQuadFilled

绘制填充四边形。

#### 参数

同 `AddQuad`，但无 thickness。

---

### AddTriangle

绘制三角形边框。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | p1        |
| Vector2 | p2        |
| Vector2 | p3        |
| number  | color     |
| number  | thickness |

---

### AddTriangleFilled

绘制填充三角形。

#### 参数

| 类型    | 名称  |
|---------|-------|
| Vector2 | p1    |
| Vector2 | p2    |
| Vector2 | p3    |
| number  | color |

---

### AddCircle

绘制圆形边框。

#### 参数

| 类型    | 名称      | 默认 |
|---------|-----------|------|
| Vector2 | center    |
| number  | radius    |
| number  | color     |
| number  | segments  | 0    |
| number  | thickness | 1    |

---

### AddCircleFilled

绘制填充圆。

#### 参数

| 类型    | 名称     |
|---------|----------|
| Vector2 | center   |
| number  | radius   |
| number  | color    |
| number  | segments |

---

### AddNgon

绘制正多边形边框。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | center    |
| number  | radius    |
| number  | color     |
| number  | segments  |
| number  | thickness |

---

### AddNgonFilled

绘制填充正多边形。

#### 参数

| 类型    | 名称     |
|---------|----------|
| Vector2 | center   |
| number  | radius   |
| number  | color    |
| number  | segments |

---

### AddEllipse

绘制椭圆边框。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | center    |
| Vector2 | radius    |
| number  | color     |
| number  | rotation  |
| number  | segments  |
| number  | thickness |

---

### AddEllipseFilled

绘制填充椭圆。

#### 参数

| 类型    | 名称     |
|---------|----------|
| Vector2 | center   |
| Vector2 | radius   |
| number  | color    |
| number  | rotation |
| number  | segments |

---

### AddText

绘制文本。

#### 参数

| 类型    | 名称     |
|---------|----------|
| Vector2 | position |
| number  | color    |
| string  | text     |

#### 示例

```javascript
drawList.AddText(
    {x: 10, y: 10},
    0xffffffff,
    "Hello ImGui"
);
```

---

### AddBezierCubic

绘制三次贝塞尔曲线。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | p1        |
| Vector2 | p2        |
| Vector2 | p3        |
| Vector2 | p4        |
| number  | color     |
| number  | thickness |
| number  | segments  |

---

### AddBezierQuadratic

绘制二次贝塞尔曲线。

#### 参数

| 类型    | 名称      |
|---------|-----------|
| Vector2 | p1        |
| Vector2 | p2        |
| Vector2 | p3        |
| number  | color     |
| number  | thickness |
| number  | segments  |

---

### AddPolyline

绘制连续折线。

#### 参数

| 类型      | 名称      |
|-----------|-----------|
| Vector2[] | points    |
| number    | color     |
| number    | thickness |
| number    | flags     |

#### 示例

```javascript
drawList.AddPolyline([
    {x: 0, y: 0},
    {x: 50, y: 50},
    {x: 100, y: 0}
], 0xffffffff, 2);
```

---

### AddConvexPolyFilled

绘制凸多边形填充。

#### 参数

| 类型      | 名称   |
|-----------|--------|
| Vector2[] | points |
| number    | color  |

---

### AddConcavePolyFilled

绘制凹多边形填充。

#### 参数

| 类型      | 名称   |
|-----------|--------|
| Vector2[] | points |
| number    | color  |

---

#### Vector2 格式

所有坐标参数均使用以下格式：

```
{
    x: number,
    y: number
}
```

例如：

```
{
    x:100,
    y:200
}
```

#### Color 格式

颜色使用 ImGui `ImU32` 格式：

```
0xAABBGGRR
```

示例：

```
0xffffffff // 白色
0xff0000ff // 红色
0xff00ff00 // 绿色
0xffff0000 // 蓝色
```

#### 注意事项

- 所有绘制操作会直接写入当前 ImGui DrawList。
- 坐标使用屏幕空间坐标。
- 颜色使用 32 位整数。
- thickness 参数单位为像素。
- segments 参数为 0 时由 ImGui 自动计算。
- 多边形至少需要两个有效点。

---

## ShowDemoWindow

显示 Dear ImGui 官方 Demo 窗口。

#### 参数

| 类型      | 名称   | 说明           |
| ------- | ---- | ------------ |
| boolean | open | 可选。控制窗口是否打开。 |

也可以传入通过 ImGui API 创建的布尔引用对象。

#### 返回值

无。

#### 示例

```javascript
const open = new ImGui.Value(true);

ImGui.ShowDemoWindow(open);
```

#### 注意事项

* 不传入参数时，窗口状态由 ImGui 内部管理。
* 传入参数时，可以通过修改布尔值控制窗口显示状态。

---

## ShowMetricsWindow

显示 ImGui Metrics 调试窗口。

该窗口用于查看 ImGui 内部状态，例如：

* Window 信息
* DrawList 信息
* ID Stack
* 内存使用情况

#### 参数

| 类型      | 名称   | 说明           |
| ------- | ---- | ------------ |
| boolean | open | 可选。控制窗口是否打开。 |

#### 返回值

无。

#### 示例

```javascript
ImGui.ShowMetricsWindow();
```

---

## ShowStackToolWindow

显示 ImGui ID Stack 调试窗口。

用于调试 ImGui 内部 ID 栈状态。

#### 参数

| 类型      | 名称   | 说明           |
| ------- | ---- | ------------ |
| boolean | open | 可选。控制窗口是否打开。 |

#### 返回值

无。

#### 示例

```javascript
ImGui.ShowStackToolWindow();
```

---

## ShowAboutWindow

显示 ImGui 关于窗口。

#### 参数

| 类型      | 名称   | 说明           |
| ------- | ---- | ------------ |
| boolean | open | 可选。控制窗口是否打开。 |

#### 返回值

无。

#### 示例

```javascript
ImGui.ShowAboutWindow();
```

---

## ShowStyleEditor

显示 ImGui 样式编辑器。

可以用于实时调整 ImGui 样式。

#### 参数

| 类型         | 名称    | 说明             |
| ---------- | ----- | -------------- |
| ImGuiStyle | style | 可选。指定要编辑的样式对象。 |

#### 返回值

无。

#### 示例

```javascript
ImGui.ShowStyleEditor();
```

---

## ShowStyleSelector

显示样式选择器。

#### 参数

| 类型     | 名称    | 说明     |
| ------ | ----- | ------ |
| string | label | 选择器名称。 |

#### 返回值

无。

#### 异常

当参数为空或类型错误时抛出异常：

```
Invalid arguments
```

#### 示例

```javascript
ImGui.ShowStyleSelector("Style");
```

---

## ShowFontSelector

显示字体选择器。

#### 参数

| 类型     | 名称    | 说明     |
| ------ | ----- | ------ |
| string | label | 选择器名称。 |

#### 返回值

无。

#### 异常

当参数为空或类型错误时抛出异常：

```
Invalid arguments
```

#### 示例

```javascript
ImGui.ShowFontSelector("Font");
```

---

## ShowUserGuide

显示 ImGui 用户指南窗口。

#### 参数

无。

#### 返回值

无。

#### 示例

```javascript
ImGui.ShowUserGuide();
```

---

## GetVersion

获取当前 ImGui 版本。

#### 参数

无。

#### 返回值

| 类型     | 说明         |
| ------ | ---------- |
| string | ImGui 版本号。 |

#### 示例

```javascript
const version = ImGui.GetVersion();

console.log(version);
```

输出：

```
1.90.0
```
