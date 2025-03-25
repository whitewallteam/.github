# 命令方块编辑

```javascript
function onPlayerBuildBlockEvent(playerId, x, y, z, side) {
    const data = {
        ['mode']: 'Repeating',
        ['isRedStoneMode']: true, // 是否需要红石
        ['isConditional']: true, // 是否需要条件
        ['command']: 'say 这个命令方块被改了',
        ['lastOutput']: '输出内容',
        ['name']: '命令方块名称',
        ['tickDelay']: 0,
        ['shouldTrackOutput']: true,
        ['executeOnFirstTick']: true,
    };
    setCommandBlockData(x, y, z, data)
    clientMessage('更新命令方块数据')
    return true;
}

function onPlayerAttackEvent(playerId, targetId) {
    const type = getEntityTypeId(targetId);
    if (type === 524388) {
        const data = {
            ['command']: 'say 这个命令方块矿车被改了',
            ['lastOutput']: '输出内容',
            ['name']: '命令方块矿车名称',
            ['tickDelay']: 0,
            ['shouldTrackOutput']: true,
            ['executeOnFirstTick']: true,
        };
        setCommandBlockMinecartData(targetId, data)
        clientMessage('更新命令方块矿车数据')
        return true;
    }
}

function onSendChatMessageEvent(message) {
    if (message === '退出脚本') {
        clientMessage('§b[命令编辑] §e脚本已关闭')
        exit()
        return true;
    }
}

clientMessage('§b[命令编辑] §e脚本加载完成')
```