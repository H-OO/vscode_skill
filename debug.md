# 调试模式

进入调试模式 → 点击添加配置

进入到`launch.json`文件，选择启动方式

## 修改 launch.json 文件

```json
// --- launch.json
{
  // 使用 IntelliSense 了解相关属性。 
  // 悬停以查看现有属性的描述。
  // 欲了解更多信息，请访问: https://go.microsoft.com/fwlink/?linkid=830387
  "version": "0.2.0",
  "configurations": [
    // node 启动
    {
      "type": "node",
      "request": "launch",
      "name": "Launch Program",
      "program": "${workspaceFolder}/index.js"
    },
    // npm 启动
    {
      "type": "node",
      "request": "launch",
      "name": "Launch via NPM",
      "runtimeExecutable": "npm",
      "runtimeArgs": [
        "run-script", // run
        "debug" // 对应package.json中scripts中的debug
      ],
      "port": 9229
    },
  ]
}
```

## 修改 package.json

```json
{
  "name": "t",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "dev": "node ./index.js",
    "debug": "node --inspect-brk=9229 ./index.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```


