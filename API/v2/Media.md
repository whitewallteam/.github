`media` 模块提供音频播放相关 API，基于 FMOD 实现音频资源创建、播放、音量控制、3D 音效设置以及播放状态管理等功能。

通过 `require` 获取：

```javascript
const media = require("media");
````

---

## System

`System` 用于管理音频系统，可以创建音频资源并播放声音。

#### 创建实例

```javascript
const system = new media.System();
```

---

### createSound

创建一个音频资源。

#### 语法

```javascript
system.createSound(source, mode);
```

#### 参数

| 参数   | 类型   | 必填        | 说明            |
|--------|--------|-------------|-----------------|
| source | string | ArrayBuffer | ArrayBufferView | 是  | 音频路径或音频数据 |
| mode   | number | 否          | FMOD 音频模式   |

#### 返回值

返回 `Sound` 对象。

#### 示例

```javascript
const sound = system.createSound("music.mp3");
```

---

### createStream

创建一个流式音频资源。

#### 语法

```javascript
system.createStream(source, mode);
```

#### 参数

| 参数   | 类型   | 必填        | 说明            |
|--------|--------|-------------|-----------------|
| source | string | ArrayBuffer | ArrayBufferView | 是  | 音频路径或音频数据 |
| mode   | number | 否          | FMOD 音频模式   |

#### 返回值

返回 `Sound` 对象。

#### 示例

```javascript
const stream = system.createStream("music.mp3");
```

---

### playSound

播放音频。

#### 语法

```javascript
system.playSound(sound, paused);
```

#### 参数

| 参数   | 类型    | 必填 | 说明             |
|--------|---------|------|------------------|
| sound  | Sound   | 是   | 要播放的音频对象 |
| paused | boolean | 否   | 是否暂停播放     |

#### 返回值

返回 `Channel` 对象。

#### 示例

```javascript
const channel = system.playSound(sound);
```

暂停播放：

```javascript
const channel = system.playSound(sound, true);
```

---

## Sound

`Sound` 表示一个音频资源对象。

---

### setDefaults

设置默认频率和优先级。

#### 语法

```javascript
sound.setDefaults(frequency, priority);
```

#### 参数

| 参数      | 类型   | 必填 | 说明         |
|-----------|--------|------|--------------|
| frequency | number | 是   | 默认播放频率 |
| priority  | number | 是   | 优先级       |

#### 返回值

无。

---

### getDefaults

获取默认设置。

#### 语法

```javascript
sound.getDefaults();
```

#### 返回值

返回对象：

```
{
    frequency: number,
    priority: number
}
```

---

### set3DMinMaxDistance

设置 3D 音频距离范围。

#### 语法

```javascript
sound.set3DMinMaxDistance(min, max);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| min  | number | 是   | 最小距离 |
| max  | number | 是   | 最大距离 |

---

### get3DMinMaxDistance

获取 3D 音频距离范围。

#### 返回值

```
{
    min: number,
    max: number
}
```

---

### set3DConeSettings

设置 3D 音锥参数。

#### 语法

```javascript
sound.set3DConeSettings(
    insideConeAngle,
    outsideConeAngle,
    outsideVolume
);
```

#### 参数

| 参数             | 类型   | 必填 | 说明     |
|------------------|--------|------|----------|
| insideConeAngle  | number | 是   | 内锥角度 |
| outsideConeAngle | number | 是   | 外锥角度 |
| outsideVolume    | number | 是   | 外锥音量 |

---

### get3DConeSettings

获取 3D 音锥参数。

#### 返回值

```
{
    insideConeAngle: number,
    outsideConeAngle: number,
    outsideVolume: number
}
```

---

### getName

获取音频名称。

#### 语法

```javascript
sound.getName();
```

#### 返回值

`string`

---

### getLength

获取音频长度。

#### 语法

```javascript
sound.getLength(type);
```

#### 参数

| 参数 | 类型   | 必填 | 说明     |
|------|--------|------|----------|
| type | number | 否   | 时间单位 |

#### 返回值

`number`

---

### getFormat

获取音频格式信息。

#### 语法

```javascript
sound.getFormat();
```

#### 返回值

```
{
    type: number,
    format: number,
    channels: number,
    bits: number
}
```

---

### getNumSubSounds

获取子声音数量。

#### 返回值

`number`

---

### getNumTags

获取标签数量。

#### 返回值

```
{
    numTags: number,
    numTagsUpdated: number
}
```

---

### getTag

获取音频标签。

#### 语法

```javascript
sound.getTag(name, index);
```

#### 参数

| 参数  | 类型   | 必填 | 说明     |
|-------|--------|------|----------|
| name  | string | 是   | 标签名称 |
| index | number | 是   | 标签索引 |

#### 返回值

```
{
    type: number,
    datatype: number,
    name: string,
    data: External,
    datalen: number,
    updated: boolean
}
```

---

### getOpenState

获取音频加载状态。

#### 返回值

```
{
    openState: number,
    percentBuffered: number,
    starving: boolean,
    diskBusy: boolean
}
```

---

### setMode

设置播放模式。

#### 语法

```javascript
sound.setMode(mode);
```

#### 参数

| 参数 | 类型   | 必填 |
|------|--------|------|
| mode | number | 是   |

---

### getMode

获取播放模式。

#### 返回值

`number`

---

### setLoopCount

设置循环次数。

#### 语法

```javascript
sound.setLoopCount(count);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| count | number | 是   |

---

### getLoopCount

获取循环次数。

#### 返回值

`number`

---

## ChannelGroup

`ChannelGroup` 表示音频通道组。

---

### getName

获取通道组名称。

#### 返回值

`string`

---

### getNumChannels

获取通道数量。

#### 返回值

`number`

---

### getChannel

获取指定通道。

#### 语法

```javascript
group.getChannel(index);
```

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| index | number | 是   |

#### 返回值

`Channel`

---

## Channel

`Channel` 表示正在播放的音频通道。

---

### stop

停止播放。

#### 语法

```javascript
channel.stop();
```

---

### setPaused

设置暂停状态。

#### 语法

```javascript
channel.setPaused(paused);
```

#### 参数

| 参数   | 类型    | 必填 |
|--------|---------|------|
| paused | boolean | 是   |

---

### getPaused

获取暂停状态。

#### 返回值

`boolean`

---

### setVolume

设置音量。

#### 语法

```javascript
channel.setVolume(volume);
```

#### 参数

| 参数   | 类型   | 必填 |
|--------|--------|------|
| volume | number | 是   |

---

### getVolume

获取音量。

#### 返回值

`number`

---

### setVolumeRamp

设置音量渐变。

#### 语法

```javascript
channel.setVolumeRamp(enable);
```

#### 参数

| 参数   | 类型    | 必填 |
|--------|---------|------|
| enable | boolean | 是   |

---

### getVolumeRamp

获取音量渐变状态。

#### 返回值

`boolean`

---

### getAudibility

获取当前可听度。

#### 返回值

`number`

---

### setPitch

设置音调。

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| pitch | number | 是   |

---

### getPitch

获取音调。

#### 返回值

`number`

---

### setMute

设置静音。

#### 参数

| 参数 | 类型    | 必填 |
|------|---------|------|
| mute | boolean | 是   |

---

### getMute

获取静音状态。

#### 返回值

`boolean`

---

### setReverbProperties

设置混响参数。

#### 语法

```javascript
channel.setReverbProperties(instance, wet);
```

#### 参数

| 参数     | 类型   | 必填 |
|----------|--------|------|
| instance | number | 是   |
| wet      | number | 是   |

---

### getReverbProperties

获取混响参数。

#### 返回值

`number`

---

### setLowPassGain

设置低通滤波增益。

#### 参数

| 参数 | 类型   | 必填 |
|------|--------|------|
| gain | number | 是   |

---

### getLowPassGain

获取低通滤波增益。

#### 返回值

`number`

---

### setCallback

设置播放回调。

#### 语法

```javascript
channel.setCallback(callback);
```

#### 参数

| 参数     | 类型     | 必填 |
|----------|----------|------|
| callback | function | 是   |

回调参数：

```javascript
(controlType, callbackType)
```

| 参数         | 类型   | 说明     |
|--------------|--------|----------|
| controlType  | number | 控制类型 |
| callbackType | number | 回调类型 |

---

### isPlaying

判断是否正在播放。

#### 返回值

`boolean`

---

### setFrequency

设置播放频率。

#### 参数

| 参数      | 类型   | 必填 |
|-----------|--------|------|
| frequency | number | 是   |

---

### getFrequency

获取播放频率。

#### 返回值

`number`

---

### setPriority

设置优先级。

#### 参数

| 参数     | 类型   | 必填 |
|----------|--------|------|
| priority | number | 是   |

---

### getPriority

获取优先级。

#### 返回值

`number`

---

### setPosition

设置播放位置。

#### 语法

```javascript
channel.setPosition(position, unit);
```

#### 参数

| 参数     | 类型   | 必填 |
|----------|--------|------|
| position | number | 是   |
| unit     | number | 否   |

---

### getPosition

获取播放位置。

#### 返回值

`number`

---

### setChannelGroup

设置所属通道组。

#### 语法

```javascript
channel.setChannelGroup(group);
```

#### 参数

| 参数  | 类型         | 必填 |
|-------|--------------|------|
| group | ChannelGroup | 是   |

---

### getChannelGroup

获取所属通道组。

#### 返回值

`ChannelGroup`

---

### setLoopCount

设置循环次数。

#### 参数

| 参数  | 类型   | 必填 |
|-------|--------|------|
| count | number | 是   |

---

### getLoopCount

获取循环次数。

#### 返回值

`number`

---

### setLoopPoints

设置循环区间。

#### 语法

```javascript
channel.setLoopPoints(start, startType, end, endType);
```

#### 参数

| 参数      | 类型   | 必填 |
|-----------|--------|------|
| start     | number | 是   |
| startType | number | 是   |
| end       | number | 是   |
| endType   | number | 是   |

---

### getLoopPoints

获取循环区间。

#### 返回值

```
{
    start: number,
    end: number
}
```
