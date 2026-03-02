# Scene B — Neon Night Market
## 東南アジアの夜市 × サイバーパンク LP

---

## 目的・コンテキスト

フードイベント・ナイトマーケット・路上グルメフェスの告知LPを生成してください。
香港・台北・バンコクの路地裏に迷い込んだような過密で生命力あふれるビジュアル体験を設計します。
情報が「氾濫」するように見えながら、視線の導線だけは意図的にコントロールしてください。
「今すぐ行きたい」という衝動を引き起こすページです。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts：Zen Dots / Stick / Boogaloo など「エネルギッシュ・ポップ」系フォント
- JavaScript：グリッチアニメーション + スクロール連動演出

---

## 世界観・トーン

- 赤提灯・蛍光看板・湯気・雑踏の活気
- 「整っていないことが正しい」カオスの美学
- キーワード：Neon / Chaos / Alive / Street / Heat

---

## カラーパレット

- ベース：深夜の路地 #0D0C0A / 屋台の影 #1A1714
- テキスト：ホットホワイト #F0EDE5 / フォグイエロー #E8D890
- アクセント（2色まで許容）：ネオンピンク #FF2D78 / 電気シアン #00E5D4
- ※ 純白 #FFFFFF・純黒 #000000・原色（彩度100%）・派手なグラデーション 禁止
- ※ ネオン色は「くすみ」を1〜2トーン落として使用すること

---

## タイポグラフィ

- 見出し（H1/イベント名）：Zen Dots または Stick
  - font-size: clamp(3rem, 9vw, 8rem)
  - letter-spacing: 0.05em
  - 斜体（transform: skewX(-6deg)）で勢いを加える
- サブ見出し：Boogaloo または Fredoka One / font-size: clamp(1.2rem, 3vw, 2.5rem)
- 本文（body）：Noto Sans JP / font-size: 0.95rem / line-height: 1.75
- ラベル・数字：Zen Dots / font-size: 1.5rem〜 / 蛍光カラーで強調
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- 「わざと崩した」アシンメトリー必須：要素を意図的にずらし・重ねる
- section padding：2〜4rem（余白は少なく——密度と圧迫感を演出）
- テキストと背景要素の overlap を3箇所以上（重なりが「にぎわい」を表現する）
- 複数の細いボーダーラインを「看板の枠」として活用（色付きボーダー可）
- 回転要素（transform: rotate(−3deg)〜+3deg）を2箇所以上

---

## 構成セクション

1. **HERO** — イベント名（巨大テキスト・斜め配置）+ 日程・場所 + 「今すぐ申込」CTA
2. **LINEUP** — 出店者・フード一覧（タグ・スタンプ・バッジ風レイアウト）
3. **HIGHLIGHTS** — 見どころを「手書き吹き出し風」に配置
4. **MAP & ACCESS** — 簡易地図風イラスト（CSSのみで表現）+ アクセス情報
5. **TICKET CTA** — チケット価格と申込ボタン（ネオンカラー強調）

---

## 装飾ルール（必須遵守）

### 使用可能

- 1px 極細ボーダー（border: 1px solid rgba(26,26,26,0.1)）
- backdrop-filter: blur(12px) / 半透明背景
- SVG feTurbulence によるノイズテクスチャ（opacity 0.03〜0.05）
- テキストアニメーション：opacity + translateY（0.6s ease、stagger）
- ホバー：下線 transform: scaleX / 文字色の subtle なシフト

### 完全禁止

- 絵文字・アイコン（FontAwesome 含む）一切禁止
- box-shadow の blur 半径 8px 超
- border-radius 16px 超
- linear-gradient / radial-gradient の彩度が高いもの
- 均等割り3カラムカード
- Inter / Roboto / Arial / system-ui
- 紫・青のグラデーション

---

## 「忘れられないディテール」（最低2つ必須実装）

- [ ] **グリッチテキスト**：メインタイトルにCSSグリッチアニメーション（text-shadow のずれ・clip-path）
- [ ] **点滅ネオン**：アクセントカラーのテキストまたはボーダーに低速点滅（animation: flicker）
- [ ] **スタンプ風バッジ**：「限定」「NEW」などを回転させたCSSのみのスタンプ装飾（transform: rotate）
- [ ] **カウントダウン**：イベント開催までのカウントダウンタイマー（ネオンカラー表示）

---

## 補足指示

- イベント名は仮称「HEAT NIGHT MARKET」を使用
- 出店者名・フード名は架空の日本語・英語混在で8〜10件
- 「蒸気・熱気」を表現するためCSSの blur / opacity アニメーションを背景に使う
- 地図はCSSグリッドの線のみで表現（画像不使用）
- モバイル時は要素の重なりを維持したまま縦スクロールに最適化
