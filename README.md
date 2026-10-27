# bionicreader 桌面版

**Windows 免安装版 · 双击即用的仿生阅读器**

导入本地 EPUB / TXT / PDF，用**仿生阅读（Bionic Reading）**方式重新排版，
针对 ADHD 阅读时的跳行、走神、回读问题设计。

不用装 Python，不用起本地服务，不用敲任何命令 —— 下载、双击、开始读。

---

## 立即下载

### 推荐：免安装单文件版

### ⬇️ [BionicReader-1.2.0-portable.exe](https://github.com/nsnd3000-dotcom/bionic-reader-desktop/releases/latest/download/BionicReader-1.2.0-portable.exe)

约 81 MB ｜ Windows 10 / 11 · 64 位 ｜ 不写注册表 ｜ 删掉文件即卸载

### 备选：绿色压缩包

### ⬇️ [BionicReader-1.2.0-win64.zip](https://github.com/nsnd3000-dotcom/bionic-reader-desktop/releases/latest/download/BionicReader-1.2.0-win64.zip)

约 116 MB ｜ 解压后双击里面的 `Bionic Reader.exe` ｜ 启动比单文件版更快，适合放 U 盘

> 打不开单文件版就换这个，两个版本功能完全一样。
> 历史版本见 [Releases](https://github.com/nsnd3000-dotcom/bionic-reader-desktop/releases)。

---

## 使用方法

**第一步** 点上面的链接下载 `BionicReader-1.2.0-portable.exe`。

**第二步** 双击它。

- 单文件版第一次启动要先自解压到临时目录，**等 5～10 秒**，之后启动就快了。
- 如果弹出蓝色窗口「Windows 已保护你的电脑」：点 **更多信息 → 仍要运行**。
  （exe 没有购买代码签名证书，SmartScreen 对没下载量的新软件都会这样提示，属正常现象。）

**第三步** 把书拖进窗口，或者点中间那个按钮选文件。EPUB / TXT / PDF 都行。

读完不需要退出登录、不需要联网，**全程离线**。

### 快捷键

| 键 | 作用 |
|---|---|
| `B` | 开 / 关仿生阅读加粗 |
| `P` | 开 / 关设置面板 |
| `S` | 开 / 关目录 |
| `N` | 打开「笔记」页签（所有高亮与批注） |
| `T` | 切换主题（浅色 / 深色 / 护眼） |
| `H` | 回到首页 / 换一本书 |

### 阅读数据存在哪

```
%APPDATA%\Bionic Reader
```

阅读进度、荧光笔高亮、笔记批注都保存在这里，全在本地，**不联网、不上传**。
想彻底卸载：删掉 exe，再删掉上面那个文件夹即可。

---

## 功能

- **仿生阅读加粗** —— 词首加粗比例、强度、跳过短词阈值都可调，长按 `B` 一键对比效果
- **荧光笔高亮** —— 5 种颜色，划过的段落下次打开还在原位
- **笔记批注** —— 高亮随手写备注，侧栏「笔记」页签集中管理，点一下跳回原文位置
- **排版全可调** —— 主题、字体、字号、行距、字距、页宽、对齐方式
- **EPUB 目录解析** —— 多级目录、按目录切章、章节跳转、进度记忆
- **PDF 原版式阅读** —— 保留原书版式，不重排
- **完全离线** —— 内置 JSZip 与 PDF.js，不请求任何 CDN

---

## 系统要求

- Windows 10 / 11（64 位）
- 不需要安装 Python、.NET、Node.js 或任何运行时
- 不需要管理员权限

---

## 常见问题

**双击了，什么都没发生？**
1. 看一眼 exe 同目录有没有生成 `bionic-startup.log`。
   有日志 = 程序启动了但窗口有问题，把日志内容发个 issue。
   没日志 = 系统层面没让它跑起来，大概率被杀软拦了。
2. 换 **绿色压缩包** 版本试试，两个版本内核一样，只是启动方式不同。
3. 别把 exe 放在只读目录、网络盘、OneDrive 同步目录里 —— Chromium 在这些位置会初始化失败。
   放到 `D:\BionicReader\` 这类普通本地目录最稳。
4. 杀毒软件可能误报（未签名 exe 的常见情况），把它加进白名单即可。

**提示「Bionic Reader 已经在运行」？**
说明后台已经有一个进程（可能被最小化了）。打开任务管理器，结束 `Bionic Reader.exe`，再重新打开。

**打开是空白页？**
先在设置里切一下主题试试；仍有问题请提 issue，并附上 exe 同目录的 `bionic-startup.log`。

**为什么这么大（80 MB）？**
这是 Electron 打包的程序，体积里绝大部分是 Chromium 运行时 —— 换来的是「不用装任何东西、双击就能跑」。

**和网页版有什么区别？**
网页版是单个 `index.html`，需要用浏览器打开并起一个本地服务（否则进度存不住）；
桌面版把这些都包好了，双击即用。**两边的阅读数据不互通。**

---

## 关于

- 源码与开发文档：[nsnd3000-dotcom/bionic-reader](https://github.com/nsnd3000-dotcom/bionic-reader)
- 本仓库只存放 Windows 桌面版的打包产物（源码不在本仓库）
- 许可证：MIT
