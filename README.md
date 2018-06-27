# X社区 地图翻译 / stripper / Entwatch
---
这是X社区 地图翻译 / Entwatch / stripper mapcfg(地图参数) 或者其他翻译 GIT仓库。

地图翻译/stripper/mapcfg 支持所有类型服务器。

只要对应服务器具备相应地图就会同步本仓库数据，其他服务器不会产生影响。

## 目录说明
---
+ mapcfg      ->地图参数
+ mappool     ->地图池控制系统
+ entwatch    ->神器显示配置
+ ze_mapstext ->ZE地图翻译

## 游戏中自动同步方法
---
1. 更新/添加修改/你想要的 通过创建 [Pull requests](https://github.com/MapTextLang/MapTextLang/pull/new/master).

2. 游戏服务器会每隔24小时 自动检测修改并同步 op / mapper可以输入 !git_update 强行同步

## 地图修改服务器参数/或指令拦截
---

### 地图参数拦截功能

`sm_block_command` 想要拦截参数关键词
`sm_block_command zr_infect_spawntime` 就可以禁止掉地图修改尸变时间

### [用法演示](https://github.com/MapTextLang/MapTextLang/blob/master/mapcfg/ze_grau_a03_4.cfg#L15-L17)
---

默认拦截有关 "STEAM_" 所有关键词
在mapcfg中添加 `mapcommandblock_enable 0` 则不会阻挡地图操作命令（默认 1） 此CVAR安全锁定 只能由配置文件修改

但即使地图有白名单参数 也拒绝 kick ban操作 此屏蔽强制执行

通过 sm_block_command "增加想要的参数命令关键词"

捕捉地图在做什么命令？
使用 `sm_showmapcmd` 开关捕捉 信息输出到控制台

## 翻译文件禁止事项
---
1. 禁止使用特殊字符 如`/` `\` `＂` `“`　等符号
2. 禁止删除引号 `"` 删除括号如`{` `}`．
3. 禁止修改地图主语句, 如: `*** The Train Will Leave in 5 seconds ***`
4. 禁止换行
