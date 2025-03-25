# 入门

让我们来通过一段代码进入跑路科技的世界！

```javascript
const id = getLocalPlayerUniqueID();
if (isPlayer(id)) {
    const size = getEntitySize(id);
    clientMessage("我叫" + getEntityName(id), "我在世界的唯一ID是" + id, "实体类型为" +
    getEntityTypeId(id), "碰撞箱" + size.x + " " + size.y);
}

const list = getEntityList();

const nbt = getEntityNBT(list[0]);
clientMessage('第一个生物NBT:' + nbt);
const rot = getEntityRot(list[0]);
clientMessage('第一个生物视角:' + rot.pitch + ' ' + rot.yaw)

for (var i = 0; i < list.length; i++) {
    if (list[i] !== id && getEntityTypeId(list[i]) !== 64) {
        setEntityName(list[i], "猪");
        var pos = getEntityPos(list[i]);
        setEntityPos(list[i], pos.x, pos.y + 50, pos.z);
    }
}

const player_list = getPlayerList();
clientMessage('当前世界有' + player_list.length + "个玩家");

clientMessage("俯视角增加5 偏航角增加10");
setLocalPlayerRot(5, 10);

thread(function () {
    clientMessage('在新线程运行');
    for (let i = 0; i < list.length; i++) {
        clientMessage('新线程中:' + getEntityName(list[i]));
    }
}, 1000);

function onCallModuleEvent(args) {
    clientMessage("调用数据:" + args.fun + ' - ' + args.name);
}

function onPlayerBuildBlockEvent(playerId, x, y, z, side) {
    const block = getBlock(x, y, z);
    if (block == null)
        return false;
    const json = string_format('{"type":"form","title":"提示","content":"当前点击了 {} {} {} 方块 {}","buttons":[{"text":"setBlock"},{"text":"fill"},{"text":"destroy"}]}', x, y, z, block.namespace);
    addForm(json, function (index) {
        clientMessage('选择:' + index);
        switch (index) {
            case 0:
                executeCommand(string_format('/setblock {} {} {} grass', x, y, z));
                break;
            case 1:
                executeCommand(string_format('/fill {} {} {} {} {} {} grass', x + 5, y + 5, z + 5, x - 5, y - 5, z - 5));
                break;
            case 2:
                executeCommand(string_format('/fill {} {} {} {} {} {} air 0 destroy', x + 5, y + 5, z + 5, x - 5, y - 5, z - 5));
                break;
        }
    });
}

function onCommandOutputEvent(type, args, value) {
    clientMessage('输出类型:' + type, '输出值:' + value);
    for (let i = 1; i < args.length; i++) {
        clientMessage('type:' + args[i].type, 'key:' + args[i].key);
        const array = args[i].list;
        for (let j = 1; j < array.length; j++) {
            clientMessage('内容:' + array[j]);
        }
    }
    return true;
}

function onPlayerAuthInputEvent(input) {
    const UP = 10
    if ((input.flag & (1 << UP)) != 0){
        clientMessage('当前正在向前移动')
    }
}

function onPlayerInputEvent(input) {
    const JUMP = 8
    if (input.action == JUMP){
        clientMessage('当前正在跳跃')
    }
}

const headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/99.0.4844.74 Safari/537.36 Edg/99.0.1150.55',
    'Accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9'
};
curl_get('http://www.baidu.com', headers, function (result_code, data) {
    clientMessage(result_code, data);
});

thread(function () {
    clientMessage('脚本自动退出');
    exit();
}, 1000 * 10);
```