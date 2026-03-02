# F3 — 丁寧な暮らし系マガジン LP
## てのひら / ライフスタイルコンテンツマガジン

---

## 目的
「丁寧な暮らし」テーマのオンラインマガジンTOP。天然生活・暮らしの手帖的な信頼と温もりのある誌面感。

---

## フォント
- 大見出し：Shippori Mincho / weight 500 / size clamp(2rem,5vw,4.5rem) / letter-spacing 0.1em
  - 一部に縦書き（writing-mode: vertical-rl）使用
- 英字アクセント：Lora Italic / letter-spacing 0.05em
- 本文：Noto Sans JP / size 0.92rem / line-height 2.2 / letter-spacing 0.06em
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:    #F5F1E8  アイボリー
--bg2:   #EDE7D8  クリームイエロー
--ink:   #2C2018  ダークブラウン
--mid:   #7A6552  ミドルブラウン
--terra: #B8604A  テラコッタ
--sage:  #7A8F72  セージグリーン
```
純白・純黒・鮮やかな原色 禁止。「退色した古い本」のような温かみのあるトーン。

---

## レイアウト
- section padding 最低 8rem（mobile 4rem）
- 縦書きテキスト（writing-mode: vertical-rl）を1〜2箇所使用
- 記事一覧：雑誌目次風・非均等グリッド（横長+縦長+正方形の混在）
- SVG手書き風ライン（stroke-dasharray アニメ）でセクション間を区切る
- 背景全体に SVG feTurbulence ノイズ（opacity 0.05）——和紙テクスチャ

---

## セクション構成
1. **MASTHEAD** — マガジン名（縦×横書き混在）+ 季節の一言 + 最新号日付
2. **FEATURED** — 今月特集（大きな画像 + 縦書き見出し）
3. **CONTENTS** — 記事一覧5〜6点（不規則グリッド）
4. **SEASON** — 季節の仕事・暦（縦書きタイポ + 4項目）
5. **COLUMN** — 連載コラム4点（番号 + テキスト主体・余白）
6. **SUBSCRIBE** — 定期購読（温かみのあるCTA）

---

## 必須ディテール（最低2つ）
- [ ] 縦書き見出し：writing-mode: vertical-rl で季節感ある縦書き
- [ ] SVG手書き線：stroke-dasharray アニメ「今書いている」ような線（スクロールトリガー）
- [ ] 和紙テクスチャ：SVG feTurbulence ノイズを背景全体に（opacity 0.05）

---

## 装飾ルール
**OK：** 1px極細ボーダー / backdrop-filter blur(8px) / 和紙テクスチャ
**禁止：** 絵文字 / アイコン / box-shadow blur 8px超 / border-radius 12px超 / 均等割りカード / 派手アニメ（静けさが命）

---

## 感情設計（コピー指針）
- タイトルは「ノウハウ」より「問いかけ」：「どうする→どう感じる」
- 季節の話題を必ず入れる（女性は季節の変化に感度が高い）
- 「誰かに読んでほしい」シェア衝動を生む詩的な一言コピー
- 「ゆっくり読む時間」が許される余白と文字量

---

## 補足
- マガジン名：**てのひら**（サブ：暮らしの中の小さな豊かさ）
- 記事タイトル：架空の日本語（例：「秋の台所仕事、十二のこと」）
- 画像：CSSプレースホルダー（温かみのあるブラウン系グラデ）
- フッターに「編集後記」的なひとこと文を入れる
