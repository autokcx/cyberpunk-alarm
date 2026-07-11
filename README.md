# CyberPunk 闹钟 ⚡

> Kevin's 1st vibe coding app —— 一个赛博朋克风格的**番茄钟 / 专注计时器**,用 [Electron](https://www.electronjs.org/) 打包成 macOS 桌面应用。

计时结束时会用 CS:GO 经典语音台词提醒你("Rush B!"、"The bomb has been planted." …),霓虹配色 + 环形进度条,专治摸鱼。

---

## ✨ 功能

- 🍅 **三种模式**:专注 `25min` · 小憩 `5min` · 长休 `15min`
- ⭕ **环形进度条**:剩余时间一目了然
- 🔊 **CS:GO 语音提醒**:启动、暂停、重置、番茄完成、休息结束各有专属台词
  - 默认用系统语音合成朗读;放入真实 `.mp3` 后自动优先播放(见下方「自定义音效」)
- ⌨️ **空格键**一键启动 / 暂停
- 🔔 完成时弹**系统通知**,并统计已完成的番茄数
- 🎨 霓虹青 / 荧光黄双主题配色,专注/休息自动切换

---

## 🚀 运行方式

### 方式一:直接用打包好的 app(日常推荐)

不需要终端、不需要 Node。用 `npm run package` 打包后,双击生成的
`dist/CyberPunk 闹钟-darwin-arm64/CyberPunk 闹钟.app` 即可。

> 首次打开若提示「无法验证开发者」:右键图标 → **打开** → 再点一次**打开**(自签名应用,只需操作一次)。

### 方式二:开发模式(改代码时用)

```bash
git clone https://github.com/autokcx/cyberpunk-alarm.git
cd cyberpunk-alarm
npm install
npm start
```

---

## 📦 打包成 macOS app

```bash
npm run package
```

产物输出到 `dist/`。(打包产物和 `node_modules` 已通过 `.gitignore` 排除,不进 git。)

---

## 🎧 自定义音效

把真实音频放进 `sounds/`,App 会自动优先播放(覆盖内置语音台词):

| 触发时机 | 文件名 |
|---|---|
| 启动 | `start.mp3` |
| 暂停 | `pause.mp3` |
| 重置 | `reset.mp3` |
| 番茄完成 | `workDone.mp3` |
| 休息结束 | `breakDone.mp3` |

放好文件后重新 `npm run package` 打包即可。没有对应文件时,自动回退到系统语音朗读台词。

---

## 🛠 技术栈

- [Electron](https://www.electronjs.org/) 33 —— 桌面应用外壳
- 原生 HTML / CSS / JavaScript —— 界面与逻辑(单文件 `index.html`)
- [Rajdhani](https://fonts.google.com/specimen/Rajdhani) 字体 —— 赛博朋克数字风
- Web Speech API + Web Audio API —— 语音台词与合成音效

## 📄 许可

MIT © Kevin
