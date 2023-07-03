

# Debug
```shell
ts-node --esm --experimental-specifier-resolution=node -T src/node/index.ts vitepress
```

* 由于使用的是 esm 语法，所以需要以 esm 来进行编译
* -T 是忽略所有 ts 错误
* `--experimental-specifier-resolution=node` 是由于 ts-node --esm 时候无法自动补齐 file extension 具体见 https://github.com/TypeStrong/ts-node/discussions/1781 
* 后还需要根据报错进行修改。由于很多包是 cmjs ，所以 import 的时候会提示例如 `The requested module 'picocolors' is a CommonJS module, which may not support all module.exports as named exports.` ，只需要将其改为 default 引入再进行解构就好了