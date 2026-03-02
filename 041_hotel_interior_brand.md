# F11 — Hotel-like Interior Brand LP
## SŌMA / ホテルライクインテリアブランド

---

## 目的
「毎日をホテルのように」をコンセプトにしたインテリア・ホームグッズブランドのLP。
ACEホテル・andaz・一泊15万円の旅館——そのチェックイン時の「はっとする感覚」を
自分の部屋で日常にしたい女性のためのページ。

---

## フォント
- 大見出し：Bodoni Moda Italic / size clamp(2.5rem,6vw,5.5rem) / letter-spacing 0.03em
- 中見出し：Noto Serif JP / weight 400 / letter-spacing 0.15em
- 本文：Jost / weight 300 / size 0.9rem / line-height 2.2 / letter-spacing 0.08em
- ルーム番号・数字：DM Mono / letter-spacing 0.1em
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:      #F7F4EF  リネンホワイト
--bg2:     #EEEAE3  ウォームグレー
--bg-dark: #1E1C18  ダークチャコール（アクセントセクションに使用）
--ink:     #2A2620  ウォームブラック
--mid:     #888078  グレージュ
--stone:   #B8B0A4  ストーングレー
--brass:   #B89860  ブラス（金属感のあるゴールド）
```
純白・純黒 禁止。ホテルロビーのような「白でも暖かい」ニュートラル。

---

## レイアウト
- 12カラムグリッド（均等割り禁止）
- section padding 最低 10rem（mobile 5rem）
- 「部屋番号」的なルーム感：セクションごとに薄い番号（01 / 02 / 03）を背景に大きく
- 画像は水平横長（16:9）と縦長（3:4）の混在——ホテルの間取り図的な視点
- フルブリードのダーク背景セクションを1箇所（ルームサービス的なCTA）

---

## セクション構成
1. **LOBBY** — ブランド名（Bodoni Italic）+ 「Check in to your everyday」+ 全幅横長画像
2. **AMENITIES** — 商品ライン紹介（リネン / セラミック / アロマ / ミラー）非均等グリッド
3. **THE ROOM** — インテリアスタイリング提案（大きな部屋写真 + ルーム番号装飾）
4. **DETAIL** — プロダクトのこだわり（素材・職人・生産地）细线テーブル形式
5. **CONCIERGE** — ダーク背景 / パーソナルスタイリング相談CTA
6. **CHECKOUT** — ショップへのリンク + ニュースレター登録

---

## ボタン・インタラクション（女性向け）
- CTAボタン：背景なし / brass 1px border → hover で背景が brass になり文字が dark に変わる（0.5s ease）
- 商品カード：hover で 1px brass border が四辺から描かれる（clip-path animate）
- ルーム番号装飾：スクロール視差で背景の大きな番号が 0.15倍速で動く
- ナビ：scroll で header が bg-dark + backdrop-blur に切り替わる（transition 0.6s）

---

## 必須ディテール（最低2つ）
- [ ] ルーム番号背景：セクションごとに 01/02/03 を font-size 20vw / opacity 0.04 で配置
- [ ] brass ボーダーアニメ：商品ホバー時に細い金色ボーダーが四辺から現れる
- [ ] 視差スクロール：横長メイン画像が 0.2倍速で動く
- [ ] ダーク切り替えナビ：スクロール量でヘッダーが bg 切り替わる

---

## 装飾ルール
**OK：** 極細ボーダー（1px stone） / backdrop-filter blur / SVG noise opacity 0.03 / 視差 / ルーム番号装飾
**禁止：** 絵文字 / アイコン / box-shadow blur 8px超 / 均等割りカード / border-radius 8px超 / 派手グラデ

---

## 感情設計（コピー指針）
- 「部屋を変える」ではなく「毎朝の感覚を変える」
- ホテル語彙を借りる：Check in / Amenity / Suite / Concierge / Stay
- 「贅沢品」でなく「投資」——「毎日触れるものだから」
- 五感への訴求：手触り・香り・光の反射

---

## 補足
- ブランド名：**SŌMA**（ローマ字表記）/ 商品名：架空英語（例：Stone Carafe / Linen Duvet / Brass Mirror）
- コピー：英語主体 / 本文日本語
- 画像：CSSプレースホルダー（ウォームグレー系グラデーション）
- 価格表記あり / ¥ 表記でシンプルに
