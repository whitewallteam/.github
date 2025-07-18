## EntityFlag

| 名称                        | 数据值 | 描述                         |
|---------------------------|-----|----------------------------|
| OnFire                    | 0   | 实体是否着火，实体在燃烧并受到火焰伤害        |
| Sneaking                  | 1   | 实体是否处于潜行状态，移动速度减慢并不会触发压力板等 |
| Riding                    | 2   | 实体是否骑乘在另一实体上               |
| Sprinting                 | 3   | 实体是否在奔跑                    |
| UsingItem                 | 4   | 实体是否正在使用物品                 |
| Invisible                 | 5   | 实体是否处于隐身状态                 |
| Tempted                   | 6   | 实体是否被诱惑，通常是指被食物吸引          |
| InLove                    | 7   | 实体是否处于爱情模式，通常用于动物繁殖        |
| Saddled                   | 8   | 实体是否装备了鞍                   |
| Powered                   | 9   | 实体是否被充能                    |
| Ignited                   | 10  | 实体是否被点燃                    |
| Baby                      | 11  | 实体是否为婴儿状态                  |
| Converting                | 12  | 实体是否在转化过程中                 |
| Critical                  | 13  | 实体是否处于暴击状态                 |
| CanShowName               | 14  | 实体是否可以显示名称                 |
| AlwaysShowName            | 15  | 实体是否始终显示名称                 |
| NoAI                      | 16  | 实体是否没有AI                   |
| Silent                    | 17  | 实体是否无声                     |
| WallClimbing              | 18  | 实体是否能爬墙                    |
| CanClimb                  | 19  | 实体是否能攀爬                    |
| CanSwim                   | 20  | 实体是否能游泳                    |
| CanFly                    | 21  | 实体是否能飞行                    |
| CanWalk                   | 22  | 实体是否能行走                    |
| Resting                   | 23  | 实体是否处于休息状态                 |
| Sitting                   | 24  | 实体是否处于坐姿状态                 |
| Angry                     | 25  | 实体是否处于愤怒状态                 |
| Interested                | 26  | 实体是否感兴趣，通常用于互动行为           |
| Charged                   | 27  | 实体是否带电                     |
| Tamed                     | 28  | 实体是否被驯服                    |
| Orphaned                  | 29  | 实体是否成为孤儿                   |
| Leashed                   | 30  | 实体是否被拴住                    |
| Sheared                   | 31  | 实体是否被剪毛                    |
| Gliding                   | 32  | 实体是否在滑翔                    |
| Elder                     | 33  | 实体是否是长者                    |
| Moving                    | 34  | 实体是否在移动                    |
| Breathing                 | 35  | 实体是否在呼吸                    |
| Chested                   | 36  | 实体是否有箱子                    |
| Stackable                 | 37  | 实体是否可堆叠                    |
| ShowBottom                | 38  | 实体是否显示底部                   |
| Standing                  | 39  | 实体是否站立                     |
| Shaking                   | 40  | 实体是否震动                     |
| Idling                    | 41  | 实体是否闲置                     |
| Casting                   | 42  | 实体是否在施法                    |
| Charging                  | 43  | 实体是否在充电                    |
| WasdControlled            | 44  | 实体是否被WASD控制                |
| CanPowerJump              | 45  | 实体是否可以强力跳跃                 |
| Lingering                 | 46  | 实体是否徘徊                     |
| HasCollision              | 47  | 实体是否有碰撞                    |
| HasGravity                | 48  | 实体是否有重力                    |
| FireImmune                | 49  | 实体是否免疫火焰                   |
| Dancing                   | 50  | 实体是否在跳舞                    |
| Enchanted                 | 51  | 实体是否被附魔                    |
| ReturnTrident             | 52  | 实体是否会返回三叉戟                 |
| ContainerIsPrivate        | 53  | 容器是否为私密                    |
| IsTransforming            | 54  | 实体是否在变形                    |
| DamageNearbyMobs          | 55  | 是否伤害附近的生物                  |
| Swimming                  | 56  | 实体是否在游泳                    |
| Bribed                    | 57  | 实体是否被贿赂                    |
| IsPregnant                | 58  | 实体是否怀孕                     |
| LayingEgg                 | 59  | 实体是否在下蛋                    |
| RiderCanPick              | 60  | 骑乘者是否可以拾取                  |
| TransitionSitting         | 61  | 实体是否在过渡坐姿                  |
| Eating                    | 62  | 实体是否在吃东西                   |
| LayingDown                | 63  | 实体是否在躺下                    |
| Sneezing                  | 64  | 实体是否在打喷嚏                   |
| Trusting                  | 65  | 实体是否信任                     |
| Rolling                   | 66  | 实体是否在翻滚                    |
| Scared                    | 67  | 实体是否感到害怕                   |
| InScaffolding             | 68  | 实体是否在脚手架内                  |
| OverScaffolding           | 69  | 实体是否在脚手架上                  |
| FallThroughScaffolding    | 70  | 实体是否会掉落脚手架                 |
| Blocking                  | 71  | 实体是否在格挡                    |
| TransitionBlocking        | 72  | 实体是否在过渡格挡                  |
| BlockedUsingShield        | 73  | 实体是否用盾牌格挡                  |
| BlockedUsingDamagedShield | 74  | 实体是否用受损盾牌格挡                |
| Sleeping                  | 75  | 实体是否在睡觉                    |
| WantsToWake               | 76  | 实体是否想醒来                    |
| TradeInterest             | 77  | 实体是否对交易感兴趣                 |
| DoorBreaker               | 78  | 实体是否能破门                    |
| BreakingObstruction       | 79  | 实体是否能破坏障碍                  |
| DoorOpener                | 80  | 实体是否能开门                    |
| IsIllagerCaptain          | 81  | 实体是否是掠夺者队长                 |
| Stunned                   | 82  | 实体是否眩晕                     |
| Roaring                   | 83  | 实体是否在咆哮                    |
| DelayedAttack             | 84  | 实体是否延迟攻击                   |
| IsAvoidingMobs            | 85  | 实体是否避开生物                   |
| FacingTargetToRangeAttack | 86  | 实体是否面对远程攻击目标               |
| HiddenWhenInvisible       | 87  | 实体是否在隐身时隐藏                 |
| IsInUI                    | 88  | 实体是否在UI中                   |
| Stalking                  | 89  | 实体是否在潜行                    |
| Emoting                   | 90  | 实体是否在表达情感                  |
| Celebrating               | 91  | 实体是否在庆祝                    |
| Admiring                  | 92  | 实体是否在仰慕                    |
| CelebratingSpecial        | 93  | 实体是否在特殊庆祝                  |
| OutOfControl              | 94  | 实体是否失控                     |
| RamAttack                 | 95  | 实体是否在冲撞攻击                  |
| PlayingDead               | 96  | 实体是否在装死                    |
| InAscendableBlock         | 97  | 实体是否在可攀爬方块内                |
| OverDescendableBlock      | 98  | 实体是否在可下降方块上                |

## Attributes

| 名称                                    | 数据值 | 描述                                        |
|:--------------------------------------|:----|:------------------------------------------|
| minecraft:health                      | 1   | 生命值，原版的值范围为 [0, 20]                       |
| minecraft:follow_range                | 2   | 跟随方块数(一般指怪的仇恨范围)，原版值范围为 [1, 2024]，默认值为 16 |
| minecraft:knockback_resistance        | 3   | 击退抵抗，原版值范围为 [1, +∞]，默认最大值为 1              |
| minecraft:movement                    | 4   | 移速，原版的值范围为 [0, +∞]                        |
| minecraft:underwater_movement         | 5   | 水里的移速，原版的值范围为 [0, +∞]                     |
| minecraft:lava_movement               | 6   | 岩浆里的移速，原版的值范围为 [0, +∞]                    |
| minecraft:attack_damage               | 7   | 攻击力，原版的值范围为 [1, 1]                        |
| minecraft:absorption                  | 8   | 伤害吸收生命值，详见备注，原版的值范围为 [0, 16]              |
| minecraft:luck                        | 9   | 幸运值，原版的值范围为 [-1024, 1024]                 |
| minecraft:horse.jump_strength         | 10  | 跳跃力(指骑乘后跳跃可跳跃的高度)，原版值范围为 [0, +∞]          |
| minecraft:player.hunger               | 11  | 饥饿值，原版的值范围为 [0, 20]                       |
| minecraft:player.saturation           | 12  | 饱和值，原版的值范围为 [0, 20]                       |
| minecraft:player.exhaustion           | 13  | 玩家的疲劳度                                    |
| minecraft:player.level                | 14  | 玩家的经验等级                                   |
| minecraft:player.experience           | 15  | 玩家的经验值                                    |
| minecraft:zombie.spawn_reinforcements | 16  | 控制僵尸增援的能力                                 |

## PlayerInputFlags

| 名称                    | 数据值 | 描述              |
|:----------------------|:----|:----------------|
| ASCEND                | 0   | 表示玩家执行上升操作      | 
| DESCEND               | 1   | 表示玩家执行下降操作      | 
| NORTH_JUMP            | 2   | 玩家执行朝北方向的跳跃动作   | 
| JUMP_DOWN             | 3   | 玩家执行向下跳跃的动作     | 
| SPRINT_DOWN           | 4   | 玩家在冲刺状态下执行下降操作  | 
| CHANGE_HEIGHT         | 5   | 玩家在空中改变高度的动作    | 
| JUMPING               | 6   | 玩家正在执行跳跃动作      | 
| AUTO_JUMPING_IN_WATER | 7   | 玩家在水中自动跳跃       | 
| SNEAKING              | 8   | 玩家处于潜行状态        | 
| SNEAK_DOWN            | 9   | 玩家在潜行状态下执行下降操作  | 
| UP                    | 10  | 玩家朝上移动          | 
| DOWN                  | 11  | 玩家朝下移动          | 
| LEFT                  | 12  | 玩家朝左移动          | 
| RIGHT                 | 13  | 玩家朝右移动          | 
| UP_LEFT               | 14  | 玩家朝左上方向移动       | 
| UP_RIGHT              | 15  | 玩家朝右上方向移动       | 
| WANT_UP               | 16  | 玩家期望向上移动        | 
| WANT_DOWN             | 17  | 玩家期望向下移动        | 
| WANT_DOWN_SLOW        | 18  | 玩家期望以较慢的速度向下移动  | 
| WANT_UP_SLOW          | 19  | 玩家期望以较慢的速度向上移动  | 
| SPRINTING             | 20  | 玩家正在冲刺          | 
| ASCEND_BLOCK          | 21  | 玩家执行上升到方块的动作    | 
| DESCEND_BLOCK         | 22  | 玩家执行下降到方块的动作    | 
| SNEAK_TOGGLE_DOWN     | 23  | 玩家在潜行状态下切换至下降状态 | 
| PERSIST_SNEAK         | 24  | 玩家持续潜行状态        | 
| START_SPRINTING       | 25  | 玩家开始冲刺          | 
| STOP_SPRINTING        | 26  | 玩家停止冲刺          | 
| START_SNEAKING        | 27  | 玩家开始潜行          | 
| STOP_SNEAKING         | 28  | 玩家停止潜行          | 
| START_SWIMMING        | 29  | 玩家开始游泳          | 
| STOP_SWIMMING         | 30  | 玩家停止游泳          | 
| START_JUMPING         | 31  | 玩家开始执行跳跃        | 
| START_GLIDING         | 32  | 玩家开始执行滑翔动作      | 
| STOP_GLIDING          | 33  | 玩家停止滑翔          |

## PlayerInput

| 名称                       | 数据值 | 描述         |
|:-------------------------|:----|:-----------|
| START_BREAK              | 0   | 开始破坏方块     |
| ABORT_BREAK              | 1   | 中止破坏方块     |
| STOP_BREAK               | 2   | 停止破坏方块     |
| GET_UPDATED_BLOCK        | 3   | 获取更新后的方块信息 |
| DROP_ITEM                | 4   | 丢弃物品       |
| START_SLEEPING           | 5   | 开始睡觉       |
| STOP_SLEEPING            | 6   | 停止睡觉       |
| RESPAWN                  | 7   | 重新生成       |
| JUMP                     | 8   | 跳跃         |
| START_SPRINT             | 9   | 开始冲刺       |
| STOP_SPRINT              | 10  | 停止冲刺       |
| START_SNEAK              | 11  | 开始潜行       |
| STOP_SNEAK               | 12  | 停止潜行       |
| DIMENSION_CHANGE_REQUEST | 13  | 请求维度切换     |
| DIMENSION_CHANGE_ACK     | 14  | 维度切换确认     |
| START_GLIDE              | 15  | 开始滑翔       |
| STOP_GLIDE               | 16  | 停止滑翔       |
| BUILD_DENIED             | 17  | 建造被拒绝      |
| CONTINUE_BREAK           | 18  | 继续破坏方块     |
| SET_ENCHANTMENT_SEED     | 20  | 设置附魔种子     |
| START_SWIMMING           | 21  | 开始游泳       |
| STOP_SWIMMING            | 22  | 停止游泳       |
| START_SPIN_ATTACK        | 23  | 开始旋转攻击     |
| STOP_SPIN_ATTACK         | 24  | 停止旋转攻击     |
| OPEN_CONTAINER           | 25  | 打开容器       |

## EntityBehavior

| 名称                                       | 数据值 | 描述                        |
|------------------------------------------|-----|---------------------------|
| JUMP                                     | 1   | 跳跃动画                      |
| HURT_ANIMATION                           | 2   | 受伤动画                      |
| DEATH_ANIMATION                          | 3   | 死亡动画                      |
| ARM_SWING                                | 4   | 挥臂动画                      |
| STOP_ATTACK                              | 5   | 停止攻击动画                    |
| TAME_FAIL                                | 6   | 驯服失败动画                    |
| TAME_SUCCESS                             | 7   | 驯服成功动画                    |
| SHAKE_WET                                | 8   | 抖落水分动画                    |
| USE_ITEM                                 | 9   | 使用物品动画                    |
| EAT_GRASS_ANIMATION                      | 10  | 吃草动画                      |
| FISH_HOOK_BUBBLE                         | 11  | 鱼钩气泡动画                    |
| FISH_HOOK_POSITION                       | 12  | 鱼钩位置更新                    |
| FISH_HOOK_HOOK                           | 13  | 鱼钩钩住实体                    |
| FISH_HOOK_TEASE                          | 14  | 鱼钩逗弄动画                    |
| SQUID_INK_CLOUD                          | 15  | 鱿鱼墨云动画                    |
| ZOMBIE_VILLAGER_CURE                     | 16  | 僵尸村民治愈动画                  |
| PLAY_AMBIENT_SOUND                       | 17  | 播放环境音                     |
| RESPAWN                                  | 18  | 重生动画                      |
| IRON_GOLEM_OFFER_FLOWER                  | 19  | 铁傀儡献花                     |
| IRON_GOLEM_WITHDRAW_FLOWER               | 20  | 铁傀儡收回花                    |
| LOVE_PARTICLES                           | 21  | 繁殖粒子（爱心粒子）                |
| VILLAGER_ANGRY                           | 22  | 村民愤怒粒子                    |
| VILLAGER_HAPPY                           | 23  | 村民开心粒子                    |
| WITCH_SPELL_PARTICLES                    | 24  | 女巫法术粒子                    |
| FIREWORK_PARTICLES                       | 25  | 烟花粒子                      |
| IN_LOVE_PARTICLES                        | 26  | 恋爱粒子                      |
| SILVERFISH_SPAWN_ANIMATION               | 27  | 银鱼生成动画                    |
| GUARDIAN_ATTACK                          | 28  | 守卫攻击动画                    |
| WITCH_DRINK_POTION                       | 29  | 女巫喝药水动画                   |
| WITCH_THROW_POTION                       | 30  | 女巫扔药水动画                   |
| MINECART_TNT_PRIME_FUSE                  | 31  | 矿车TNT引爆                   |
| CREEPER_PRIME_FUSE                       | 32  | 苦力怕引爆                     |
| AIR_SUPPLY_EXPIRED                       | 33  | 气供耗尽                      |
| PLAYER_ADD_XP_LEVELS                     | 34  | 玩家增加经验等级                  |
| ELDER_GUARDIAN_CURSE                     | 35  | 上古守卫者诅咒动画                 |
| AGENT_ARM_SWING                          | 36  | 代理挥臂动画                    |
| ENDER_DRAGON_DEATH                       | 37  | 末影龙死亡动画                   |
| DUST_PARTICLES                           | 38  | 灰尘粒子（用途不明）                |
| ARROW_SHAKE                              | 39  | 箭头抖动                      |
| EATING_ITEM                              | 57  | 吃物品动画                     |
| BABY_ANIMAL_FEED                         | 60  | 喂养幼动物粒子（绿色粒子，如在作物上使用骨粉）   |
| DEATH_SMOKE_CLOUD                        | 61  | 死亡烟雾云                     |
| COMPLETE_TRADE                           | 62  | 完成交易动画                    |
| REMOVE_LEASH                             | 63  | 移除拴绳（数据1表示剪断拴绳）           |
| CARAVAN_UPDATED                          | 64  | 商队更新动画                    |
| CONSUME_TOTEM                            | 65  | 消耗图腾动画                    |
| PLAYER_CHECK_TREASURE_HUNTER_ACHIEVEMENT | 66  | 玩家检查寻宝者成就                 |
| ENTITY_SPAWN                             | 67  | 实体生成（用于Minecraft事件处理，不需要） |
| DRAGON_PUKE                              | 68  | 龙的呕吐粒子                    |
| ITEM_ENTITY_MERGE                        | 69  | 物品实体合并                    |
| START_SWIM                               | 70  | 开始游泳动画                    |
| BALLOON_POP                              | 71  | 气球爆炸动画                    |
| TREASURE_HUNT                            | 72  | 寻宝动画                      |
| AGENT_SUMMON                             | 73  | 代理召唤动画                    |
| CHARGED_CROSSBOW                         | 74  | 充能十字弓动画                   |
| FALL                                     | 75  | 跌落动画                      |
| GROW_UP                                  | 76  | 成长动画                      |

## PlayerAction

| 名称                               | 数据值 | 描述            |
|----------------------------------|-----|---------------|
| StartDestroyBlock                | 0   | 玩家开始破坏方块。     |
| AbortDestroyBlock                | 1   | 玩家中止破坏方块。     |
| StopDestroyBlock                 | 2   | 玩家停止破坏方块。     |
| GetUpdatedBlock                  | 3   | 获取更新后的方块。     |
| DropItem                         | 4   | 玩家丢弃物品。       |
| StartSleeping                    | 5   | 玩家开始睡觉。       |
| StopSleeping                     | 6   | 玩家停止睡觉。       |
| Respawn                          | 7   | 玩家重生。         |
| StartJump                        | 8   | 玩家开始跳跃。       |
| StartSprinting                   | 9   | 玩家开始冲刺。       |
| StopSprinting                    | 10  | 玩家停止冲刺。       |
| StartSneaking                    | 11  | 玩家开始潜行。       |
| StopSneaking                     | 12  | 玩家停止潜行。       |
| CreativeDestroyBlock             | 13  | 玩家在创造模式中破坏方块。 |
| ChangeDimensionAck               | 14  | 玩家改变维度确认。     |
| StartGliding                     | 15  | 玩家开始滑翔。       |
| StopGliding                      | 16  | 玩家停止滑翔。       |
| DenyDestroyBlock                 | 17  | 拒绝破坏方块。       |
| CrackBlock                       | 18  | 破坏方块时出现裂痕。    |
| ChangeSkin                       | 19  | 玩家更换皮肤。       |
| DEPRECATED_UpdatedEnchantingSeed | 20  | 已弃用：更新附魔种子。   |
| StartSwimming                    | 21  | 玩家开始游泳。       |
| StopSwimming                     | 22  | 玩家停止游泳。       |
| StartSpinAttack                  | 23  | 玩家开始旋转攻击。     |
| StopSpinAttack                   | 24  | 玩家停止旋转攻击。     |
| InteractWithBlock                | 25  | 玩家与方块互动。      |
| PredictDestroyBlock              | 26  | 预测破坏方块。       |
| ContinueDestroyBlock             | 27  | 继续破坏方块。       |
| StartItemUseOn                   | 28  | 玩家开始使用物品。     |
| StopItemUseOn                    | 29  | 玩家停止使用物品。     |
| HandledTeleport                  | 30  | 处理传送。         |
| MissedSwing                      | 31  | 玩家挥手。         |
| StartCrawling                    | 32  | 玩家开始爬行。       |
| StopCrawling                     | 33  | 玩家停止爬行。       |
| StartFlying                      | 34  | 玩家开始飞行。       |
| StopFlying                       | 35  | 玩家停止飞行。       |
| ClientAckServerData              | 36  | 客户端确认服务器数据。   |
| Count                            | 37  | 枚举的数量。        |

## OptionID

| 名称                                               | 数据值 | 描述                 |
|--------------------------------------------------|-----|--------------------|
| MP_USERNAME                                      | 0   | 玩家用户名              |
| MP_PREV_APP_NAME                                 | 1   | 上一个应用名称            |
| GAME_DIFFICULTY_NEW                              | 2   | 游戏难度               |
| GAME_THIRDPERSON                                 | 3   | 是否使用第三人称视角         |
| CTRL_INTERACTION_MODEL                           | 4   | 交互模型               |
| GFX_DPAD_SCALE                                   | 5   | 按钮大小               |
| GFX_ALWAYS_HIGHLIGHT_HOVERING_BOX_IN_CROSSHAIR   | 6   | 始终高亮交叉线中的框         |
| GFX_SHOW_ACTION_BUTTON                           | 7   | 显示行动按钮             |
| CTRL_SPRINT_ON_MOVEMENT                          | 8   | 移动时冲刺              |
| CTRL_MOVE_STICK_VISIBLE                          | 9   | 移动摇杆是否可见           |
| GFX_THUMBSTICK_OPACITY                           | 10  | 摇杆透明度              |
| CTRL_DEFAULT_MOVE_STICK_VISIBLE                  | 11  | 默认移动摇杆可见性          |
| CTRL_CREATIVE_DELAYED_BLOCK_BREAKING             | 12  | 创意模式下延迟破坏方块        |
| CTRL_ENABLE_NEW_TOUCH_CONTROL_SCHEMES            | 13  | 启用新触控控制方案          |
| MP_SERVER_VISIBLE                                | 14  | 服务器可见性             |
| MP_XBOXLIVE_VISIBLE                              | 15  | Xbox Live 可见性      |
| MP_NEX_VISIBLE                                   | 16  | 第三方主机可见性           |
| MP_PSN_VISIBLE                                   | 17  | PSN 可见性            |
| GAME_LANGUAGE                                    | 19  | 游戏语言               |
| GAME_SKINTYPEFULL                                | 20  | 皮肤类型               |
| GAME_LASTCUSTOMSKINNEW                           | 21  | 最后自定义皮肤            |
| GAME_RECENTSKIN1                                 | 22  | 最近使用的皮肤 1          |
| GAME_RECENTSKIN2                                 | 23  | 最近使用的皮肤 2          |
| GAME_RECENTSKIN3                                 | 24  | 最近使用的皮肤 3          |
| GAME_HASEVERLOGGEDINTOXBL                        | 25  | 是否曾登录 Xbox Live    |
| GAME_HASCHOSENNOTTOSIGNINTOXBL                   | 26  | 是否选择不登录 Xbox Live  |
| DVCE_FILESTORAGELOCATION                         | 27  | 文件存储位置             |
| CTRL_ISLEFTHANDED                                | 28  | 是否左撇子              |
| CTRL_STATICJOYSTICK                              | 29  | 静态摇杆               |
| CTRL_USETOUCHJOYPAD                              | 30  | 使用触控操纵杆            |
| CTRL_SWAPJUMPANDSNEAK                            | 31  | 交换跳跃和潜行操作          |
| GFX_VIEWDISTANCE                                 | 32  | 视距                 |
| GFX_PARTICLEVIEWDISTANCE                         | 33  | 粒子视距               |
| GFX_VIEWBOBBING                                  | 34  | 视角摇摆               |
| GFX_FANCYGRAPHICS                                | 35  | 精美图形               |
| GFX_TRANSPARENTLEAVES                            | 36  | 透明树叶               |
| GFX_VR_TRANSPARENTLEAVES                         | 37  | VR模式下透明树叶          |
| GFX_SMOOTHLIGHTING                               | 38  | 平滑光照               |
| GFX_VR_SMOOTHLIGHTING                            | 39  | VR模式下平滑光照          |
| GFX_UNSPECIFIED_OPTION                           | 40  | 未指定的选项             |
| GFX_FANCYSKIES                                   | 41  | 精美天空               |
| GFX_FIELD_OF_VIEW                                | 45  | 视场                 |
| GFX_MSAA                                         | 46  | 多重采样抗锯齿            |
| GFX_TEXEL_AA_2                                   | 47  | 纹素抗锯齿              |
| GFX_GAMMA                                        | 48  | 伽马值                |
| GFX_MULTITHREADED_RENDERER                       | 49  | 多线程渲染器             |
| GFX_NE_VSYNC                                     | 50  | 禁用垂直同步             |
| DEV_FILE_WATCHER                                 | 51  | 文件监视器              |
| RECEIVE_VOICE                                    | 244 | 接收语音               |
| OPEN_MICROPHONE                                  | 245 | 打开麦克风              |
| CTRL_TRADITION_CONTROLS                          | 246 | 传统控制设置             |
| OPERATOR_VER                                     | 247 | 操作员版本              |
| GFX_GRAPHICS_LEVEL_DEFAULT                       | 248 | 默认图形级别             |
| GFX_GRAPHICS_LEVEL_USER_DEFINE                   | 249 | 用户定义的图形级别          |
| GFX_GRAPHICS_LEVEL                               | 250 | 图形级别               |
| GFX_MAX_FRAMERATE                                | 251 | 最大帧率               |
| GFX_FULLSCREEN                                   | 252 | 全屏模式               |
| SHOW_ADVANCED_VIDEO_SETTINGS                     | 253 | 显示高级视频设置           |
| GFX_GUISCALE_OFFSET                              | 255 | GUI缩放偏移            |
| GFX_SPLITSCREEN_GUISCALE_OFFSET                  | 256 | 分屏GUI缩放偏移          |
| SAFE_ZONE_X                                      | 257 | 安全区X坐标             |
| SAFE_ZONE_Y                                      | 258 | 安全区Y坐标             |
| GFX_SAFE_ZONE_ALL                                | 259 | 所有安全区              |
| SCREEN_POSITION_X                                | 260 | 屏幕X坐标              |
| SCREEN_POSITION_Y                                | 261 | 屏幕Y坐标              |
| GFX_UI_PROFILE                                   | 262 | 用户界面配置             |
| BETA_NEW_DEATH_SCREEN                            | 263 | 新死亡屏幕（测试版）         |
| AUDIO_MAIN                                       | 264 | 主音频类别              |
| AUDIO_SOUND                                      | 265 | 音频设置组              |
| AUDIO_MUSIC                                      | 266 | 音乐音频类别             |
| AUDIO_AMBIENT                                    | 267 | 环境音频类别             |
| AUDIO_BLOCK                                      | 268 | 块音频类别              |
| AUDIO_HOSTILE                                    | 269 | 敌对音频类别             |
| AUDIO_NEUTRAL                                    | 270 | 中立音频类别             |
| AUDIO_RECORD                                     | 271 | 记录音频类别             |
| AUDIO_PLAYER                                     | 272 | 玩家音频类别             |
| AUDIO_WEATHER                                    | 273 | 天气音频类别             |
| AUDIO_TEXT_TO_SPEECH                             | 274 | 语音合成音频类别           |
| VR_CAMERA_MOVEMENT                               | 275 | VR相机移动             |
| VR_SNAP_ANGLE                                    | 276 | VR快照角度             |
| VR_STUTTER_TURN_CONSTANT_TIME                    | 277 | VR抖动转向常量时间         |
| VR_STUTTER_TURN_SOUND                            | 278 | VR抖动转向声音           |
| VR_MOVEMENT                                      | 279 | VR移动               |
| VR_JUMP                                          | 280 | VR跳跃               |
| VR_HEAD_STEERING                                 | 281 | VR头部操控             |
| VR_STICKY_MINING                                 | 282 | VR粘附式挖矿            |
| VR_HUD_POSITION                                  | 283 | VR HUD位置           |
| VR_SENSITIVITY                                   | 284 | VR灵敏度              |
| VR_GAMMA                                         | 285 | VR伽马值              |
| VR_RESET_PLAYER_ALIGNMENT                        | 286 | 重置玩家对齐             |
| VR_PARTICLE_VIEW_DIST                            | 287 | VR粒子视距             |
| VR_HUD_DISTANCE                                  | 288 | VR HUD距离           |
| VR_HMD_DISPLACEMENT                              | 289 | VR HMD位移           |
| VR_RENDER_DISTANCE                               | 290 | VR渲染距离             |
| VR_AUTOJUMP                                      | 291 | VR自动跳跃             |
| VR_STEREO_RENDERING                              | 292 | VR立体渲染             |
| VR_USE_NORMAL_HIT                                | 294 | 使用正常击中反应           |
| VR_USE_RED_FLASH                                 | 295 | 使用红色闪光作为击中反馈       |
| VR_RSTICK_PITCH_ASSIST                           | 296 | VR右摇杆俯仰辅助          |
| VR_RSTICK_DEADBAND                               | 297 | VR右摇杆死区            |
| VR_RSTICK_GAZEADJUST                             | 298 | VR右摇杆视线调整          |
| VR_GAZE_PITCH_BOOST                              | 299 | VR视线俯仰增强           |
| VR_LIVING_ROOM_CURSOR_CENTERED                   | 300 | VR客厅光标居中           |
| VR_TAP_TURN                                      | 301 | VR轻触转向             |
| VR_TAPTURN_SENSITIVITY                           | 302 | VR轻触转向灵敏度          |
| VR_WHEELTURN_SENSITIVITY                         | 303 | VR轮转灵敏度            |
| VR_180_TURNS                                     | 304 | VR180度转向           |
| VR_LIVINGROOM_HINT_TIME                          | 305 | VR客厅提示时间           |
| VR_MIRROR_TEXTURE                                | 306 | VR镜像纹理             |
| VR_HAND_CONTROLS_ITEM                            | 307 | VR手部控制项            |
| VR_HAND_POINTER                                  | 308 | VR手部指针             |
| VR_HANDS_VISIBLE                                 | 309 | VR手部可见性            |
| VR_UI_MOUSE_SENSITIVITY                          | 310 | VR用户界面鼠标灵敏度        |
| VR_MSAA                                          | 311 | VR多重采样抗锯齿          |
| VR_LIVING_ROOM                                   | 312 | VR客厅               |
| RIGHT_STICK_AIM                                  | 313 | 右摇杆瞄准              |
| RIGHT_STICK_AIM_SENSITIVITY                      | 314 | 右摇杆瞄准灵敏度           |
| VR_RIGHT_STICK_PITCH_ASSIST_MAX_ANGLE            | 315 | VR右摇杆俯仰辅助最大角度      |
| VR_RIGHT_STICK_PITCH_ASSIST_STEPPINGS            | 316 | VR右摇杆俯仰辅助步进        |
| STORE_HAS_PURCHASED_COINS                        | 317 | 是否已购买硬币            |
| SWITCH_COIN_DEBUG                                | 318 | 开关硬币调试             |
| DEV_SHOW_CHUNK_MAP                               | 319 | 显示块地图              |
| DEV_CHUNK_MAP_MODE                               | 320 | 块地图模式              |
| DEV_DISABLE_RENDER_TERRAIN                       | 321 | 禁用渲染地形             |
| DEV_DISABLE_RENDER_ENTITIES                      | 322 | 禁用渲染实体             |
| DEV_DISABLE_RENDER_BLOCK_ENTITIES                | 323 | 禁用渲染方块实体           |
| DEV_DISABLE_RENDER_PARTICLES                     | 324 | 禁用渲染粒子             |
| DEV_DISABLE_RENDER_SKY                           | 325 | 禁用渲染天空             |
| DEV_DISABLE_RENDER_WEATHER                       | 326 | 禁用渲染天气             |
| DEV_DISABLE_RENDER_HUD                           | 327 | 禁用渲染HUD            |
| DEV_DISABLE_RENDER_ITEM_IN_HAND                  | 328 | 禁用手中物品渲染           |
| DEV_DISABLE_RENDER_MAIN_MENU_CUBEMAP             | 329 | 禁用主菜单立方体贴图渲染       |
| DEV_DISABLE_RENDER_MAIN_MENU_PAPERDOLL_ANIMATION | 330 | 禁用主菜单纸娃娃动画渲染       |
| DEV_ENABLE_PROFILER                              | 331 | 启用分析器              |
| DEV_BENCHMARK_MODE_TIME                          | 333 | 基准测试模式时间           |
| DEV_DISABLE_CLIENT_BLOB_CACHE                    | 334 | 禁用客户端缓存            |
| DEV_FORCE_CLIENT_BLOB_CACHE                      | 335 | 强制启用客户端缓存          |
| DEV_CONNECTION_QUALITY                           | 336 | 连接质量               |
| DEV_SHOW_LATENCY_GRAPH                           | 337 | 显示延迟图表             |
| DEV_RENDER_BOUNDING_BOX                          | 338 | 渲染边界框              |
| DEV_RENDER_PATHS                                 | 339 | 渲染路径               |
| DEV_RENDER_GOAL_STATE                            | 340 | 渲染目标状态             |
| DEV_NEW_PARTICLE_SYSTEM                          | 342 | 新粒子系统              |
| DEV_ACHIEVEMENTS_ALWAYS_ENABLED                  | 345 | 始终启用成就             |
| DEV_CREATE_REALM_WITHOUT_PURCHASE                | 346 | 无需购买创建领域           |
| DEV_USE_IPV6_ONLY                                | 347 | 仅使用IPv6            |
| DEV_OVERRIDE_XBOX_SANDBOX                        | 348 | 重写Xbox沙盒           |
| DEV_XBOX_SANDBOX                                 | 349 | Xbox沙盒             |
| DISCOVERY_ENVIRONMENT                            | 360 | 发现环境               |
| DEV_REALMS_ENVIRONMENT                           | 361 | 领域环境               |
| DEV_REALMS_SKU                                   | 366 | 领域SKU              |
| DEV_STORE_OFFER_QUERY_REQUIRES_XBL               | 367 | 商店报价查询需要XBL        |
| DEV_RESET_CLIENT_ID                              | 368 | 重置客户端ID            |
| DEV_ENABLE_DEBUG_HUD_OVERLAY                     | 388 | 启用调试HUD覆盖          |
| SHOW_BUILD_INFO                                  | 390 | 显示构建信息             |
| OPTION_USE_OVERRIDE_VERSION                      | 396 | 使用覆盖版本设置           |
| REALMS_SHOW_FRIEND_INVITES_ONLY                  | 397 | 仅显示好友邀请            |
| NUMBER_OF_OWNED_REALMS                           | 398 | 拥有的领域数量            |
| NUMBER_OF_FRIENDS_REALMS                         | 399 | 朋友的领域数量            |
| REALMS_VIEW_UPSELL_SCREEN_COUNT                  | 400 | 领域查看附加销售屏幕计数       |
| SHOWN_RATINGS_PROMPT                             | 401 | 显示评级提示             |
| SAVE_AND_QUIT_COUNT                              | 402 | 保存并退出计数            |
| SHOW_WORLDS_TRIAL_BUTTON                         | 403 | 显示世界试用按钮           |
| ALLOW_CELLULAR_DATA                              | 404 | 允许使用移动数据           |
| AUTO_UPDATE_MODE                                 | 406 | 自动更新模式             |
| AUTO_UPDATE_ENABLED                              | 407 | 启用自动更新             |
| WEBSOCKET_ENCRYPTION                             | 408 | WebSocket加密        |
| TEXT_TO_SPEECH_DISCOVERED                        | 409 | 发现文本转语音            |
| MONITOR_PLATFORM_TEXT_TO_SPEECH                  | 410 | 监控平台文本转语音          |
| CHAT_TEXT_TO_SPEECH                              | 411 | 聊天文本转语音            |
| UI_TEXT_TO_SPEECH                                | 412 | 用户界面文本转语音          |
| OPEN_CHAT_MESSAGE                                | 413 | 打开聊天消息             |
| CTRL_SENSITIVITY                                 | 414 | 控制器灵敏度             |
| CTRL_SMOOTH_ROTATION_SPEED                       | 415 | 控制器平滑旋转速度          |
| CTRL_INVERT_MOUSE                                | 416 | 反转鼠标控制             |
| CTRL_AUTOJUMP                                    | 417 | 控制器自动跳跃            |
| CTRL_FULL_KEYBOARD_GAMEPLAY                      | 418 | 完整键盘游戏玩法           |
| FEEDBACK_DESTROY_VIBRATION                       | 419 | 反馈破坏振动             |
| FEEDBACK_SPLIT_VIBRATION                         | 420 | 反馈分割振动             |
| GFX_TOGGLE_CLOUDS                                | 421 | 切换云层显示             |
| CTRL_TOGGLE_CROUCH                               | 422 | 切换蹲伏状态             |
| GFX_SPLITSCREEN                                  | 442 | 分屏显示               |
| GFX_HIDE_HUD                                     | 443 | 隐藏HUD              |
| GFX_HIDE_HAND                                    | 444 | 隐藏手部显示             |
| VR_HIDE_HUD                                      | 445 | 隐藏VR HUD           |
| VR_HIDE_HAND                                     | 446 | 隐藏VR手部             |
| GFX_INGAME_PLAYER_NAMES                          | 447 | 游戏内玩家名称显示          |
| GFX_SPLITSCREEN_INGAME_PLAYER_NAMES              | 448 | 分屏游戏内玩家名称显示        |
| GFX_INTERFACE_OPACITY                            | 449 | 界面不透明度             |
| GFX_SPLITSCREEN_INTERFACE_OPACITY                | 450 | 分屏界面不透明度           |
| GFX_TEXT_BACKGROUND_OPACITY                      | 451 | 文本背景不透明度           |
| GAME_ACK_AUTOSAVE                                | 452 | 游戏确认自动保存           |
| REALMSPLUS_UPGRADE_NOTICE_STATE                  | 453 | 领域+升级通知状态          |
| GFX_SHOW_AUTOSAVE_ICON                           | 454 | 显示自动保存图标           |
| GFX_HAS_SET_SAFE_ZONE                            | 455 | 是否已设置安全区           |
| DEV_FIND_MOBS                                    | 456 | 开发者查找生物            |
| GFX_FIELD_OF_VIEW_TOGGLE                         | 457 | 切换视野范围             |
| GFX_GAMEPAD_CURSOR                               | 458 | 游戏手柄光标             |
| HDR_BRIGHTNESS                                   | 493 | HDR亮度              |
| HAS_SET_HDR_BRIGHTNESS                           | 494 | 是否已设置HDR亮度         |
| CTRL_HOTBAR_ONLY_TOUCH                           | 497 | 热键栏仅触控             |
| GFX_GAMEPAD_CURSOR_SENSITIVITY                   | 501 | 游戏手柄光标灵敏度          |
| GAME_LAST_SHOWN_REALMS_ENDED_DATE                | 502 | 上次显示的领域结束日期        |
| REALMS_SUNSET_TIER                               | 503 | 领域日落等级             |
| GEO_SUNSETTING                                   | 504 | 地理日落               |
| HAS_SHOWN_BEING_SUNSET_NOTICE                    | 505 | 显示日落通知             |
| HAS_SHOWN_SUNSET_NOTICE                          | 506 | 显示日落通知             |
| DEV_SUNSETTING_TIER                              | 507 | 开发者日落等级            |
| DEV_SUNSET_STATE                                 | 508 | 开发者日落状态            |
| DEV_USE_SUNSET_OVERRIDES                         | 509 | 使用日落覆盖             |
| GAME_SHOWN_PLATFORM_NETWORK_CONNECT              | 511 | 显示平台网络连接           |
| SCREEN_ANIMATIONS                                | 512 | 屏幕动画               |
| CTRL_SWAP_GAMEPAD_AB_BUTTONS                     | 513 | 交换游戏手柄AB按钮         |
| CTRL_SWAP_GAMEPAD_XY_BUTTONS                     | 514 | 交换游戏手柄XY按钮         |
| CTRL_CLEAR_HOTBAR                                | 515 | 清空热键栏              |
| GFX_BUBBLE_PARTICLES                             | 516 | 泡沫粒子               |
| GAME_SHOWN_PLATFORM_PREMIUM_UPSELL               | 517 | 显示平台高级附加销售         |
| CHAT_COLOR_CODE                                  | 532 | 聊天颜色代码             |
| CHAT_FONT_SIZE                                   | 533 | 聊天字体大小             |
| CHAT_LINE_SPACING                                | 534 | 聊天行间距              |
| CHAT_MENTIONS_COLOR_CODE                         | 535 | 聊天提及颜色代码           |
| CHAT_TYPEFACE                                    | 536 | 聊天字体类型             |
| CONTENT_LOG_FILE                                 | 538 | 内容日志文件             |
| CONTENT_LOG_GUI                                  | 539 | 内容日志GUI            |
| GAMEPLAY_TIPS_ENABLED                            | 541 | 启用游戏提示             |
| GAMEPLAY_TIPS_SHOULD_BE_SHOWN                    | 542 | 应显示游戏提示            |
| DAY_ONE_EXPERIENCE_COMPLETED                     | 560 | 第一天体验已完成           |
| SELECT_CRAFTTABLE_TIPS_SHOULD_BE_SHOWN           | 561 | 应显示选择工艺台提示         |
| PLACE_CRAFTTABLE_TIPS_SHOULD_BE_SHOWN            | 562 | 应显示放置工艺台提示         |
| USE_CRAFTTABLE_TIPS_SHOULD_BE_SHOWN              | 563 | 应显示使用工艺台提示         |
| MAKE_CRAFTTABLE_TIPS_SHOULD_BE_SHOWN             | 564 | 应显示制作工艺台提示         |
| NEED_MORE_MATERIALS_TIPS_SHOULD_BE_SHOWN         | 565 | 应显示需要更多材料提示        |
| IS_LEGACY_PLAYER                                 | 566 | 是否为遗留玩家            |
| TOAST_NOTIFICATION_DURATION                      | 567 | Toast通知持续时间        |
| CHAT_MESSAGE_DURATION                            | 568 | 聊天消息持续时间           |
| DEV_ENABLE_TEXTURE_HOT_RELOADER                  | 569 | 启用纹理热重载            |
| PLAYFAB_COMMERCE_ENABLED                         | 570 | 启用PlayFab商务        |
| DO_NOT_SHOW_MULTIPLAYER_ONLINE_SAFETY_WARNING    | 573 | 不显示多人在线安全警告        |
| ONLY_SHOW_TRUSTED_SKINS                          | 574 | 仅显示受信任的皮肤          |
| CAMERA_SHAKE                                     | 577 | 相机震动               |
| DEV_TRANSPORT_LAYER_TYPE                         | 579 | 开发者传输层类型           |
| GFX_GUI_ACCESSIBILITY_SCALING                    | 581 | GUI可访问性缩放          |
| GFX_RAYTRACING                                   | 582 | 启用光线追踪             |
| RAYTRACING_VIEW_DISTANCE                         | 583 | 光线追踪视距             |
| DEFERRED_VIEW_DISTANCE                           | 584 | 延迟视距               |
| GFX_UPSCALING                                    | 585 | 启用上采样              |
| RESOURCE_CONCATENATION_ENABLED                   | 586 | 启用资源连接             |
| CTRL_SPYGLASS_DAMP                               | 594 | 控制器望远镜阻尼           |
| CTRL_DWELL_BEFORE_DRAG_TIME                      | 595 | 拖动前停留时间            |
| CTRL_STACK_SPLITTING_TRIGGER_TIME                | 596 | 堆叠拆分触发时间           |
| SHOW_RENDER_DISTANCE_WARNING_MODAL               | 604 | 显示渲染距离警告模态框        |
| DISPLAY_SKIN_ROTATION_SPEED_MULTIPLIER           | 605 | 显示皮肤旋转速度乘数         |
| HAS_SHOWN_STORAGE_LOCATION_WARNING               | 607 | 显示存储位置警告           |
| GAME_EVENT_RETENTION_TICKS                       | 608 | 游戏事件保留计时           |
| DEEP_DARK_DEBUG_RENDER                           | 609 | 深暗调试渲染             |
| COPY_COORDINATE_UI                               | 610 | 复制坐标用户界面           |
| DARKNESS_EFFECT_MODIFIER                         | 611 | 黑暗效果修改器            |
| GLINT_STRENGTH                                   | 612 | 闪光强度               |
| GLINT_SPEED                                      | 613 | 闪光速度               |
| TOUCH_CONTROL_SELECTION_SCREEN                   | 615 | 触控控制选择屏幕           |
| GATHERING_CONFIG_ID_OVERRIDE                     | 617 | 收集配置ID覆盖           |
| DEVICE_LOST_TELEMETRY_ENABLED                    | 618 | 启用设备丢失遥测           |
| HIDDEN_ENABLE_CLIENT_SCRIPT                      | 620 | 启用隐藏客户端脚本          |
| HIDDEN_SCRIPT_ROUTER                             | 621 | 隐藏脚本路由             |
| HIDDEN_SCRIPT_KEY                                | 622 | 隐藏脚本键              |
| HIDDEN_CUSTOM_TOUCH_ZONE                         | 623 | 隐藏自定义触控区域          |
| GFX_RESIZABLE_UI                                 | 625 | 启用可调整大小的UI         |
| GFX_HOTBAR_SCALE                                 | 626 | 热键栏缩放              |
| REALMS_PLUS_LAST_SHOWN_GOOGLE_HOLD_DATE          | 627 | 领域+上次显示的Google持有日期 |
| CTRL_RESET_ON_START                              | 628 | 启动时重置控制器           |
| GPU_VALIDATION_ENABLED                           | 629 | 启用GPU验证            |
| GPU_VALIDATION_VERBOSE                           | 630 | 启用GPU验证详细信息        |
| GPU_VALIDATION_OUTPUT_MANAGER_ENABLED            | 631 | 启用GPU验证输出管理器       |
| GPU_VALIDATION_DISABLE_ERROR_SUPPRESS            | 632 | 禁用GPU验证错误抑制        |
| LOAD_RENDERDOC_DLL                               | 633 | 加载RenderDoc DLL    |
| DEV_CONTROL_TOWER_OVERRIDE_TRANSPORT_LAYER       | 639 | 开发者控制塔覆盖传输层        |
| DO_NOT_SHOW_MULTIPLAYER_IP_SAFETY_WARNING        | 640 | 不显示多人在线IP安全警告      |
| DO_NOT_SHOW_WORLDS_WITHOUT_ENTITLEMENT_WARNING   | 641 | 不显示无权访问的世界警告       |
| DO_NOT_SHOW_OLD_WORLDS_WARNING                   | 642 | 不显示旧世界警告           |
| EMOTE_CHAT                                       | 643 | 表情聊天               |

## FunctionID

| 序号 | 名称      | ID                       |
|----|---------|--------------------------|
| 1  | 能力编辑    | fun_abilities            |
| 3  | 附魔编辑器   | fun_enchant_menu         |
| 4  | 游戏模式修改  | fun_game_mode            |
| 5  | 快捷传送菜单  | fun_teleport_menu        |
| 6  | 物品编辑器   | fun_item_editor          |
| 7  | 网络数据包管理 | fun_network_packet_mgr   |
| 8  | 花雨庭远程商店 | fun_open_shop            |
| 9  | 自动瞄准    | fun_aimbot               |
| 10 | 踏空      | fun_air_jump             |
| 11 | 冲刺      | fun_air_sprint           |
| 12 | 虚空回弹    | fun_anti_void            |
| 13 | 自动手持搭路  | fun_auto_build           |
| 14 | 自动破坏    | fun_auto_destroy         |
| 15 | 自动破坏方块  | fun_auto_destroy_block   |
| 16 | 自动前进    | fun_auto_forward         |
| 17 | 自动滑翔    | fun_gliding              |
| 18 | 自动选择方块  | fun_auto_block           |
| 19 | 自动选择武器  | fun_auto_weapons         |
| 20 | 自动冲刺    | fun_auto_sprint          |
| 21 | 自动游泳    | fun_swimming             |
| 22 | 自动图腾    | fun_auto_totem           |
| 23 | 移动跳跃    | fun_move_jump            |
| 24 | 点击范围破坏  | fun_click_destroy        |
| 25 | 点击骑乘    | fun_entity_riding        |
| 26 | 点击传送    | fun_click_teleport       |
| 27 | 无粒子生成   | fun_no_particle          |
| 28 | 麒麟臂     | fun_fast_destroy         |
| 29 | 快速添加物品  | fun_fast_add_item        |
| 30 | 游戏变速    | fun_timer                |
| 31 | 实体碰撞箱   | fun_hitbox               |
| 32 | 高跳      | fun_jump_high            |
| 33 | 杀戮光环    | fun_killaura             |
| 34 | 玩家锁背    | fun_lock_behind          |
| 35 | 重复发送数据包 | fun_multiple_packet      |
| 36 | 抗击退     | fun_no_knockback         |
| 37 | 停止发送数据包 | fun_no_packet            |
| 38 | 视图模型    | fun_view_model           |
| 39 | 智能战斗    | fun_smart_team           |
| 40 | 环绕攻击    | fun_surround_attack      |
| 41 | 主界面模块   | fun_hud_module           |
| 42 | 实体模型变更  | fun_reach                |
| 43 | 自动穿装    | fun_auto_armor           |
| 44 | 无摔落伤害   | fun_no_fall              |
| 45 | 无火焰附加   | fun_no_fire              |
| 46 | 自动开箱    | fun_chest_aura           |
| 47 | 容器快速拿物  | fun_chest_stealer        |
| 48 | 自动吃物    | fun_auto_eat             |
| 49 | 单人游戏无敌  | fun_invincible           |
| 50 | 无蛛网减速   | fun_no_web               |
| 51 | 连锁挖矿    | fun_chain_mining         |
| 52 | 自动钓鱼    | fun_auto_fishing         |
| 53 | 自动爬梯    | fun_auto_ladder          |
| 54 | 音频控制    | fun_sound_engine         |
| 55 | 水上漂     | fun_jesus                |
| 56 | 方块操作距离  | fun_extended_block_reach |
| 57 | 望远镜     | fun_zoom                 |
| 58 | NBT编辑器  | fun_nbt_editor           |
| 59 | 实体渲染    | fun_name_tags            |
| 60 | 箱子渲染    | fun_chest_esp            |
| 61 | 飞行坐骑    | fun_ride_flying          |
| 62 | 自由视角    | fun_free_camera          |
| 63 | 快速建造    | fun_fast_build           |
| 64 | 方块渲染    | fun_block_render         |
| 66 | 实体事件管理器 | fun_entity_event_manager |
| 67 | 矿物透视    | fun_xray                 |
| 68 | 崩溃服务器   | fun_crash_server         |
| 70 | 背包移动    | fun_inventory_move       |
| 71 | 联机假名    | fun_fake_name            |
| 73 | 方块轮廓    | fun_block_outline        |
| 74 | 实体追踪    | fun_tracer               |
| 75 | ESP     | fun_esp                  |
| 76 | 自动点击    | fun_auto_clicker         |
| 77 | 使用物品不减速 | fun_no_slow_down         |
| 78 | 一步登天    | fun_step                 |
| 79 | 自动开弓    | fun_auto_bow             |

## Button

| 键位名称                                 | 描述         |
|--------------------------------------|------------|
| button.jump                          | 跳跃         |
| button.change_flight_height          | 切换飞行高度     |
| button.sneak                         | 潜行         |
| button.up                            | 向上移动       |
| button.down                          | 向下移动       |
| button.left                          | 向左移动       |
| button.right                         | 向右移动       |
| button.upleft                        | 向左上移动      |
| button.upright                       | 向右上移动      |
| button.ascend                        | 上升（飞行模式）   |
| button.descend                       | 下降（飞行模式）   |
| button.sprint                        | 奔跑         |
| button.fly_down_slow                 | 缓慢下降       |
| button.fly_up_slow                   | 缓慢上升       |
| button.ascendScaffolding             | 登上脚手架      |
| button.descendScaffolding            | 从脚手架下降     |
| button.sneak_toggle                  | 潜行切换       |
| button.look_up_slight                | 微微向上看      |
| button.look_down_slight              | 微微向下看      |
| button.look_up_right                 | 向右上看       |
| button.look_up                       | 向上看        |
| button.look_up_left                  | 向左上看       |
| button.look_right                    | 向右看        |
| button.look_center                   | 视角居中       |
| button.look_left                     | 向左看        |
| button.look_down_right               | 向右下看       |
| button.look_down                     | 向下看        |
| button.look_down_left                | 向左下看       |
| button.look_up_smooth                | 平滑向上看      |
| button.look_down_smooth              | 平滑向下看      |
| button.look_left_smooth              | 平滑向左看      |
| button.look_right_smooth             | 平滑向右看      |
| button.sprint_toggle                 | 奔跑切换       |
| button.pointer_pressed               | 指针点击       |
| button.pause                         | 暂停游戏       |
| button.emote                         | 表情动作       |
| button.inventory                     | 打开物品栏      |
| button.open_crafting                 | 打开合成界面     |
| button.drop                          | 丢弃物品       |
| button.slot1                         | 快捷栏槽位1     |
| button.slot2                         | 快捷栏槽位2     |
| button.slot3                         | 快捷栏槽位3     |
| button.slot4                         | 快捷栏槽位4     |
| button.slot5                         | 快捷栏槽位5     |
| button.slot6                         | 快捷栏槽位6     |
| button.slot7                         | 快捷栏槽位7     |
| button.slot8                         | 快捷栏槽位8     |
| button.slot9                         | 快捷栏槽位9     |
| button.set_spawn                     | 设置重生点      |
| button.enable_text_to_speech         | 启用文字转语音    |
| button.force_screens_type_pocket     | 强制启用手机版界面  |
| button.force_gui_scaling             | 强制界面缩放     |
| button.new_ui_debug                  | 新UI调试      |
| button.focus_debug                   | 聚焦调试元素     |
| button.pick_debug_object             | 选中调试对象     |
| button.reload_ui_definitions         | 重载UI定义     |
| button.voice_trans                   | 语音翻译       |
| button.fold_menu                     | 折叠菜单       |
| button.report_cheat                  | 举报作弊       |
| button.destroy_or_attack             | 破坏/攻击      |
| button.build_or_interact             | 建造/互动      |
| button.stick_cursor                  | 固定光标       |
| button.turn_interact                 | 转身互动       |
| button.destroy_or_interact           | 破坏或互动      |
| button.build_or_attack               | 建造或攻击      |
| button.interact                      | 互动         |
| button.inventory_left                | 物品栏左移      |
| button.inventory_right               | 物品栏右移      |
| button.simulate_touch                | 模拟触摸       |
| button.full_screen                   | 全屏切换       |
| button.paddle_left                   | 船桨左划       |
| button.paddle_right                  | 船桨右划       |
| button.dismount                      | 下坐骑        |
| button.hide_jump_button              | 隐藏跳跃按钮     |
| button.hide_sneak_button             | 隐藏潜行按钮     |
| button.chat                          | 聊天         |
| button.copy_current_coordinates      | 复制当前位置坐标   |
| button.copy_facing_block_coordinates | 复制朝向方块坐标   |
| button.code_builder                  | 编码工具       |
| button.immersive_reader              | 沉浸式阅读器     |
| button.toggle_control_hud            | 切换控制HUD显示  |
| button.toggle_perspective            | 切换视角       |
| button.console                       | 控制台        |
| button.menu_swap_vr_mode             | 菜单切换 VR 模式 |
| button.multi_touch                   | 多点触控       |
| button.dictationEvent                | 启动听写事件     |
| button.holo_zoom_in                  | 全息界面放大     |
| button.holo_zoom_out                 | 全息界面缩小     |
| button.holo_zoom_max                 | 全息界面最大缩放   |
| button.holo_zoom_min                 | 全息界面最小缩放   |
| button.holo_lightningbolt            | 全息闪电效果     |
| button.holo_raiseworld               | 全息抬高世界     |
| button.holo_lowerworld               | 全息降低世界     |
| button.holo_follow                   | 全息跟随       |
| button.holo_stopfollow               | 停止全息跟随     |
| button.holo_follownext               | 全息跟随下一个    |
| button.advancetime_sunrise           | 时间快进至日出    |
| button.advancetime_morning           | 时间快进至早晨    |
| button.advancetime_afternoon         | 时间快进至下午    |
| button.advancetime_evening           | 时间快进至傍晚    |
| button.advancetime_midnight          | 时间快进至午夜    |
| button.holo_placescreen              | 放置全息屏幕     |
| button.holo_placeviewer              | 放置全息查看器    |
| button.holo_goback                   | 全息界面返回     |
| button.holo_screenmode               | 全息屏幕模式切换   |
| button.holo_realitymode              | 全息现实模式切换   |
| button.holo_realitymode_VR           | 切换至VR现实模式  |
| button.holo_realitymode_reality      | 切换至普通现实模式  |
| button.holo_autoalign                | 全息自动对齐     |
| button.holo_pan                      | 全息平移       |
| button.holo_rotate                   | 全息旋转       |
| button.holo_tilt                     | 全息倾斜       |
| button.holo_pivotleft                | 全息左旋       |
| button.holo_pivotright               | 全息右旋       |
| button.holo_zoom_mode                | 全息缩放模式     |
| button.holo_screen_2d                | 全息2D屏幕模式   |
| button.holo_screen_3d                | 全息3D屏幕模式   |
| button.holo_small_screen             | 小型全息屏幕     |
| button.holo_medium_screen            | 中型全息屏幕     |
| button.holo_large_screen             | 大型全息屏幕     |
| button.holo_huge_screen              | 超大全息屏幕     |
| button.holo_mark                     | 全息标记       |
| button.holo_debug_toggle_thirdperson | 调试切换第三人称视角 |
| button.holo_debug_toggle_lsr         | 调试切换LSR模式  |
| button.holo_debug_toggle_anchors     | 调试切换锚点     |
| button.mobeffects                    | 移动物体特效     |
| button.hotbar_drop_all               | 快捷栏全部丢弃    |
| button.toggle_raytracing             | 切换光线追踪模式   |
| button.content_log_history_chord     | 内容日志记录快捷键  |

## ContainerID

| ID | 名称                                    | 描述（容器功能）      |
|----|---------------------------------------|---------------|
| 0  | `AnvilInputContainer`                 | 铁砧输入容器        |
| 1  | `AnvilMaterialContainer`              | 铁砧材料容器        |
| 2  | `AnvilResultPreviewContainer`         | 铁砧输出预览容器      |
| 3  | `SmithingTableInputContainer`         | 锻造台输入容器       |
| 4  | `SmithingTableMaterialContainer`      | 锻造台材料容器       |
| 5  | `SmithingTableResultPreviewContainer` | 锻造台输出预览容器     |
| 6  | `ArmorContainer`                      | 盔甲栏容器         |
| 7  | `LevelEntityContainer`                | 实体容器          |
| 8  | `BeaconPaymentContainer`              | 信标容器          |
| 9  | `BrewingStandInputContainer`          | 酿造台输入容器       |
| 10 | `BrewingStandResultContainer`         | 酿造台输出容器       |
| 11 | `BrewingStandFuelContainer`           | 酿造台燃料容器       |
| 12 | `CombinedHotbarAndInventoryContainer` | 快捷栏与背包组合容器    |
| 13 | `CraftingInputContainer`              | 工作台输入容器       |
| 14 | `CraftingOutputPreviewContainer`      | 工作台输出预览容器     |
| 15 | `RecipeConstructionContainer`         | 合成书-建筑分类      |
| 16 | `RecipeNatureContainer`               | 合成书-自然分类      |
| 17 | `RecipeCustomContainer`               | 合成书-自定义分类     |
| 18 | `RecipeItemsContainer`                | 合成书-物品列表      |
| 19 | `RecipeSearchContainer`               | 合成书-搜索结果      |
| 20 | `RecipeSearchBarContainer`            | 合成书-搜索栏       |
| 21 | `RecipeEquipmentContainer`            | 合成书-装备分类      |
| 22 | `RecipeBookContainer`                 | 合成书主容器        |
| 23 | `EnchantingInputContainer`            | 附魔台输入容器       |
| 24 | `EnchantingMaterialContainer`         | 附魔台材料（青金石）    |
| 25 | `FurnaceFuelContainer`                | 熔炉燃料容器        |
| 26 | `FurnaceIngredientContainer`          | 熔炉原料容器        |
| 27 | `FurnaceResultContainer`              | 熔炉输出容器        |
| 28 | `HorseEquipContainer`                 | 马具容器（鞍、马铠）    |
| 29 | `HotbarContainer`                     | 快捷栏容器         |
| 30 | `InventoryContainer`                  | 玩家背包容器        |
| 31 | `ShulkerBoxContainer`                 | 潜影盒容器         |
| 32 | `TradeIngredient1Container`           | 交易输入槽位 1      |
| 33 | `TradeIngredient2Container`           | 交易输入槽位 2      |
| 34 | `TradeResultPreviewContainer`         | 交易输出结果容器      |
| 35 | `OffhandContainer`                    | 副手容器          |
| 36 | `CompoundCreatorInput`                | 化合物创建器输入（教育版） |
| 37 | `CompoundCreatorOutputPreview`        | 化合物创建器输出      |
| 38 | `ElementConstructorOutputPreview`     | 元素构造器输出       |
| 39 | `MaterialReducerInput`                | 材料还原器输入容器     |
| 40 | `MaterialReducerOutput`               | 材料还原器输出容器     |
| 41 | `LabTableInput`                       | 实验桌输入容器       |
| 42 | `LoomInputContainer`                  | 织布机旗帜输入容器     |
| 43 | `LoomDyeContainer`                    | 织布机染料容器       |
| 44 | `LoomMaterialContainer`               | 织布机图案模板容器     |
| 45 | `LoomResultPreviewContainer`          | 织布机输出预览容器     |
| 46 | `BlastFurnaceIngredientContainer`     | 高炉原料容器        |
| 47 | `SmokerIngredientContainer`           | 烟熏炉原料容器       |
| 48 | `Trade2Ingredient1Container`          | 交易配方 2 输入 1   |
| 49 | `Trade2Ingredient2Container`          | 交易配方 2 输入 2   |
| 50 | `Trade2ResultPreviewContainer`        | 交易配方 2 输出容器   |
| 51 | `GrindstoneInputContainer`            | 砂轮输入容器        |
| 52 | `GrindstoneAdditionalContainer`       | 砂轮附加物品容器      |
| 53 | `GrindstoneResultPreviewContainer`    | 砂轮输出容器        |
| 54 | `StonecutterInputContainer`           | 切石机输入容器       |
| 55 | `StonecutterResultPreviewContainer`   | 切石机输出容器       |
| 56 | `CartographyInputContainer`           | 制图台输入容器（地图）   |
| 57 | `CartographyAdditionalContainer`      | 制图台附加容器（玻璃板）  |
| 58 | `CartographyResultPreviewContainer`   | 制图台输出容器       |
| 59 | `BarrelContainer`                     | 木桶容器          |
| 60 | `CursorContainer`                     | 鼠标指针物品容器      |
| 61 | `CreatedOutputContainer`              | 创建输出容器（通用）    |
| 62 | `SmithingTableTemplateContainer`      | 锻造台模板容器       |
