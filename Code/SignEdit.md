# 告示牌编辑

```javascript
function onPlayerBuildBlockEvent(playerId, x, y, z, side) {
    setBlockEntityData(x, y, z, string_format('{IgnoreLighting:0b,PersistFormatting:1b,SignTextColor:-16777216,Text:"{}}",TextIgnoreLegacyBugResolved:0b,TextOwner:"",id:"Sign",isMovable:1b,x:{},y:{},z:{}}', '这个告示牌被修改了\n第二行\n第三行', x, y, z))
    clientMessage('更新告示牌数据')
    return true;
}

function onSendChatMessageEvent(message) {
    if (message === '退出脚本') {
        clientMessage('§b[告示牌编辑] §e脚本已关闭')
        exit()
        return true;
    }
}

clientMessage('§b[告示牌编辑] §e脚本加载完成')
```