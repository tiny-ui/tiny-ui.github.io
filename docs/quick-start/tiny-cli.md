---
layout: default
title: Tiny CLI 介绍
parent: 快速开始
nav_order: 1
---

# Tiny CLI 使用介绍
## Tiny CLI 命令集合

```shell
tiny init /* 创建项目 */

tiny dev /* 编译并开启本地服务 */

tiny build /* 构建项目正式产物 */

tiny dep /* 更新依赖 */

tiny clean /* 清理项目缓存 */

tiny -h /* 使用帮助 */

tiny -v /* 查看版本 */
```

## 安装 Tiny CLI
### 基本要求
在使用 Tiny CLI 工具前，你必须：
- 安装 JDK 11 并配置环境变量
- 安装 Node.js & NPM
- 安装 Android SDK
  - 配置好 ANDROID_HOME 环境变量
  - 配置好ANDROID_TOOLS (platform-tools)环境变量

### Tiny CLI 安装

```shell
# 终端执行(需翻墙)
brew tap shouduzhanshi/brew

brew install shouduzhanshi/brew/tinytool
```

### 升级 Tiny CLI
```shell
# 先执行这个
brew tap --force-auto-update shouduzhanshi/brew
brew update
# 然后
brew upgrade tinytool
```

## FAQ
todo 

## Change Log
### v1.0.8.2
- fix:修复热重载Bug.

### v1.0.8.1
功能下线:
- 下线JavaScript工程 HotReload 命令,后续所有工程 run & hotReload 统一使用 "tiny dev"命令

新特性&功能调整:
- 变更 "build" 命令,"tiny build" 命令后续会专注于构建Release产物.
- 新增 "clean" 命令,现在可以通过  "tiny clean" 命令清理工程构建缓存了.
- 新增 "dev" 命令,用于承接老版本"build"命令的工作.
- 新增"dep"命令,现在可以通过dep命令安装dsl依赖.
- 新增"init"命令,替换原有"create"命令
- tiny_tool 改名为 tiny

优化:
- HotReload 性能优化,支持多页面调试.

Fix:
- 修复新建页面 HotReload 失效问题. 感谢王海龙杨继斌同学提供的issues.
