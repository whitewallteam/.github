# 快照创建与使用

```javascript

// 定义快照代码
// 也可以读取本地文件
const snapshot = `
// 定义变量
const Module = {
    name: 'Snapshot',
    version: '1.0.0',
    description: 'Snapshot created by Snapshot.md',
    author: 'Snapshot',
}

// 声明资源路径变量
// 只能声明变量，不能调用API函数
let resourcePath

// 定义事件回调函数
function onCallModuleEvent(args) {
    console.log('Call Module Event', args)
}

// 自定义入口代码
function main() {
    // 获取资源路径
    // 需要在这里调用API函数，否则无法使用
    resourcePath = getResource('data')
    console.log('Resource Path:', resourcePath)
}
`
try {
    const bin = createSnapshot(snapshot)

    const path = getResource('data')

    File.writeBinary(`${path}/snapshot.bin`, bin)

    const snapshotBin = File.readBinary(`${path}/snapshot.bin`)

    loadSnapshot(snapshotBin)
} catch (e) {
    console.log(e)
}

```