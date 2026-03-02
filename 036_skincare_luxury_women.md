# F1 — Luxury Beauty Brand LP
## LUMÈRE / ラグジュアリースキンケアブランド

---

## 目的
プレミアムスキンケアブランドのLP。「足し算ではなく、引き算の贅沢」。Aesop・Sisley的な「説明しすぎない品格」。

---

## フォント
- 大見出し：Cormorant Garamond Italic / weight 300 / size clamp(2.8rem,5vw,5rem)
- 本文：DM Sans / weight 300 / size 0.9rem / line-height 2.1 / letter-spacing 0.06em
- ラベル：0.6rem / letter-spacing 0.3em / uppercase
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:    #FAF7F3  ウォームオフホワイト
--bg2:   #F2EDE6  深みベージュ
--ink:   #2A1F1A  ダークウォームブラウン
--mid:   #8C7B6E  ミドルベージュ
--gold:  #C5A882  くすみゴールド
--mauve: #D4C0B8  ペールモーブ
```
純白・純黒・派手なグラデーション 禁止。肌に馴染むニュートラルトーンで統一。

---

## レイアウト
- section padding 最低 10rem（mobile 5rem）——「余白が品格」
- ヒーロー：min-height 100vh / グリッド 5:7 / テキスト左下配置
- 画像比率：縦長 2:3 または 3:4 基本
- テキストと画像の overlap 2箇所以上
- 区切り：1px solid rgba(42,31,26,0.1)

---

## セクション構成
1. **HERO** — ブランド名（大きな斜体）+ タグライン + 縦長画像（視差）
2. **INTRO** — 1〜2文の哲学テキスト（大きめセリフ・センター・金のライン装飾）
3. **COLLECTION** — 商品3点（非均等グリッド・縦長・重なり）
4. **RITUAL** — 使い方・儀式説明（テキスト主体 + サイドイメージ + ステップ番号）
5. **INGREDIENTS** — 原材料こだわり（SVG細線区切り・ラベルスタイル）
6. **ORDER CTA** — 一言コピー + シンプルボタン

---

## 必須ディテール（最低2つ）
- [ ] カスタムカーソル：通常ポインター非表示 / 8pxドット（くすみゴールド）追従
- [ ] 視差：ヒーロー画像がスクロール 0.3倍速で動く（translateY）
- [ ] テキストフェード：opacity + translateY / 1.2s ease / stagger 0.2s

---

## 装飾ルール
**OK：** 1px極細ボーダー / backdrop-filter blur(12px) / SVG noiseテクスチャ opacity 0.035
**禁止：** 絵文字 / アイコン / box-shadow blur 8px超 / border-radius 16px超（ボタン除く）/ 均等割りカード

---

## 感情設計（コピー指針）
- 「効能」より「感覚・情景」：「乾燥が気になる」→「朝、鏡の前に立つのが楽しくなる」
- 「私だけの時間」「自分のために」という自己投資の文脈
- 数字より物語：成分%より「どんな畑で育ったか」
- コピーは日英混在（見出し英語/仏語、本文日本語）

---

## 補足
- ブランド名：**LUMÈRE** / 商品名：架空仏語風（Eau Profonde, Huile de Soir等）
- 画像：CSSプレースホルダー（テクスチャ付きグレーベージュ）/ 価格表記なし
