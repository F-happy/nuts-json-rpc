# nuts-json-rpc
[![npm](https://img.shields.io/npm/v/nuts-json-rpc.svg?style=flat-square)](https://www.npmjs.com/package/nuts-json-rpc)
[![npm](https://img.shields.io/npm/l/nuts-json-rpc.svg?style=flat-square)](https://www.npmjs.com/package/nuts-json-rpc)

这是一个遵循 json-rpc2.0 协议的 node 客户端

## 安装方法：
```
$ npm install --save-dev nuts-json-rpc
```
## 使用：
```javascript
const {createClient, NutsJsonRPC} = require('nuts-json-rpc');

(async () => {
    try {
        this.host = `${youhost}/rpc/`;
        const client = createClient(`${this.host}${youurl}`, {'Authorization': 'uid'});
        let value = await client.call('youmethod', youargs);
        console.log(value);
    } catch (err) {
        console.log(err);
    }
})();

// or
(async () => {
    try {
        this.host = `${youhost}/rpc/`;
        const client = new NutsJsonRPC(`${this.host}${youurl}`, port, {'Authorization': 'uid'});
        let value = await client.call('youmethod', youargs);
        console.log(value);
    } catch (err) {
        console.log(err);
    }
})();
```

## API:

### call(method, params)
> 发起一个正常的rpc请求

### notify(method, params)
> 发起一个rpc通知

### printRequestBody(function)
> 打印请求体

```javascript
const client = new NutsJsonRPC(`${this.host}${url}`, 80);
client.printRequestBody(console.log);
```