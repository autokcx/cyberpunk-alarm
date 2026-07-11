# CSGO Focus Timer ⚡

> Kevin's 1st vibe coding app —— 一个赛博朋克风格的**番茄钟 / 专注计时器**,用 [Electron](https://www.electronjs.org/) 打包成 macOS 桌面应用。

计时结束时会用 CS:GO 经典语音台词提醒你("The bomb has been planted."、"Terrorists Win!" …),霓虹配色 + C4 引信进度条,专治摸鱼。

---

## ✨ 功能

- 🍅 **两种模式**:专注(可选 `5 / 15 / 25 / 35 / 45` 分钟)· 休息(可选 `5 / 10 / 15` 分钟)
- 💣 **C4 引信进度条**:专注时化身待引爆的 C4,剩余时间一目了然
- 🔊 **CS:GO 语音提醒**:启动、暂停、重置、番茄完成、休息结束各有专属台词(系统语音合成朗读)
- ⌨️ **空格键**一键启动 / 暂停
- 🔔 完成时弹**系统通知**,并统计已完成的番茄数
- 🎨 霓虹青 / 荧光黄双主题配色,专注/休息自动切换

---

## 🚀 运行方式

### 方式一:直接用打包好的 app(日常推荐)

不需要终端、不需要 Node。用 `npm run package` 打包后,双击生成的
`dist/CSGO Focus Timer-darwin-arm64/CSGO Focus Timer.app` 即可。

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

## 🛠 技术栈

- [Electron](https://www.electronjs.org/) 33 —— 桌面应用外壳
- 原生 HTML / CSS / JavaScript —— 界面与逻辑(单文件 `index.html`)
- [Rajdhani](https://fonts.google.com/specimen/Rajdhani) 字体 —— 赛博朋克数字风
- Web Speech API + Web Audio API —— 语音台词与合成音效

## 📄 许可

MIT © Kevin
