<!--
 * @Author: 雪风@mud.ren
 * @Date: 2022-03-25 13:28:42
 * @LastEditTime: 2022-03-25 13:40:35
 * @LastEditors: 雪风
 * @Description: mudcore框架template
 *  https://bbs.mud.ren
-->
## MUDCORE游戏开发示例

如果你是使用mudcore框架全新开发MUD游戏，可参考此示例模版。框架使用说明文档：https://bbs.mud.ren/threads/66

### 项目安装

点击项目上的 [Use this template](https://github.com/mudcore/demo/generate) 生成项目到自己的仓库，然后使用以下指令clone代码：

```bash
# 下载代码
git clone --recurse-submodules <你的项目地址>
```

如果你已经克隆了项目但忘记了 `--recurse-submodules`，那么可以运行 `git submodule update --init` 将 `git submodule init` 和 `git submodule update` 合并成一步。如果还要初始化、抓取并检出任何嵌套的子模块， 请使用简明的 `git submodule update --init --recursive`。

如果需要保持框架为最新版，请进入项目目录后运行以下指令：

```bash
# 更新框架
git submodule update --remote
```

### 启动游戏

    driver config.cfg

> 项目提供了二个配置文件：

* config.cfg - 精简版运行时配置文件
* config.ini - 完整版运行时配置文件

### 目录说明

目录|说明
-|-
data|游戏存档目录，包括游戏配置文件示例config.example
include|游戏代码头文件目录
log|游戏日志目录
system|游戏系统文件目录
mudcore|MUDCORE框架目录，请勿修改其中代码
www|websocket HTTP网页代码，包括2个版本
.vscode|Visual Studio Code 配置目录，方便开发调试

其中 mudcore 目录为引入的框架子模块，不要改动其中的任何代码，其它游戏目录为开发者自己定义的，可根据需要调整。

### 关于环境配置

因为推荐使用git管理代码，有一些核心配置（如数据库密码）为了安全不建议直接写在代码中，MUDCORE 推荐的做法是在`/data/`目录中新建一个`.env`文件，重要配置在这里定义，在游戏中使用`config`或`env`函数读取或写入。此文件不会提交到仓库中，具体可参考`.env.example`文件。
