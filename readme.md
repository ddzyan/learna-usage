# lerna 使用demo

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

