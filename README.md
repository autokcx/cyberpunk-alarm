# CS Timer 💣

> Kevin's 1st vibe coding app —— 一个 **CS:GO 战术主题**的番茄钟 / 专注计时器,用 [Electron](https://www.electronjs.org/) 打包成 macOS 桌面应用。

把「专注」变成一局 CS:GO:开始专注 = **埋下 C4**,顶部红灯闪烁、引信读条,倒计时归零就是一次**起爆**——火球 + 震屏 + 真实 C4 爆炸声 + "Terrorists Win!"。专注结束进入休息,喝杯咖啡 ☕ 放松一下。专治摸鱼。

当前版本:**v1.3.0**

---

## ✨ 功能

- 🎯 **两种模式**
  - **专注(T · 埋雷)**:可选 `5 / 15 / 25 / 35 / 45` 分钟,恐怖分子(T)主题
  - **休息(放松)**:可选 `5 / 10 / 15` 分钟,咖啡 ☕ + 青色朴素风
- 💣 **手绘 C4 炸弹**:专注时显示一颗 SVG 画的 C4(炸药棒 + 引爆器 + 数码屏 + **顶部闪烁红灯**),下方引信进度条随剩余时间收缩
- 💥 **起爆特效**:专注归零时白光火球 + 冲击波 + 火星喷溅 + 震屏
- 🔊 **CS:GO 真实原声**(放在 `sounds/`,HTML5 Audio 播放)
  | 时机 | 音效 |
  |---|---|
  | 埋雷 / 开始专注 | `planted.mp3` — "The bomb has been planted." |
  | 专注完成起爆 | `explosion.mp3` — 真实 C4 爆炸声 |
  | 专注完成胜利 | `terrorists_win.mp3` — "Terrorists Win!" |
  | 休息结束 | `ct_win.mp3` — "Counter-Terrorists Win" |
- ⏱️ **最后 10 秒**:时钟变红抖动 + 嘀嘀提示音(DETONATING)
- 🧑‍✈️ **操作员卡片**:T 武装头像 + 战术 HUD 状态条(LIVE·REC / de_focus / 实时时钟)
- 🏆 **战绩统计**:每完成一次专注 +1 分(Rounds Won)
- ⌨️ **空格键**一键启动 / 暂停
- 🔔 完成时弹**系统通知**

---

## 🚀 运行方式

### 方式一:直接用打包好的 app(日常推荐)

不需要终端、不需要 Node。用 `npm run package` 打包后,双击生成的
`dist/CS Timer-darwin-arm64/CS Timer.app` 即可。

> 首次打开若提示「无法验证开发者」:右键图标 → **打开** → 再点一次**打开**(自签名应用,只需操作一次)。

### 方式二:开发模式(改代码时用)

```bash
git clone https://github.com/autokcx/cs-timer.git
cd cs-timer
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

## 📁 项目结构

```
cs-timer/
├─ index.html      # 全部界面 + 逻辑(单文件)
├─ main.js         # Electron 主进程(建窗口 / 系统通知)
├─ preload.js      # 暴露 notify 给渲染进程
├─ avatars/        # t.png(T 头像;休息用咖啡 emoji,无需图片)
├─ sounds/         # 真实 CS:GO 音效 mp3
└─ fonts/          # Rajdhani 字体
```

---

## 🛠 技术栈

- [Electron](https://www.electronjs.org/) 33 —— 桌面应用外壳
- 原生 HTML / CSS / JavaScript —— 界面与逻辑(全在单文件 `index.html`)
- 内联 SVG —— 手绘 C4 炸弹
- CSS 动画 —— 起爆火球 / 冲击波 / 震屏
- Web Audio API —— UI 提示音(实时合成);`sounds/` 内真实 CS:GO 音效走 HTML5 Audio
- [Rajdhani](https://fonts.google.com/specimen/Rajdhani) 字体 —— 战术数字风

> 音效版权:`sounds/` 内为 CS:GO / CS2 原声,版权归 Valve,仅作个人学习练手使用。

---

## 📄 许可

代码 MIT © Kevin。CS:GO 音效版权归 Valve。
