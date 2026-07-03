# 實體橋接控制台（Wireless Bridge）

WEMOS 感測器訊號（MQTT）→ 網頁遊戲動作的橋接工具。選組別連線、設定「當 A 有訊號就⋯」規則、貼入 HTML 遊戲即可合體。

## 上架（GitHub Pages）

1. GitHub → New repository：名稱建議 `toy-bridge`（Public）
2. 上傳本資料夾的 `index.html`（和這個 README）→ Commit
3. Settings → Pages → Deploy from a branch → `main` / root → Save
4. 1–2 分鐘後生效：`https://你的帳號.github.io/toy-bridge/`

## 回填設定

- GAS Dashboard 指令碼屬性 `BRIDGE_URL` = 上面網址

## 連線設定（頁面內「給老師」摺疊區可改）

| 項目 | 預設值 |
|---|---|
| Broker | `wss://broker.emqx.io:8084/mqtt`（自有 broker 請換掉） |
| Topic 前綴 | `ckfablab/toy2026`（訂閱 `前綴/g1~g6/signal`） |

需與 `06_Arduino範本_WEMOS.ino` 的設定一致。注意：帳密寫在前端頁面原始碼中，僅適合活動用臨時帳號，活動後建議更換。

## 必測

GitHub Pages 是 https，MQTT 必須走 **wss**（不能 ws）；上架後開頁面 → 選 g1 → 連線 → 綠燈，WEMOS 按鈕觸發後「訊號紀錄」跳出 A。
