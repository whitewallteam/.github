# RPC通讯

```javascript
//??c? ??playerId?-4294967295?message?升10级?pType?hasCount??
sendRpc(98247598,"93c40163920984c408706c617965724964c40b2d34323934393637323935c4076d657373616765c408e58d873130e7baa7c405705479706501c408686173436f756e74c3c0")

function hexToString(hex) {
    let str = '';
    for (let i = 0; i < hex.length; i += 2) {
        str += String.fromCharCode(parseInt(hex.substr(i, 2), 16));
    }
    return str;
}

function stringToHex(str) {
    let hex = '';
    for (let i = 0; i < str.length; i++) {
        hex += str.charCodeAt(i).toString(16);
    }
    return hex;
}

function onPyRpcSendEvent(id,str){
    clientMessage(hexToString(str))
}
```