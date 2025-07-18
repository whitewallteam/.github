
### getBooleanOption

**描述**: 获取指定 ID 的布尔选项值及其默认值，返回包含选项值和默认值的对象。

**参数**:
- `id` - `number` - 布尔选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `value` - `boolean` - 当前布尔选项的值。
- `defaultValue` - `boolean` - 该布尔选项的默认值。

**示例代码**:
```javascript
let option = getBooleanOption(1);
console.log(`Option Value: ${option.value}, Default Value: ${option.defaultValue}`);
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的布尔值和默认值。

---

### setBooleanOption

**描述**: 设置指定 ID 的布尔选项值，允许用户指定当前值和默认值。

**参数**:
- `id` - `number` - 布尔选项的唯一标识符。
- `{value, defaultValue}` - `Object` - 一个对象，包含以下属性：
  - `value` - `boolean` - 要设置的当前布尔选项值。
  - `defaultValue` - `boolean` - 布尔选项的默认值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setBooleanOption(1, { value: true, defaultValue: false });
console.log("Boolean option has been set.");
```

**注意事项**: 确保提供有效的选项 ID 及合适的布尔值，以避免意外覆盖重要设置。

---

### setIntOption

**描述**: 设置指定 ID 的整数选项值，允许用户指定最小值、最大值、当前值和默认值。

**参数**:
- `id` - `number` - 整数选项的唯一标识符。
- `{minValue, maxValue, currentValue, defaultValue}` - `Object` - 一个对象，包含以下属性：
  - `minValue` - `number` - 整数选项的最小值。
  - `maxValue` - `number` - 整数选项的最大值。
  - `currentValue` - `number` - 当前的整数选项值。
  - `defaultValue` - `number` - 整数选项的默认值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setIntOption(1, { minValue: 0, maxValue: 100, currentValue: 50, defaultValue: 25 });
console.log("Integer option has been set.");
```

**注意事项**: 确保提供有效的选项 ID 以及合理的值，以避免超出范围或不符合预期的设置。

---

### getIntOption

**描述**: 获取指定 ID 的整数选项值及其属性，返回包含当前值、最小值、最大值和默认值的对象。

**参数**:
- `id` - `number` - 整数选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `currentValue` - `number` - 当前整数选项的值。
- `minValue` - `number` - 整数选项的最小值。
- `maxValue` - `number` - 整数选项的最大值。
- `defaultValue` - `number` - 整数选项的默认值。

**示例代码**:
```javascript
let intOption = getIntOption(1);
console.log(`Current Value: ${intOption.currentValue}, Min: ${intOption.minValue}, Max: ${intOption.maxValue}, Default: ${intOption.defaultValue}`);
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的整数值和属性。

---

### setFloatOption

**描述**: 设置指定 ID 的浮点选项值，允许用户指定最小值、最大值、当前值和默认值。

**参数**:
- `id` - `number` - 浮点选项的唯一标识符。
- `{minValue, maxValue, currentValue, defaultValue}` - `Object` - 一个对象，包含以下属性：
  - `minValue` - `number` - 浮点选项的最小值。
  - `maxValue` - `number` - 浮点选项的最大值。
  - `currentValue` - `number` - 当前的浮点选项值。
  - `defaultValue` - `number` - 浮点选项的默认值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setFloatOption(1, { minValue: 0.0, maxValue: 100.0, currentValue: 50.0, defaultValue: 25.0 });
console.log("Float option has been set.");
```

**注意事项**: 确保提供有效的选项 ID 以及合理的值，以避免超出范围或不符合预期的设置。

---

### getFloatOption

**描述**: 获取指定 ID 的浮点选项值及其属性，返回包含当前值、最小值、最大值和默认值的对象。

**参数**:
- `id` - `number` - 浮点选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `currentValue` - `number` - 当前浮点选项的值。
- `minValue` - `number` - 浮点选项的最小值。
- `maxValue` - `number` - 浮点选项的最大值。
- `defaultValue` - `number` - 浮点选项的默认值。

**示例代码**:
```javascript
let floatOption = getFloatOption(1);
console.log(`Current Value: ${floatOption.currentValue}, Min: ${floatOption.minValue}, Max: ${floatOption.maxValue}, Default: ${floatOption.defaultValue}`);
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的浮点值和属性。

---

### setStringOption

**描述**: 设置指定 ID 的字符串选项值，允许用户指定新的字符串值。

**参数**:
- `id` - `number` - 字符串选项的唯一标识符。
- `{string:value}` - `Object` - 一个对象，包含以下属性：
  - `value` - `string` - 要设置的新的字符串值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setStringOption(1, { string: "New Option Value" });
```

**注意事项**: 确保提供有效的选项 ID 以及合理的字符串值，以确保选项被正确更新。

---

### getStringOption

**描述**: 获取指定 ID 的字符串选项值，返回包含当前字符串值的对象。

**参数**:
- `id` - `number` - 字符串选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `value` - `string` - 当前字符串选项的值。

**示例代码**:
```javascript
let stringOption = getStringOption(1);
console.log(`Current Value: ${stringOption.value}`);
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的字符串值。

---

### getVec3Option

**描述**: 获取指定 ID 的三维向量选项值及其默认值，返回包含当前向量值和默认值的对象。

**返回值**: `Object` - 包含以下属性的对象：
- `value` - `Object` - 当前三维向量选项的值，包含：
  - `x` - `number` - 向量的 X 轴分量。
  - `y` - `number` - 向量的 Y 轴分量。
  - `z` - `number` - 向量的 Z 轴分量。
- `defaultValue` - `Object` - 默认三维向量选项的值，包含：
  - `x` - `number` - 默认向量的 X 轴分量。
  - `y` - `number` - 默认向量的 Y 轴分量。
  - `z` - `number` - 默认向量的 Z 轴分量。

**示例代码**:
```javascript
let vec3Option = getVec3Option();
console.log(`Current Value - X: ${vec3Option.value.x}, Y: ${vec3Option.value.y}, Z: ${vec3Option.value.z}`);
console.log(`Default Value - X: ${vec3Option.defaultValue.x}, Y: ${vec3Option.defaultValue.y}, Z: ${vec3Option.defaultValue.z}`);
```

**注意事项**: 确保调用此函数时能正确返回有效的三维向量值及其默认值。

---

### setVec3Option

**描述**: 设置指定 ID 的三维向量选项值，允许用户指定当前向量和默认向量。

**参数**:
- `id` - `number` - 三维向量选项的唯一标识符。
- `{value, defaultValue}` - `Object` - 一个对象，包含以下属性：
  - `value` - `Object` - 要设置的当前三维向量值，包含：
    - `x` - `number` - 向量的 X 轴分量。
    - `y` - `number` - 向量的 Y 轴分量。
    - `z` - `number` - 向量的 Z 轴分量。
  - `defaultValue` - `Object` - 三维向量的默认值，包含：
    - `x` - `number` - 默认向量的 X 轴分量。
    - `y` - `number` - 默认向量的 Y 轴分量。
    - `z` - `number` - 默认向量的 Z 轴分量。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setVec3Option(1, {
  value: { x: 1.0, y: 2.0, z: 3.0 },
  defaultValue: { x: 0.0, y: 0.0, z: 0.0 }
});
```

**注意事项**: 确保提供有效的选项 ID 以及合理的三维向量值，以确保选项被正确更新。

---

### setEnumOption

**描述**: 设置指定 ID 枚举选项的当前值和默认值，允许用户指定新的当前值和默认值。

**参数**:
- `id` - `number` - 枚举选项的唯一标识符。
- `{currentValue, defaultValue}` - `Object` - 一个对象，包含以下属性：
  - `currentValue` - `number` - 要设置的当前枚举选项值。
  - `defaultValue` - `number` - 枚举选项的默认值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setEnumOption(1,{ currentValue: 1, defaultValue: 0 });
```

**注意事项**: 确保提供合理的值，以确保枚举选项被正确更新。枚举值通常是预定义的一组常量之一。

---

### getEnumOption

**描述**: 获取指定 ID 的枚举选项值及其属性，返回包含当前值、默认值以及可用值的对象。

**参数**:
- `id` - `number` - 枚举选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `values` - `Array` - 包含可用枚举值的数组，每个枚举值是一个对象，包含：
  - `name` - `string` - 枚举值的名称。
  - `value` - `number` - 枚举值的实际值。
- `currentValue` - `number` - 当前枚举选项的值。
- `defaultValue` - `number` - 枚举选项的默认值。

**示例代码**:
```javascript
let enumOption = getEnumOption(1);
console.log(`Current Value: ${enumOption.currentValue}`);
console.log(`Default Value: ${enumOption.defaultValue}`);
console.log("Available Values:");
enumOption.values.forEach(option => {
    console.log(`Name: ${option.name}, Value: ${option.value}`);
});
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的枚举值及其属性。

---

### getInputModeBoolOption

**描述**: 获取指定 ID 的输入模式布尔选项值及其属性，返回包含可用值和默认值的对象。

**参数**:
- `id` - `number` - 输入模式布尔选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `values` - `Array` - 包含可用输入模式的数组，每个输入模式是一个对象，包含：
  - `name` - `string` - 输入模式的名称。
  - `id` - `number` - 输入模式的唯一标识符。
  - `value` - `boolean` - 输入模式的布尔值。
- `defaultValues` - `Array` - 包含默认输入模式的数组，每个默认模式是一个对象，包含：
  - `name` - `string` - 默认输入模式的名称。
  - `id` - `number` - 默认输入模式的唯一标识符。
  - `value` - `boolean` - 默认输入模式的布尔值。

**示例代码**:
```javascript
let inputModeOption = getInputModeBoolOption(1);
console.log("Available Values:");
inputModeOption.values.forEach(option => {
    console.log(`Name: ${option.name}, ID: ${option.id}, Value: ${option.value}`);
});
console.log("Default Values:");
inputModeOption.defaultValues.forEach(defaultOption => {
    console.log(`Name: ${defaultOption.name}, ID: ${defaultOption.id}, Value: ${defaultOption.value}`);
});
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的输入模式及其属性。

---

### setInputModeBoolOption

**描述**: 设置指定 ID 的输入模式布尔选项值，允许用户指定可用值和默认值。

**参数**:
- `id` - `number` - 输入模式布尔选项的唯一标识符。
- `{values, defaultValues}` - `Object` - 一个对象，包含以下属性：
  - `values` - `Array` - 包含可用输入模式的数组，每个输入模式是一个对象，包含：
    - `id` - `number` - 输入模式的唯一标识符。
    - `value` - `boolean` - 输入模式的布尔值。
  - `defaultValues` - `Array` - 包含默认输入模式的数组，每个默认模式是一个对象，包含：
    - `id` - `number` - 默认输入模式的唯一标识符。
    - `value` - `boolean` - 默认输入模式的布尔值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setInputModeBoolOption(1, {
  values: [
    { id: 1, value: true },
    { id: 2, value: false }
  ],
  defaultValues: [
    { id: 1, value: true },
    { id: 2, value: false }
  ]
});
console.log("Input mode boolean option has been set.");
```

**注意事项**: 确保提供有效的选项 ID 及合理的值，以确保输入模式布尔选项被正确更新。

---

### setInputModeFloatOption

**描述**: 设置指定 ID 的输入模式浮点选项值，允许用户指定可用值、默认值以及值的范围（最小值和最大值）。

**参数**:
- `id` - `number` - 输入模式浮点选项的唯一标识符。
- `{values, defaultValues}` - `Object` - 一个对象，包含以下属性：
  - `values` - `Array` - 包含可用输入模式的数组，每个输入模式是一个对象，包含：
    - `id` - `number` - 输入模式的唯一标识符。
    - `value` - `number` - 输入模式的浮点值。
  - `defaultValues` - `Array` - 包含默认输入模式的数组，每个默认模式是一个对象，包含：
    - `id` - `number` - 默认输入模式的唯一标识符。
    - `value` - `number` - 默认输入模式的浮点值。
- `minValue` - `number` - 可接受的最小浮点值。
- `maxValue` - `number` - 可接受的最大浮点值。

**返回值**: `void` - 无返回值。

**示例代码**:
```javascript
setInputModeFloatOption(1, {
  values: [
    { id: 1, value: 0.5 },
    { id: 2, value: 1.0 }
  ],
  defaultValues: [
    { id: 1, value: 0.5 },
    { id: 2, value: 0.75 }
  ], minValue: 0.0, maxValue: 2.0});
```

**注意事项**: 确保提供有效的选项 ID、合理的浮点值以及合适的最小和最大值，以确保输入模式浮点选项被正确更新。

---

### getInputModeFloatOption

**描述**: 获取指定 ID 的输入模式浮点选项值及其属性，返回包含可用值、默认值以及最小值和最大值的对象。

**参数**:
- `id` - `number` - 输入模式浮点选项的唯一标识符。

**返回值**: `Object` - 包含以下属性的对象：
- `values` - `Array` - 包含可用输入模式的数组，每个输入模式是一个对象，包含：
  - `id` - `number` - 输入模式的唯一标识符。
  - `value` - `number` - 输入模式的浮点值。
- `defaultValues` - `Array` - 包含默认输入模式的数组，每个默认模式是一个对象，包含：
  - `id` - `number` - 默认输入模式的唯一标识符。
  - `value` - `number` - 默认输入模式的浮点值。
- `minValue` - `number` - 可接受的最小浮点值。
- `maxValue` - `number` - 可接受的最大浮点值。

**示例代码**:
```javascript
let floatOption = getInputModeFloatOption(1);
console.log("Available Values:");
floatOption.values.forEach(option => {
    console.log(`ID: ${option.id}, Value: ${option.value}`);
});
console.log("Default Values:");
floatOption.defaultValues.forEach(defaultOption => {
    console.log(`ID: ${defaultOption.id}, Value: ${defaultOption.value}`);
});
console.log(`Min Value: ${floatOption.minValue}, Max Value: ${floatOption.maxValue}`);
```

**注意事项**: 确保提供有效的选项 ID，以便正确获取相应的输入模式及其属性。

---

### loadNbtFromFile

**描述**: 从指定路径加载 NBT 二进制数据并返回为字符串。

**参数**:
- `path` - `string` - 文件的路径，包含 NBT 数据的文件位置。

**返回值**: `string` - 成功加载时返回包含 NBT 数据的字符串；如果加载失败，返回空字符串 `""`。

**示例代码**:
```javascript
let nbtData = loadNbtFromFile("path/to/file.nbt");
if (nbtData) {
    console.log("NBT Data loaded successfully: " + nbtData);
} else {
    console.log("Failed to load NBT Data.");
}
```

**注意事项**:
- 确保 `path` 指向一个有效的 NBT 文件。
- 如果文件路径无效或文件内容无法解析为 NBT 格式，方法将返回空字符串。
- 调用此方法前，请确保文件权限允许读取操作。

---

### saveNbtToFile

**描述**: 将指定的 NBT 数据以二进制方式保存到文件中。

**参数**:
- `path` - `string` - 文件的路径，指定保存 NBT 数据的文件位置。
- `nbt` - `string` - 要保存的 NBT 数据字符串。

**返回值**: `boolean` - 保存成功返回 `true`，否则返回 `false`。

**示例代码**:
```javascript
let nbtData = '{"id": "minecraft:chest", "Count": 1}';
let isSaved = saveNbtToFile("path/to/file.nbt", nbtData);
if (isSaved) {
    console.log("NBT Data saved successfully.");
} else {
    console.log("Failed to save NBT Data.");
}
```

**注意事项**:
- 确保 `path` 是有效的文件路径，并且程序有写入权限。
- `nbt` 应为有效的 NBT 格式字符串，否则保存可能会失败。
- 如果文件已存在，将覆盖文件内容；确保在保存前备份重要数据。

---

### isInGame

**描述**:  
判断当前玩家是否处于游戏状态。

**参数**:  
无

**返回值**:  
`boolean` - 如果玩家处于游戏中，返回 `true`；否则返回 `false`。

**示例代码**:  
```javascript
if (isInGame()) {
    console.log("Player is in the game.");
} else {
    console.log("Player is not in the game.");
}
```
**注意事项**:
- 无。

---

### getLanguageString

**描述**:  
获取指定语言字符串的翻译。

**参数**:  
- `key` - `string` - 语言字符串的键。

**返回值**:  
`string` - 语言字符串的翻译。

**示例代码**:  
```javascript
let translatedString = getLanguageString("key");
console.log(translatedString);
```
**注意事项**:
- 无。

---

### setLanguageString

**描述**:  
设置指定语言字符串的翻译。

**参数**:  
- `key` - `string` - 语言字符串的键。
- `value` - `string` - 语言字符串的翻译。

**返回值**: 无返回值。

**示例代码**:  
```javascript
setLanguageString("key", "翻译");
```
**注意事项**:
- 无。