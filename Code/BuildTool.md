# 建筑工具

```javascript
/**
 * @author: WhiteWallTeam
 * @date: 2024.10.12
 * @description: 建筑工具
 */

const Config = {
        DATA_PATH: getResource() + '/data',
        MODULE_BUILD_TOOL: false,
        CLICK_COPY: false,
        EXCLUDE_AIR: true,
        POS_DATA: {x: 0, y: 0, z: 0},
        BUILD_TASKS: [],
        BUILD_TASKS_SPEED: 5,
        CURRENT_TICK: 0,
        SAVE_TICK: 0,
    };

File.mkdirs(Config.DATA_PATH);

export function onCallModuleEvent(args) {
    const { fun, value } = args;

    if (fun === 'script_build_tool' && isInGame()) {
        Config.MODULE_BUILD_TOOL = value;
        addCustomArrayList('script_build_tool', '建筑工具', '建筑工具', value);
        clientMessage(`§b[建筑工具] §${value ? 'e已经启用，请点击地面打开菜单' : 'c已经禁用'}`);
    }
}

// 状态转字符串
function bool2str(bool) {
    return bool ? '§2已打开' : '§c已关闭';
}

// 移除区块数据
function removeBlocksData(name) {
    try {
        File.delete(`${Config.DATA_PATH}/${name}`);
    } catch (error) {
        clientMessage(`Failed to delete block data: ${error}`);
    }
}

// 保存区块数据
function saveBlocksData(name, blocks) {
    const json = JSON.stringify(blocks);
    try {
        File.write(`${Config.DATA_PATH}/${name}.json`, json);
    } catch (error) {
        clientMessage(`Failed to save block data: ${error}`);
    }
}

// 加载区块数据
function loadBlocksData(name) {
    try {
        const blocks = File.read(`${Config.DATA_PATH}/${name}`);
        return JSON.parse(blocks);
    } catch (error) {
        clientMessage(`Failed to load block data: ${error}`);
        return null;
    }
}

// 获取区块数据
function getChunkBlocks(x1, y1, z1, x2, y2, z2) {
    const sx = Math.min(x1, x2);
    const sy = Math.min(y1, y2);
    const sz = Math.min(z1, z2);
    const ex = Math.max(x1, x2);
    const ey = Math.max(y1, y2);
    const ez = Math.max(z1, z2);
    const blocks = [];

    for (let hx = sx; hx <= ex; hx++) {
        for (let hy = sy; hy <= ey; hy++) {
            for (let hz = sz; hz <= ez; hz++) {
                const block = getBlock(hx, hy, hz);
                if (Config.EXCLUDE_AIR && (block.id === 0 || block.namespace === 'minecraft:air')) {
                    continue;
                }
                blocks.push({
                    name: block.namespace,
                    aux: block.aux,
                    x: hx - sx,
                    y: hy - sy,
                    z: hz - sz
                });
            }
        }
    }
    return blocks;
}

// 显示建筑菜单
function showListMenu() {
    const menu = {
        type: 'form',
        title: '建筑列表',
        content: '请选择需要粘贴的建筑',
        buttons: []
    };

    const files = File.list(Config.DATA_PATH);

    // 如果没有文件，添加“暂无数据”按钮
    if (!files || files.length === 0) {
        menu.buttons.push({ text: '暂无数据' });
    } else {
        // 处理每个文件
        files.forEach(file => {
            menu.buttons.push({
                text: file.name.replace('.json', ''),
                image: { type: 'path', data: 'textures/ui/default_world.png' }
            });
        });
    }

    addForm(JSON.stringify(menu), function (index) {
        if (index >= 0 && files && files.length > index) {
            const blocks = loadBlocksData(files[index].name);
            clientMessage(blocks ? '读取成功' : '读取失败');
            if (blocks) Config.BUILD_TASKS = blocks;
        }
    });
}

// 显示移除菜单
function showRemoveListMenu() {
    const menu = {
        type: 'form',
        title: '建筑列表',
        content: '请选择需要移除的建筑',
        buttons: []
    };

    const files = File.list(Config.DATA_PATH);

    // 检查是否存在文件，否则显示“暂无数据”按钮
    if (!files || files.length === 0) {
        menu.buttons.push({ text: '暂无数据' });
    } else {
        files.forEach(file => {
            menu.buttons.push({
                text: file.name.replace('.json', ''),
                image: { type: 'path', data: 'textures/ui/default_world.png' }
            });
        });
    }

    addForm(JSON.stringify(menu), function (index) {
        if (index >= 0 && files && files.length > index) {
            removeBlocksData(files[index].name);
            clientMessage('移除成功');
        }
    });
}

// 显示坐标菜单
function showPosMenu() {
    const menu = {
        type: "custom_form",
        title: "§b坐标复制",
        content: [
            {
                type: "input",
                text: "保存名称"
            },
            {
                type: "input",
                text: "开始坐标",
                placeholder: "例如 100,10,100"
            },
            {
                type: "input",
                text: "结束坐标",
                placeholder: "例如 100,10,100"
            }
        ]
    };

    addForm(JSON.stringify(menu), function (name, start_pos, end_pos) {
        if (name && start_pos && end_pos) {
            const s = start_pos.split(',').map(Number);
            const e = end_pos.split(',').map(Number);

            if (
                name.trim().length > 0 &&
                s.length === 3 && e.length === 3 &&
                s.every(num => !isNaN(num)) &&
                e.every(num => !isNaN(num))
            ) {
                const blocks = getChunkBlocks(s[0], s[1], s[2], e[0], e[1], e[2]);
                saveBlocksData(name, blocks);
                clientMessage('保存成功');
            } else {
                clientMessage('输入错误，请输入有效的坐标格式');
            }
        } else {
            clientMessage('所有字段均为必填');
        }
    });
}

function bool2jsonValue(bool) {
    return bool ? 'true' : 'false';
}

//显示选项菜单
function showSettingMenu() {
    const value = bool2jsonValue(Config.EXCLUDE_AIR)
    addForm(`{"type":"custom_form","title":"§b修改选项","content":[{"type":"slider","text":"建造速度","min":1,"max":20,"step":1,"default":${Config.BUILD_TASKS_SPEED}},{"type":"toggle","text":"排除空气","default":${value}}]}`, function (speed, toggle) {
        if (speed != null && speed > 0) {
            Config.BUILD_TASKS_SPEED = speed;
            Config.EXCLUDE_AIR = toggle;
            clientMessage('§e保存成功');
        }
    }, function () {
        clientMessage('§e没有选择保存');
    })
}

//显示主菜单
function showMainMenu() {
    const menu = `{
        "type": "form",
        "title": "§a建筑菜单",
        "content": "§e请选择需要执行的操作",
        "buttons": [
            {
                "text": "§b两点复制 §e(点击两个位置复制)",
                "image": {
                    "type": "path",
                    "data": "textures/ui/anvil_icon.png"
                }
            },
            {
                "text": "§b坐标复制 §e(输入具体坐标复制)",
                "image": {
                    "type": "path",
                    "data": "textures/ui/anvil_icon.png"
                }
            },
            {
                "text": "§b选择粘贴",
                "image": {
                    "type": "path",
                    "data": "textures/ui/copy.png"
                }
            },
            {
                "text": "§b移除建筑",
                "image": {
                    "type": "path",
                    "data": "textures/ui/book_trash_default.png"
                }
            },
            {
                "text": "§b修改选项",
                "image": {
                    "type": "path",
                    "data": "textures/ui/dev_glyph.png"
                }
            },
            {
                "text": "§c退出工具",
                "image": {
                    "type": "path",
                    "data": "textures/ui/crossout.png"
                }
            }
        ]
    }`;
    addForm(menu, function (index) {
        switch (index) {
            case 0:
                Config.CLICK_COPY = true;
                Config.POS_DATA.x = 0;
                Config.POS_DATA.y = 0;
                Config.POS_DATA.z = 0;
                clientMessage('§b两点复制 ' + bool2str(Config.CLICK_COPY));
                break
            case 1:
                showPosMenu();
                break
            case 2:
                showListMenu();
                break
            case 3:
                showRemoveListMenu();
                break
            case 4:
                showSettingMenu();
                break
            case 5:
                Config.MODULE_BUILD_TOOL = false;
                addCustomArrayList('script_build_tool', '建筑工具', '建筑工具', false)
                clientMessage('§b[建筑工具] §c已经禁用');
                break
        }
    })
}

export function onPlayerBuildBlockEvent(playerId, x, y, z, side) {
    if (!Config.MODULE_BUILD_TOOL) {
        return false;
    }
    if (Config.SAVE_TICK === Config.CURRENT_TICK) {
        return false;
    }
    Config.SAVE_TICK = Config.CURRENT_TICK;
    if (Config.CLICK_COPY) {
        if (Config.POS_DATA.x === 0 && Config.POS_DATA.y === 0 && Config.POS_DATA.z === 0) {
            Config.POS_DATA.x = x;
            Config.POS_DATA.y = y;
            Config.POS_DATA.z = z;
            showTipMessage('§e已经选择起点，请选择终点')
        } else {
            const blocks = getChunkBlocks(Config.POS_DATA.x, Config.POS_DATA.y, Config.POS_DATA.z, x, y, z);
            const date = new Date();
            const time = date.getTime().toString();
            addForm(`{"type":"custom_form","title":"输入保存名称","content":[{"type":"input","text":"名称:","default":"${time}"}]}`, function (name) {
                if (typeof name == 'string' && name.length > 0) {
                    saveBlocksData(name, blocks);
                    clientMessage('§e保存成功');
                } else {
                    clientMessage('§c未保存');
                }
            }, function () {
                clientMessage('§c未选择保存');
            });
            Config.POS_DATA.x = 0;
            Config.POS_DATA.y = 0;
            Config.POS_DATA.z = 0;
            Config.CLICK_COPY = false
        }
        return false;
    }
    if (Config.BUILD_TASKS.length === 0) {
        Config.POS_DATA.x = x;
        Config.POS_DATA.y = y;
        Config.POS_DATA.z = z;
    }
    showMainMenu();
}

export function onTickEvent() {
    if (!Config.MODULE_BUILD_TOOL) {
        return false;
    }
    Config.CURRENT_TICK++;
    if (Config.BUILD_TASKS.length === 0) {
        return;
    }

    const maxTasks = Math.min(Config.BUILD_TASKS.length, Config.BUILD_TASKS_SPEED);

    for (let i = 0; i < maxTasks; i++) {
        const task = Config.BUILD_TASKS.shift(); // 从队列头部取出任务

        if (typeof task === 'object') {
            const {x, y, z, name, aux} = task;
            const {x: baseX, y: baseY, z: baseZ} = Config.POS_DATA;
            const command = `setblock ${baseX + x} ${baseY + y} ${baseZ + z} ${name} ${aux}`;
            executeCommand(command);
        } else {
            break;
        }
    }
    showTipMessage(`§e当前任务剩余: ${Config.BUILD_TASKS.length}`);
}

export function onCommandOutputEvent(type, args, value) {
    if (!Config.MODULE_BUILD_TOOL) {
        return false;
    }
    return Config.BUILD_TASKS.length > 0;
}
```