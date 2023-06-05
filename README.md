<!--
 * @Author: 雪风@mud.ren
 * @Date: 2022-03-25 13:28:42
 * @LastEditTime: 2022-06-14 16:46:35
 * @LastEditors: 雪风
 * @Description: mudcore框架template
 *  https://bbs.mud.ren
-->
## MUDCORE游戏开发示例

如果你是使用mudcore框架全新开发MUD游戏，可参考此示例模版。框架使用说明文档：https://bbs.mud.ren/threads/66

### 项目安装

点击项目上的 [Use this template](https://github.com/mudcore/mud/generate) 生成项目到自己的仓库，然后使用以下指令clone代码：

```bash
# 下载代码
git clone --recurse-submodules <你的项目地址>
```

如果你已经克隆了项目但忘记了 `--recurse-submodules`，那么可以在项目根目录中运行以下指令更新子模块：

```bash
# 更新子模块
git submodule update --init --recursive
```

如果需要保持框架为最新版，请在项目根目录中运行以下指令：

```bash
# 更新框架
git submodule update --remote
```

### 启动游戏

Ubuntu系统下直接运行以下指令或使用`run.sh`脚本启动游戏

    driver config.cfg

> 项目配置文件：

* config.cfg - 精简版运行时配置文件

如需完整版运行时配置文件请参考mudcore框架目录中的`config.example.ini`，另外`config.mini.ini`也值得参考。

如果你还没有编译驱动，可以先运行`build.sh`自动下载编译。

### 目录说明

目录|说明
-|-
.vscode|Visual Studio Code 配置目录，方便开发调试
data|游戏存档目录，包括游戏配置文件示例.env.example
include|游戏代码头文件目录
log|游戏日志目录
mudcore|MUDCORE框架子模块目录，请勿修改其中代码
system|游戏系统文件目录
www|websocket HTTP网页子模块目录，包括2个版本可切换

其中 mudcore 目录为引入的框架子模块，不要改动其中的任何代码，使用帮助见`mudcore/README.md`，其它游戏目录为开发者自己定义的，可根据需要自由调整。

项目其它目录结构建议配置：

目录|说明
-|-
config|游戏各种特色设置配置文件目录，注意不得保存敏感数据
cmds|游戏动作指令目录
daemons|游戏守护进程目录，推荐放在system目录下
docs|游戏文档文件目录
inherit|必须继承使用的功能模块文件目录
obj|实体对象目录，继承标准对象使用
std|标准对象目录，具体对象继承使用
verbs|游戏谓词指令目录
world|游戏世界环境目录

### 关于环境配置

因为推荐使用git管理代码，有一些核心配置（如数据库密码）为了安全不建议直接写在代码中，MUDCORE 推荐的做法是在`/data/`目录中新建一个`.env`文件，重要配置在这里定义，在游戏中使用`env()`函数读取或写入。此文件不会提交到仓库中，具体可参考`.env.example`文件。
