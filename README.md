# MOMessage

《心灵终结 3.3.6》（Mental Omega 3.3.6）的客户端界面插件。

把原本挤在角落、容易被忽略的消息改成更醒目、更易用的形式，并内置支援技能侧栏。

## 功能

**1. 战役 / 聊天消息居中显示**
- 消息框居中或贴底显示，可配置行数、宽度、字体、底板透明度
- 打字机效果

**2. 雷达事件文字化**
- 基地遭到袭击、矿车遭到袭击、发现敌军、空投区域、主要/次要目标等
- 以文字形式出现在左下角提示区
- **点击提示文字可把视角跳到事件地点**

**3. 左下角操作与战斗提示**
- 汇总当前操作反馈与战斗提示，避免刷屏丢失
- 可配置行数、宽度、字体、位置

**4. 电力与生产信息行**
- 常驻显示当前电力（产出 / 消耗 / 余量）
- 建造栏生产进度按 4 行显示（建筑 / 防御 / 步兵 / 装甲）

**5. 支援技能侧栏（内置）**
- 从 MOExperience 移植的 SWS 侧栏，显示支援技能图标
- 已合并进本插件，不再需要额外的 `MOSWSidebar.dll`
- 侧栏配置沿用 `MOExperience.ini` 的 `[SWSidebar]` 节

## 安装

1. 需要先安装 [Syringe](https://github.com/Ares-Developers/Syringe)（心灵终结自带）。
2. 把以下三个文件放进游戏根目录（`gamemd.exe` 所在目录）：
   - `MOMessage.dll`
   - `MOMessage.dll.inj`
   - `MOMessage.ini`
3. 启动游戏即可。

> 从旧版升级：如果之前装过 `MOSWSidebar.dll`，请删除它的 `.dll` / `.dll.inj` / `.ini`，否则会与本插件争用同一个钩子地址。

## 卸载

删除上面三个文件，恢复原版界面。

## 配置

界面开关在 `MOMessage.ini`，常用项：

```ini
[MsgText]
Enable=1            ; 0 = 完全关闭
CampEnable=1        ; 战役/聊天消息
CampBottom=1        ; 1 = 贴底居中
CampBottomMargin=150
MaxLines=8
MaxWidth=550
FontFace=msyh.ttc
BoardOpacity=30     ; 底板不透明度 0~100
CampAnim=1          ; 打字机效果

HintShow=1          ; 左下角提示
HintRadarShow=1     ; 雷达事件文字化
HintRadarClick=1    ; 点击提示跳转视角
HintMaxLines=8
HintBottom=150

[MsgRadar]
Name3=基地遭到袭击!
Name4=矿车遭到袭击!
Name5=发现敌军!
```

支援侧栏配置在 `MOExperience.ini` 的 `[SWSBar]` / `[SWSidebar]` 节。

## 说明

- 纯客户端插件：只在本地绘制与读取，不修改游戏模拟数据、不发送指令。
- 联机时对方无需安装。
- 点击提示跳转只改变本机视角。

## 兼容

- 心灵终结 3.3.6（gamemd + Syringe 0.7.3 + Ares 3.0p1）
- 理论兼容原版尤里的复仇 1.001，但未做完整测试
