## MUDCORE游戏开发示例

如果你是使用mudcore框架全新开发MUD游戏，可参考此示例模版。框架使用说明文档：https://bbs.mud.ren/threads/66

### 项目安装

```bash
# 下载示例项目
git clone --recurse-submodules https://github.com/mudcore/demo.git
# 更新mudcore框架
git submodule update --remote
```

### 启动游戏

    driver config.ini

### 目录说明

目录|说明
-|-
data|游戏存档目录，包括游戏配置文件示例config.example
include|游戏代码头文件目录
log|游戏日志目录
system|游戏系统文件目录
mudcore|MUDCORE框架目录
www|websocket网站代码

其中 mudcore 目录为引入的框架子模块，不要改动其中的任何代码，其它游戏目录为开发者自己定义的，可根据需要调整。

### 关于环境配置

因为推荐使用git管理代码，有一些核心配置（如数据库密码）为了安全不建议直接写在代码中，MUDCORE 推荐的做法是在`/data/`目录中新建一个`config`文件，重要配置在这里定义，在游戏中使用`config`或`env`函数读取或写入。此文件不会提交到仓库中，具体可参考`config.example`文件。
