# RPC通讯

```javascript

function hexToBytes(hex) {
    if (hex.length % 2 !== 0) {
        throw new Error("Hex string must have an even length");
    }

    const bytes = new Uint8Array(hex.length / 2);
    for (let i = 0; i < hex.length; i += 2) {
        bytes[i / 2] = parseInt(hex.substr(i, 2), 16);
    }
    return bytes;
}

function bytesToHex(bytes) {
    return Array.from(bytes)
        .map(byte => byte.toString(16).padStart(2, '0'))
        .join('');
}

function onPyRpcSendEvent(id,binary){
    clientMessage(bytesToHex(binary))
}

//??c? ??playerId?-4294967295?message?升10级?pType?hasCount??

const bytes = hexToBytes('93c40163920984c408706c617965724964c40b2d34323934393637323935c4076d657373616765c408e58d873130e7baa7c405705479706501c408686173436f756e74c3c0')
const binary = bytes.buffer

sendRpc(98247598,binary)

```