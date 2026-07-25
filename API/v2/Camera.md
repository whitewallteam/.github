`camera` 模块提供 Minecraft 摄像机控制 API，可用于修改摄像机位置、旋转、偏移、锚点以及摄像机模式等。

通过 `require` 获取：

```javascript
const camera = require("camera");
````

---

### setRotation

设置摄像机旋转角度。

#### 语法

```javascript
camera.setRotation(rotation);
```

#### 参数

| 参数     | 类型   | 必填 | 说明       |
|----------|--------|------|------------|
| rotation | object | 是   | 摄像机旋转 |

#### rotation 格式

```text
{
    x: number,
    y: number,
    z: number
}
```

其中：

| 属性 | 说明              |
|------|-------------------|
| x    | Pitch（俯仰角）   |
| y    | Yaw（水平旋转角） |
| z    | Roll（翻滚角）    |

#### 示例

```javascript
const camera = require("camera");

camera.setRotation({
    x: 30,
    y: 180,
    z: 0
});
```

---

### getRotation

获取当前摄像机旋转角度。

#### 语法

```javascript
camera.getRotation();
```

#### 返回值

```text
{
    pitch: number,
    yaw: number,
    roll: number
}
```

| 属性  | 类型   | 说明       |
|-------|--------|------------|
| pitch | number | 俯仰角     |
| yaw   | number | 水平旋转角 |
| roll  | number | 翻滚角     |

#### 示例

```javascript
const rot = camera.getRotation();

console.log(rot.pitch);
```

---

### setPos

设置编辑摄像机位置。

#### 语法

```javascript
camera.setPos(position);
```

#### 参数

| 参数     | 类型   | 必填 | 说明       |
|----------|--------|------|------------|
| position | object | 是   | 摄像机位置 |

#### position 格式

```text
{
    x: number,
    y: number,
    z: number
}
```

#### 示例

```javascript
camera.setPos({
    x: 10,
    y: 80,
    z: 10
});
```

---

### getPos

获取编辑摄像机位置。

#### 语法

```javascript
camera.getPos();
```

#### 返回值

```text
{
    x: number,
    y: number,
    z: number
}
```

---

### getWorldPos

获取摄像机世界坐标位置。

#### 语法

```javascript
camera.getWorldPos();
```

#### 返回值

```
{
    x: number,
    y: number,
    z: number
}
```

#### 说明

返回摄像机当前实际所在的 Minecraft 世界坐标。

---

### getWorldTargetPos

获取摄像机当前目标位置。

#### 语法

```javascript
camera.getWorldTargetPos();
```

#### 返回值

```
{
    x: number,
    y: number,
    z: number
}
```

---

### setOffset

设置摄像机偏移。

#### 语法

```javascript
camera.setOffset(offset);
```

#### 参数

| 参数   | 类型   | 必填 | 说明         |
|--------|--------|------|--------------|
| offset | object | 是   | 摄像机偏移量 |

#### offset 格式

```
{
    x: number,
    y: number,
    z: number
}
```

#### 示例

```javascript
camera.setOffset({
    x: 0,
    y: 2,
    z: 0
});
```

---

### getOffset

获取摄像机偏移。

#### 语法

```javascript
camera.getOffset();
```

#### 返回值

```
{
    x: number,
    y: number,
    z: number
}
```

---

### getAnchor

获取摄像机锚点位置。

#### 语法

```javascript
camera.getAnchor();
```

#### 返回值

```
{
    x: number,
    y: number,
    z: number
}
```

---

### setAnchor

设置摄像机锚点位置。

#### 语法

```javascript
camera.setAnchor(position);
```

#### 参数

| 参数     | 类型   | 必填 | 说明     |
|----------|--------|------|----------|
| position | object | 是   | 锚点坐标 |

#### 示例

```javascript
camera.setAnchor({
    x: 0,
    y: 64,
    z: 0
});
```

---

### setPitchLimit

设置摄像机俯仰角限制。

#### 语法

```javascript
camera.setPitchLimit(limit);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| limit | object | 是   | 角度限制 |

#### limit 格式

```
{
    x: number,
    y: number
}
```

#### 说明

* `x` 为最小俯仰角。
* `y` 为最大俯仰角。

#### 示例

```javascript
camera.setPitchLimit({
    x: -45,
    y: 45
});
```

---

### getPitchLimit

获取摄像机俯仰角限制。

#### 语法

```javascript
camera.getPitchLimit();
```

#### 返回值

```
{
    x: number,
    y: number
}
```

---

### resetCamera

恢复默认摄像机模式。

#### 语法

```javascript
camera.resetCamera();
```

#### 返回值

无。

#### 说明

将摄像机模式恢复为普通模式。

---

### lockCamera

锁定摄像机。

#### 语法

```javascript
camera.lockCamera();
```

#### 返回值

无。

#### 说明

设置摄像机模式为锁定模式。

---

### departCamera

启用第三人称离体摄像机。

#### 语法

```javascript
camera.departCamera();
```

#### 返回值

无。

#### 说明

设置摄像机模式为 DEPART 模式，使摄像机脱离玩家位置。

---

#### 示例

```javascript
const camera = require("camera");

// 设置摄像机位置
camera.setPos({
    x: 100,
    y: 80,
    z: 100
});

// 设置视角
camera.setRotation({
    x: 20,
    y: 90,
    z: 0
});

// 锁定摄像机
camera.lockCamera();
```

---

#### 注意事项

* 摄像机 API 需要在游戏运行状态下调用。
* 部分摄像机功能依赖当前游戏客户端状态。
* 设置摄像机模式后，可以使用 `resetCamera()` 恢复默认状态。
