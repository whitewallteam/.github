## Pos

| 名称 | 类型     | 描述  |
|:---|:-------|:----|
| x  | number | x坐标 |
| y  | number | y坐标 |
| z  | number | z坐标 |

## Rot

| 名称    | 类型     | 描述  |
|:------|:-------|:----|
| pitch | number | 俯仰角 |
| yaw   | number | 偏航角 |

## Velocity

| 名称 | 类型     | 描述  |
|:---|:-------|:----|
| x  | number | x速度 |
| y  | number | y速度 |
| z  | number | z速度 |

## Collision

| 名称 | 类型     | 描述  |
|:---|:-------|:----|
| x  | number | 实体宽 |
| y  | number | 实体高 |

## Block

| 名称              | 类型      | 描述     |
|:----------------|:--------|:-------|
| descriptionId   | string  | 翻译ID   |
| descriptionName | string  | 当前翻译名称 |
| namespace       | string  | 命名空间   |
| id              | number  | 唯一值    |
| aux             | number  | 特殊值    |
| solid           | boolean | 是否为固体  |
| runtimeId       | number  | 运行时ID  |

## File

| 名称          | 类型      | 描述    |
|:------------|:--------|:------|
| name        | string  | 名称    |
| path        | string  | 路径    |
| isFile      | boolean | 是否为文件 |
| isDirectory | boolean | 是否为目录 |
| length      | number  | 文件大小  |

## Player

| 名称                     | 类型      | 描述                                                       |
|:-----------------------|:--------|:---------------------------------------------------------|
| id                     | string  | 唯一标识                                                     |
| name                   | string  | 游戏名称                                                     |
| host                   | boolean | 是否为房主(不准确)                                               |
| permissionLevel        | number  | 权限级别(默认 = 0, 特权成员 = 1, 管理员 = 2, 房主 = 3, 成员 = 4, 自定义 = 5) |
| commandPermissionLevel | number  | 命令权限(默认 = 0, 特权成员 = 1, 管理员 = 2, 房主 = 3, 成员 = 4, 自定义 = 5) |

## Attribute

| 名称      | 类型     | 描述  |
|:--------|:-------|:----|
| max     | number | 最大值 |
| min     | number | 最小值 |
| current | number | 当前值 |

## CommandData

| 名称                 | 类型      | 描述                                                   |
|:-------------------|:--------|:-----------------------------------------------------|
| mode               | string  | 方块类型(仅命令方块设置此参数) Tick(脉冲型) Chain(连锁型) Repeating(循环型) |
| isRedStoneMode     | boolean | 是否需要被红石激活(仅命令方块设置此参数)                                |
| isConditional      | boolean | 是否需要条件(仅命令方块设置此参数)                                   |
| command            | string  | 命令内容                                                 |
| lastOutput         | string  | 命令输出文本                                               |
| name               | string  | 命令方块/矿车名称                                            |
| tickDelay          | number  | 执行每次命令的间隔时间（刻）                                       |
| shouldTrackOutput  | boolean | 是否需要输出                                               |
| executeOnFirstTick | boolean | 在保存或激活后在首个刻执行命令时为true                                |

## WorldStruct

| 名称    | 类型      | 描述     |
|:------|:--------|:-------|
| state | boolean | 是否成功找到 |
| x     | number  | x坐标    |
| y     | number  | y坐标    |
| z     | number  | z坐标    |

## Input

| 名称 | 类型     | 描述    |
|:---|:-------|:------|
| x  | number | 左右方向值 |
| y  | number | 上下方向值 |

## PlayerAuthInput

| 名称         | 类型       | 描述                      |
|:-----------|:---------|:------------------------|
| rot        | Rot      | 视角                      |
| pos        | Pos      | 坐标                      |
| delta      | Velocity | 移动值                     |
| analogMove | Input    | 移动输入值                   |
| moveVec    | Input    | 移动输入值                   |
| flags      | number   | 操作标志组(PlayerInputFlags) |

## PlayerInput

| 名称     | 类型      | 描述                |
|:-------|:--------|:------------------|
| rot    | Rot     | 视角                |
| pos    | Pos     | 坐标                |
| ground | boolean | 是否在地面             |
| action | number  | 输入类型(PlayerInput) |

## WorldData

| 名称              | 类型      | 描述       |
|:----------------|:--------|:---------|
| difficulty      | number  | 游戏难度     |
| flatWorldLayers | string  | 平坦世界层    |
| forceGameType   | boolean | 是否强制游戏模式 |
| gameType        | number  | 游戏模式     |
| levelName       | string  | 世界名称     |
| randomSeed      | number  | 随机种子     |
| time            | number  | 游戏时间     |
| lightningLevel  | number  | 闪电等级     |
| lightningTime   | number  | 闪电时间     |
| rainLevel       | number  | 雨量       |
| rainTime        | number  | 雨时间      |
| randomTickSpeed | number  | 随机刻速度    |

## EntityEffect

| 名称                              | 类型      | 描述                 |
|---------------------------------|---------|--------------------|
| id                              | number  | 药水效果的唯一标识符         |
| duration                        | number  | 药水效果的持续时间（以游戏刻为单位） |
| durationEasy                    | number  | 药水效果在“简单”难度下的持续时间  |
| durationNormal                  | number  | 药水效果在“普通”难度下的持续时间  |
| durationHard                    | number  | 药水效果在“困难”难度下的持续时间  |
| amplifier                       | number  | 药水效果的强度等级          |
| displayOnScreenTextureAnimation | boolean | 是否在屏幕上显示动画效果       |
| ambient                         | boolean | 是否为环境效果            |
| noCounter                       | boolean | 是否不显示倒计时           |
| effectVisible                   | boolean | 药水效果是否对玩家可见        |

## SizeData

| 名称           | 类型     | 描述     |
|--------------|--------|--------|
| deviceWidth  | number | 设备屏幕宽度 |
| deviceHeight | number | 设备屏幕高度 |
| screenWidth  | number | 游戏屏幕宽度 |
| screenHeight | number | 游戏屏幕高度 |

### InputMode

| 名称                 | 值 | 描述        |
|:-------------------|:--|:----------|
| `Undefined`        | 0 | 未定义的输入模式  |
| `Mouse`            | 1 | 鼠标输入模式    |
| `Touch`            | 2 | 触控输入模式    |
| `GamePad`          | 3 | 游戏手柄输入模式  |
| `MotionController` | 4 | 运动控制器输入模式 |

### PlayMode

| 名称                    | 值 | 描述       |
|:----------------------|:--|:---------|
| `Normal`              | 0 | 正常模式     |
| `Teaser`              | 1 | 预告模式     |
| `Screen`              | 2 | 屏幕模式     |
| `Viewer`              | 3 | 观众模式     |
| `Reality`             | 4 | 现实模式     |
| `Placement`           | 5 | 放置模式     |
| `LivingRoom`          | 6 | 客厅模式     |
| `ExitLevel`           | 7 | 退出关卡模式   |
| `ExitLevelLivingRoom` | 8 | 退出客厅关卡模式 |


