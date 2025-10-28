# TS3AudioBot-Pusher

一个油猴 (Tampermonkey) 脚本，它在 Bilibili 视频页面添加控制按钮，让你能一键将视频（或合集/分P）推送到你的 [TS3AudioBot](https://github.com/Splamy/TS3AudioBot) 进行播放。

## ✨ 功能特性

* **一键推送**: 在视频播放器右侧添加“直接播放”和“加入队列”按钮。
* **智能检测**: 自动检测当前视频是否为**多P**或**合集**视频。
* **批量操作**: 当检测到多P或合集时，额外显示“批量播放”和“批量添加”按钮。
* **支持分P**: 自动获取当前P数，实现精准播放 (`bv-p`)。
* **批量指令**: 自动根据规则发送正确的批量指令：
    * **合集**: 优先使用 `vall` / `addall` 指令。
    * **仅分P**: 使用 `v` / `add` 指令 + `BV号-a`。
* **图形化配置**: 通过油猴菜单进行设置，无需修改代码。

## 🧩 先决条件

在使用此脚本前，你 **必须** 满足以下条件：

1.  一个正常运行的 **TS3AudioBot** 实例。
2.  Bot 端已成功安装并加载 [**TS3AudioBot-bilibili**](https://github.com/HuxiaoRoar/TS3AudioBot-bilibili) 插件。
3.  你的浏览器安装了 [**Tampermonkey**](https://www.tampermonkey.net/) (油猴) 或同类用户脚本管理器。

## 🚀 安装

1.  确保你已满足上述所有“先决条件”。
2.  点击下面的链接进行安装：
    * **[Gist 安装链接](https://gist.github.com/HuxiaoRoar/84906305e947b6a60b43e76b62031369/raw/a7bf506690618cb450eff13ad8ae352663cbbb3c/TS3AudioBot-Pusher.user.js)** (推荐：可自动更新)
    * *或* **[GreasyFork 安装](https://greasyfork.org/zh-CN/scripts/553983-b%E7%AB%99%E9%9F%B3%E9%A2%91%E4%B8%80%E9%94%AE%E6%8E%A8%E9%80%81-ts3audiobot)**
    * *或* **[点击此处从本仓库安装](https://github.com/HuxiaoRoar/TS3AudioBot-Pusher/blob/main/TS3AudioBot-Pusher.user.js)**

## ⚙️ 配置

安装脚本后，你需要配置它才能连接到你的机器人：

1.  打开**任意一个 Bilibili 视频页面** (例如 `https://www.bilibili.com/video/BV1ZuGgzgENF`)。
2.  点击浏览器右上角的 **Tampermonkey (油猴) 扩展图标**。
3.  在弹出的菜单中，找到本脚本的名称，并点击 **"⚙️ 设置"**。
4.  在弹出的配置面板中：
    * **机器人地址**: 填入你的 TS3AudioBot API 地址 (例如: `http://192.168.50.12:58913`)。
    * **机器人序号**: 填入你要控制的机器人序号 (通常只有一个，是 `0`)。
5.  点击 **"保存"**。

## ▶️ 使用说明

配置完成后，刷新 B 站视频页面，你将在视频播放器右侧看到操作按钮。

### 第一行按钮 (单个视频)

* **直接播放**: 立即清空当前队列，并播放当前视频 (如果是分P视频，则播放你正在看的那一P)。
* **加入队列**: 将当前视频 (或当前P) 添加到播放队列的末尾。

### 第二行按钮 (批量操作)

* 此行按钮 **仅在检测到合集或多P视频时** 才会出现。
* **批量播放**: 播放**整个合集** (合集优先) 或**所有分P**。
* **批量添加**: 将**整个合集**或**所有分P**添加到播放队列的末尾。

## 🤝 相关项目

* [**TS3AudioBot**](https://github.com/Splamy/TS3AudioBot): 机器人本体。
* [**TS3AudioBot-bilibili**](https://github.com/HuxiaoRoar/TS3AudioBot-bilibili): 机器人端的B站解析插件 (本脚本的依赖)。
