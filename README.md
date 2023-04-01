# eslint-demo

## step 0

安装 eslint 包

```bash
$ npm install eslint -D
```

## step 1

初始化配置

```bash
$ npx eslint --init
```

命令行中会一步步让你选择配置项，选择完后也就生成了配置文件

eslint 的默认配置是 `"extends": "eslint:recommended"`，它不会检查任何语法错误（[No rules are enabled by default](https://eslint.org/docs/rules/)），推荐 airbnb 标准或者 [standard 标准](https://github.com/standard/eslint-config-standard)（这种库通常以 eslint-config-xx 命令，我们也会看到一些以 eslint-plugin-react 命名的仓库，可以顾名思义）

不想要某个规则，可以配置 rules，将该条规则 off 掉（如果是 tslint，则需要设置为 false），比如要干掉默认的两个空格缩进：

```
"rules": {
  "indent": ["off"]
}
```

* `"off"` 或 `0` 关闭规则
* `"warn"` 或 `1` 开启规则，使用时报 warn
* `"error"` 或 `2` 开启规则，使用时报 error

## step 2

编辑器需要安装相应的插件，比如 VSCode 需要安装 [VS Code ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)


```bash
# 手动 lint
npm run lint
```

自动 lint，在 VSCode 中的 ESlint 扩展的配置文件中配置：

```
{
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true // eslint 自动 fix
    // "source.fixAll": true // 所有工具都能自动 fix，比如如果 tsconfig.json 配置了 Unreachable code detected，则会自动删除 Unreachable code
  } 
}
```
