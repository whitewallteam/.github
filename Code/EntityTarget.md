# 实体目标

```javascript
let target;

function onPlayerAttackEvent(playerId,targetId){
    if(target){
        setEntityTarget(target,targetId)
        const name1 = getEntityName(target),name2 = getEntityName(targetId)
        showTipMessage(`已经设置${name1}的目标为${name2}`)
        target = null
    } else {
        target = targetId;
        showTipMessage('§e请点击第二个目标')
    }
    return true;
}

function onSendChatMessageEvent(message) {
    if (message === '退出脚本') {
        clientMessage('§b[实体目标编辑] §e脚本已关闭')
        exit()
        return true;
    }
}

clientMessage('§b[实体目标编辑] §e脚本加载完成')
```