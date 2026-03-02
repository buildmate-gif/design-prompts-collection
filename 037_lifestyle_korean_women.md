# F2 — Korean Lifestyle Shop LP
## DAHLIA ROOM / 韓国系ライフスタイルショップ

---

## 目的
韓国発セレクトショップのLP。「センスがいいね」と言われたい女性向け。MUSINSA・29CM的な洗練された軽さ。

---

## フォント
- 大見出し：Playfair Display Italic / weight 400 / size clamp(2.5rem,5vw,4.5rem)
- 中見出し：Noto Sans JP / weight 300 / letter-spacing 0.12em
- 本文：Noto Sans JP / size 0.88rem / line-height 2.0 / letter-spacing 0.08em
- ラベル：Jost / size 0.6rem / letter-spacing 0.22em / uppercase
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:   #FAF4F0  くすみピンクホワイト
--bg2:  #F2EAE2  ミルクベージュ
--ink:  #2E2420  ウォームチャコール
--mid:  #8A7D76  ミドルグレージュ
--rose: #D4A8A0  くすみダスティローズ
--sage: #A8B8A0  ウォームセージ
```
純白・純黒・蛍光色・高彩度カラー 禁止。彩度を必ず落とすこと。

---

## レイアウト
- section padding 最低 8rem（mobile 4rem）
- 角丸：border-radius 12px〜20px（柔らかい印象）
- 画像比率：正方形 1:1 または縦長 4:5
- テキストセンタリング多用（K-style）
- ページ全体に極細グリッド線（rgba pink 0.05）

---

## セクション構成
1. **HERO** — ショップ名（Playfair Italic）+ 季節キャッチコピー + 商品画像3点（blob形状or重なり）
2. **NEW ARRIVALS** — 新着4点（非均等グリッド・丸角・New/限定バッジ）
3. **LIFESTYLE** — 暮らし提案2行（テキスト+画像交互・2パターン）
4. **RANKING** — 人気4点（大きな薄い番号 + 画像 + テキスト）
5. **ABOUT** — ショップこだわり（セリフ体・余白 + サイドイメージ + 浮かせたメモ）
6. **SHOP CTA** — ダーク背景 + ショップリンク + SNS誘導

---

## 必須ディテール（最低2つ）
- [ ] ホバーリフト：商品画像 translateY(-6px) + soft shadow（0.4s ease）
- [ ] スクロールプログレスバー：ページトップに 2px・くすみローズ
- [ ] グリッド背景：body全体に 60px格子 rgba(212,168,160,0.05)

---

## 装飾ルール
**OK：** 1px極細ボーダー / backdrop-filter blur(12px) / SVG noise opacity 0.03
**禁止：** 絵文字 / アイコン / box-shadow blur 8px超 / border-radius 24px超 / 均等割りカード / SNSアイコン（テキストのみ）

---

## 感情設計（コピー指針）
- 機能より気分：「保湿力が高い」→「塗った後、心まで満たされるような」
- 「〇〇している私が好き」という自己肯定の文脈
- 韓国語・英語の単語をさりげなく混在（過剰にしない）
- 価格は控えめに表示

---

## 補足
- ショップ名：**DAHLIA ROOM** / 商品名：架空韓国語風英語（Yua Serum, Mellow Glow Toner等）
- コピー：日本語主体 / ラベル英語
- 画像：CSSプレースホルダー（くすみピンクベージュ・border-radius付き）
