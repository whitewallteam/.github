## BlockEntity.getPosition

获取方块实体位置。

### 语法

```javascript
blockEntity.getPosition();
```

### 返回值

```text
{
    x: number,
    y: number,
    z: number
}
```

### 示例

```javascript
const pos = entity.getPosition();

console.log(pos.x);
```

---

## BlockEntity.getType

获取方块实体类型。

### 语法

```javascript
blockEntity.getType();
```

### 返回值

| 类型   | 说明    |
|--------|---------|
| string | 类型 ID |

---

## BlockEntity.getRendererId

获取渲染器 ID。

### 语法

```javascript
blockEntity.getRendererId();
```

### 返回值

| 类型   | 说明      |
|--------|-----------|
| string | 渲染器 ID |

---

## BlockEntity.getName

获取方块实体名称。

### 语法

```javascript
blockEntity.getName();
```

### 返回值

| 类型   | 说明     |
|--------|----------|
| string | 默认名称 |

---

## BlockEntity.getCustomName

获取自定义名称。

### 语法

```javascript
blockEntity.getCustomName();
```

### 返回值

| 类型   | 说明       |
|--------|------------|
| string | 自定义名称 |

---

## BlockEntity.getNBT

获取方块实体 NBT 数据。

### 语法

```javascript
blockEntity.getNBT();
```

### 返回值

| 类型   | 说明               |
|--------|--------------------|
| string | Mojangson 格式 NBT |

---
