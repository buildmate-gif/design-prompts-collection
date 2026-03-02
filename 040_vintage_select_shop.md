# F10 — Vintage Clothing Select Shop LP
## MOTH & MIST / ヴィンテージ古着セレクトショップ

---

## 目的
70〜90年代のヴィンテージ古着を扱うセレクトショップのLP。
「新品より、その服が生きてきた時間が好き」という感覚を持つ女性向け。
マーケットの古道具屋・フランスの蚤の市・映画のワードローブ室——そんな世界観。

---

## フォント
- 大見出し：Abril Fatface / size clamp(3rem,8vw,7rem) / letter-spacing -0.02em
- 中見出し：Playfair Display Italic / weight 400
- 本文：Noto Sans JP / size 0.88rem / line-height 2.1 / letter-spacing 0.07em
- ラベル・価格：DM Mono / size 0.68rem / letter-spacing 0.12em
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:      #F0EAE0  クリームリネン
--bg2:     #E4DDD2  ウォームサンド
--ink:     #241C14  ダークエスプレッソ
--mid:     #7C6C58  ウォームグレージュ
--rust:    #A84830  バーントラスト
--olive:   #7A8060  フェイドオリーブ
--yellow:  #D4B060  マスタードゴールド
```
純白・純黒・蛍光色 禁止。「色褪せた、けど美しい」——くすんでいるのが正解。

---

## レイアウト
- 12カラムグリッド（均等割り禁止）
- section padding 7rem〜9rem（mobile 4rem）
- 画像はフィルム写真感：縦長 3:4 / 一部に傾き（rotate ±1.5deg）
- 写真の重なり（overlap）を2〜3箇所——「棚に重ねられた服」感
- ページ全体に薄いドットパターン背景（radial-gradient dots / opacity 0.04）

---

## セクション構成
1. **HERO** — 大きなAbril見出し + 傾いた画像コラージュ（3点重なり）+ フィルム風グレイン
2. **NEW IN** — 新入荷（非均等グリッド・価格はDM Mono・一点物バッジ）
3. **ERA GUIDE** — 年代別スタイルガイド（70s / 80s / 90s の横スクロール風レイアウト）
4. **STYLING** — コーディネート提案（大きな画像 + テキスト + 「こんな日に」コピー）
5. **ABOUT** — ショップの哲学（手書き風テキスト + バイヤーの一言）
6. **VISIT CTA** — 店舗案内 + オンラインショップ誘導

---

## ボタン・インタラクション（女性向け）
- CTAボタン：border 2px solid rust / 背景なし → hover で rust が左から fill（clip-path アニメ）
- 商品カード：hover で画像が sepia(0.3) から sepia(0) に切り替わる（フィルム→カラー）
- ナビリンク：hover で文字の下に 1px の手書き風下線が左から描かれる
- スクロール：各セクションが opacity + rotate(0.5deg) → rotate(0deg) で着地する

---

## 必須ディテール（最低2つ）
- [ ] フィルムグレイン：SVG feTurbulence noise を全体に（opacity 0.06）+ hero は強め（0.1）
- [ ] 傾き着地アニメ：要素が rotate(1.5deg) から rotate(0deg) + opacity 0→1 でスクロール表示
- [ ] 一点物バッジ：「1 of 1」スタンプ（rotate -8deg / rust border）商品に重ねる
- [ ] セピア→カラーホバー：商品画像が hover で filter: sepia(0.4)→sepia(0) に遷移

---

## 装飾ルール
**OK：** 極細ボーダー / フィルムグレイン / 傾き / ドットパターン / セピアフィルター
**禁止：** 絵文字 / アイコン / box-shadow blur 10px超 / 均等グリッド / 明るい彩度高い色

---

## 感情設計（コピー指針）
- 「安い・お得」の文脈は使わない——「出会い」「一点物」「この服の前の持ち主」
- 「選ぶ楽しさ」ではなく「見つける喜び」——宝探しの感覚
- 年代のストーリーを語る：「この型は1982年にしか作られていない」
- 環境への意識も自然に：「新しく作らない選択」

---

## 補足
- ショップ名：**MOTH & MIST** / 商品名：架空の年代付き（例：Levi's 501 '84 / French Linen Blouse '76）
- コピー：英語主体（キャプション・説明は日本語）
- 画像：CSSプレースホルダー（セピア系グラデーション）
- 価格表記あり（DM Monoフォントで）
