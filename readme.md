# lerna 使用demo

## 使用教程
```shell
git init lerna-usage && cd lerna-usage

# lerna初始化
lerna init

# 创建三个新的package (feu-app、feu-ui、feu-tools)
lerna create feu-app && lerna create feu-ui && lerna create feu-tools

# 添加第三方依赖包"chalk"到feu-ui的开发依赖库中
lerna add chalk --scope=feu-ui --dev

# 添加本地包feu-tools到feu-ui的依赖库中
lerna add feu-tools --scope=feu-ui

# 添加本地包feu-tools到feu-app的依赖库中
lerna add feu-tools --scope=feu-app

# 添加本地包feu-ui到feu-app的依赖库中
lerna add feu-ui --scope=feu-app

# 使用 lerna 引导程序安装所有依赖包
lerna bootstrap
```

本地包添加的时候，lerna命令会通过symlink的方式关联过去，可以理解为创建了一个快捷方式，这个对本地开发非常有用。

## 常见指令
```shell
# 安装
npm install --global lerna

# 初始化
lerna init

# 安装所有依赖项目并链接任何交叉依赖
lerna bootstrap

# 将本地路径 <pathToRepo> 中的软件包导入（import） packages/<directory-name> 中并提交 commit
lerna import <pathToPepo> 

# 创建新的package
lerna create feu-app

# 添加本地包feu-tools到feu-ui的依赖库
lerna add feu-tools --scope=feu-ui

# 添加远程依赖包"chalk"到feu-ui的开发依赖库中
lerna add chalk --scope=feu-ui --dev

# 模块包编译
lerna build

# 查看有哪些更新的packages
lerna changed

# 发包
lerna publish

# 清楚所有包下面的 node_modules
lerna clean

# 删除指定包下的依赖
lerna clean --scope=feu-ui

# 在包含该脚本命令的每个package内部执行npm script脚本命令
lerna run
```