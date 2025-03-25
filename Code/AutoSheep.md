# 自动剪羊毛

```javascript
function onSendChatMessageEvent(message) {
    if (message === '退出脚本') {
        clientMessage('§b[自动剪羊毛] §e脚本已关闭')
        exit()
        return true;
    }
}

function onTickEvent(){
    const id = getLocalPlayerUniqueID()
    const item = getEntityCarriedItem(id)
    // 判断是否手持剪刀
    if (item.namespace == 'minecraft:shears') {
        const list = getEntityList()
        for (const v of list) {
            if (getEntityNamespace(v) == "minecraft:sheep") {
                interactEntity(v)
            }
        }
    }
}

clientMessage('§b[自动剪羊毛] §e脚本加载完成')
```