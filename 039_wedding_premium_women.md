# F4 — Premium Wedding LP
## BLANC CHÉRI / プレミアムウェディングブランド

---

## 目的
高級ウェディングプランナーのLP。「静かな幸福は、騒がない」。光・余白・繊細タイポグラフィで語る。

---

## フォント
- 大見出し：Cormorant Garamond Italic / weight 300 / size clamp(3rem,7vw,6.5rem) / letter-spacing 0.06em
- 日本語：Noto Serif JP / weight 400 / line-height 2.3 / letter-spacing 0.1em
- キャプション：Jost / size 0.6rem / letter-spacing 0.28em / uppercase
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:   #FAF7F2  シャンパンホワイト
--bg2:  #F3EEE5  ペールアイボリー
--ink:  #3A2E28  ディープシャンパン
--mid:  #9A8C84  ウォームグレージュ
--gold: #C8A882  ペールゴールド
--rose: #E8D4CE  ロゼパウダー
```
純白・純黒・高彩度グラデーション 禁止。シャンパンの泡のような淡くて上質なトーン。

---

## レイアウト
- section padding 最低 12rem（mobile 5rem）——「ウェディングは急がない」
- 縦長画像比率 2:3 または 3:4 基本（フィルム写真感）
- テキストと画像の overlap 2〜3箇所
- 区切り：1px dashed rgba(200,168,130,0.3)

---

## セクション構成
1. **HERO** — ブランド名（Cormorant Italic 大）+ 英語タグライン + 縦長フルスクリーン画像
2. **CONCEPT** — 2〜3文の哲学テキスト（セリフ大・センター・広い余白）+ 金の点線フレーム
3. **STYLE** — ウェディングスタイル3種（縦長画像・非均等グリッド）
4. **MOMENT** — 「特別な瞬間」横長画像 + 縦書きテキスト
5. **SERVICE** — サービス内容（細線テーブル・番号付き）
6. **CONTACT CTA** — 「まずはご相談を」優しいCTA

---

## 必須ディテール（最低2つ）
- [ ] 光の視差：ヒーロー brightness がスクロールで 1.0→1.05 変化
- [ ] letter-spacing ホバー：0.06em → 0.10em（0.5s ease）
- [ ] 金の点線フレーム：CONCEPTテキストを囲む 1px dashed gold
- [ ] 超ゆっくりフェードイン：各セクション opacity 0→1 / 1.5s ease

---

## 装飾ルール
**OK：** 1px極細ボーダー / backdrop-filter blur(12px) / SVG noise opacity 0.03〜0.04
**禁止：** 絵文字 / アイコン / box-shadow blur 8px超 / border-radius 8px超 / 均等割りカード / 派手アニメ・グリッチ・点滅

---

## 感情設計（コピー指針）
- 「夢を叶える」→「ふたりらしさを見つける旅に寄り添う」
- CTAは命令形にしない：「今すぐ申込む」→「まずはお話を聞かせてください」
- 写真より「光と影」の言葉 / テキスト最小限
- 不安を取り除く：「わからなくても大丈夫」「一緒に考えましょう」

---

## 補足
- ブランド名：**BLANC CHÉRI** / スタイル名：架空仏語英語風（Jardin Blanc, Lumière Dorée等）
- コピー：大見出し 英語/仏語 / 本文 日本語
- 画像：CSSプレースホルダー（シャンパン〜ペールゴールドグラデ）
- 価格表記なし / 「ご予算に応じてご相談」スタイル
