# TG-SYNTH1

瀏覽器單聲道合成器，提供 Canvas 面板、16-step sequencer、電腦鍵盤與 Web MIDI 控制。HTML、CSS 與 JavaScript 內嵌於 `index.html`，無外部套件或建置步驟。

## 本機使用

```sh
cd /Users/morimagic/Desktop/ToneGodPlayer/TG-SYNTH1/web
python3 -m http.server 8000 --bind 127.0.0.1
```

開啟 http://localhost:8000 ，按 **START AUDIO** 後操作面板或鍵盤。Chrome / Edge 可使用 Web MIDI；需瀏覽器授權及相容 MIDI 裝置。AudioWorklet 與 Web MIDI 需要安全來源（HTTPS 或 localhost）。不支援 AudioWorklet 時，程式會使用 ScriptProcessor fallback。

電腦鍵盤：A W S E D F T G Y H U J K；左右方向鍵調整八度。旋鈕可拖曳，Shift 微調、雙擊輸入數值、Alt-click 重設、右鍵 MIDI Learn。

## Git 範圍

本目錄作為獨立網頁倉庫；不包含 本地原生 Source、CMake、build、dist 或 ToneGodPlayer 其他工程。保留內部音訊 processor 名稱與瀏覽器儲存 key，避免破壞現有面板設定。

遠端倉庫：https://github.com/tonegod/TG-SYNTH1 ，可見性為公開。

網頁：https://tonegod.github.io/TG-SYNTH1/ ，由 GitHub Pages 從 `main` 根目錄部署。詳見 `DEPLOY-GITHUB-PAGES.md`。

## 驗證限制

可用 Node 的 `--check` 分別檢查內嵌 UI 與 AudioWorklet JavaScript。無既有 lint/test/build 指令；JavaScript 語法檢查不代表瀏覽器音訊、MIDI 硬體或聆聽測試通過。
