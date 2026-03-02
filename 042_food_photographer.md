# F12 — Food Photographer Portfolio
## YUKI HARA / フードフォトグラファーポートフォリオ

---

## 目的
フードフォトグラファー個人のポートフォリオサイト。
「料理を撮るのではなく、食卓の空気を切り取る」フォトグラファーの世界観を伝えるページ。
依頼者（飲食店・食品ブランド・雑誌）への信頼感と、固有の美意識を両立させる。

---

## フォント
- 名前・大見出し：Fraunces Italic / weight 300 / size clamp(2.5rem,6vw,5.5rem)
- 中見出し：Noto Serif JP / weight 400 / letter-spacing 0.12em
- 本文・キャプション：Jost / weight 300 / size 0.82rem / line-height 2.2 / letter-spacing 0.1em
- 数字・データ：DM Mono / size 0.65rem
- **禁止：Inter / Roboto / Arial / system-ui**

---

## カラー
```
--bg:    #F8F4EE  クリームホワイト
--bg2:   #EEE8DC  ウォームペーパー
--ink:   #28201A  ダークブラウン
--mid:   #907060  ウォームブラウン
--mist:  #C0B8B0  ミストグレー
--green: #6A7A60  フォレストグリーン
```
純白・純黒・鮮やかな原色 禁止。「午後の窓際の光」のような柔らかさ。

---

## レイアウト
- 非均等マソンリー風グリッド（JavaScript不使用でCSSのみ）
- section padding 8rem〜10rem（mobile 4rem）
- 写真プレースホルダーの比率を意図的にバラバラに：1:1 / 3:4 / 16:9 / 2:3 が混在
- ホワイトスペースを「呼吸」として積極的に使う
- 極細ボーダーラインで「フレーム」感——写真展示のような空間

---

## セクション構成
1. **OPENING** — 名前（Fraunces Italic 大）+ 肩書き + キャッチフレーズ + 横長フルブリード写真
2. **WORKS** — ポートフォリオ（カテゴリ：Restaurant / Product / Magazine / Editorial）非均等グリッド
3. **PROCESS** — 撮影プロセス紹介（3ステップ：Before / Styling / After イメージ）
4. **CLIENTS** — 実績クライアント（テキストのみ / セリフ体 / 縦横混在レイアウト）
5. **ABOUT** — フォトグラファー紹介（縦長自己紹介写真 + 哲学テキスト）
6. **CONTACT** — 依頼フォーム + SNSリンク（テキストのみ）

---

## ボタン・インタラクション（女性向け）
- 作品ホバー：overlay が opacity 0 → 0.85（bg2）でゆっくり現れ、カテゴリ名 + 「View」が中央に
- カテゴリフィルター：選択時に下線が左から右へ描かれる（1px green / 0.4s ease）
- CTAボタン：テキスト + 右矢印 → hover で矢印が 6px 右にスライド（transform ease 0.3s）
- スクロール：各写真ブロックが opacity 0 + scale(0.97) → 1 でゆっくり浮き上がる（1s ease）

---

## 必須ディテール（最低2つ）
- [ ] 写真ホバーオーバーレイ：bg2 色の overlay + 中央テキストがゆっくり現れる（0.6s）
- [ ] スケールフェードイン：写真ブロックが scale(0.97)→scale(1) + opacity 0→1 でスクロール表示
- [ ] カーソル変化：写真にホバーで cursor が circle（24px / green border）に変わる
- [ ] カテゴリフィルター：JS でクラス切り替え + CSS transition で非選択が opacity 0.3 に

---

## 装飾ルール
**OK：** 極細ボーダー（1px mist） / 写真ホバーオーバーレイ / scale animate / カスタムカーソル
**禁止：** 絵文字 / FontAwesome / box-shadow blur 8px超 / 均等グリッド / 過剰装飾（写真が主役）

---

## 感情設計（コピー指針）
- 「おいしそうに撮ります」ではなく「記憶に残る一枚を」
- 依頼者の不安を取り除く：プロセスを可視化する / 実績を静かに見せる
- 「あなたのブランドにとって何が大切か、一緒に考えます」
- 写真のキャプションは料理の説明でなく「情景・感情」

---

## 補足
- 名前：**YUKI HARA** / 肩書き：Food & Still Life Photographer
- クライアント名：架空でOK（例：GURA Restaurant / Miele Japan / Souen Magazine）
- コピー：英語主体（本文日本語）
- 画像：CSSプレースホルダー（食材感のあるウォームトーン：クリーム・セージ・テラコッタ系）
