# Scene E — Street Zine Style
## コピー機・コラージュ・パンク・アナログ感のWebページ

---

## 目的・コンテキスト

インディーズミュージックフェスまたはアンダーグラウンドアートイベントの告知ページを生成してください。
1980〜90年代のパンク・ハードコアシーンで生まれた「ゼロックスジン（Zine）」——
手でコピーし、切り貼りし、ホッチキスで綴じた自主制作冊子の質感をWebで再現します。
「完成度が低い」ことが「本物」の証明である世界観です。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts：VT323 / Special Elite / Black Han Sans など粗さ・力強さを持つフォント
- JavaScript：ランダムな位置ズレ + タイプライター効果

---

## 世界観・トーン

- 深夜のコンビニのコピー機で刷ったフライヤー
- 「洗練」は敵——荒削りであることが誠実さの証
- キーワード：Punk / Collage / Xerox / Cut / Paste / Loud

---

## カラーパレット

- ベース：コピー用紙の黄ばみ #F0EBD8 / コピー機の影 #D8D0BE
- テキスト：インクの黒 #1A1714 / 掠れたグレー #5A5550
- アクセント（2色まで許容）：スタンプレッド #C41818 / 蛍光マーカー #E8C820
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止
- ※ 「コピーを重ねて劣化した」ような彩度低めのトーンにすること

---

## タイポグラフィ

- 見出し（H1）：VT323 または Special Elite
  - font-size: clamp(3rem, 9vw, 8rem)
  - letter-spacing: 0.08em
  - 意図的なズレ（transform: translate + rotate）で「切り貼り感」を演出
- 中見出し（H2）：Black Han Sans（日本語用）または Special Elite
  - font-size: clamp(1.5rem, 3.5vw, 3rem)
- 本文（body）：Special Elite または Noto Sans JP
  - font-size: 0.95rem / line-height: 1.9 / letter-spacing: 0.02em
- 数字・価格：VT323 / font-size: 2〜3rem / スタンプ風配置
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- 「崩し」がデザインの本体——要素を大胆にズラし・傾け・重ねること
- section padding：不規則に設定（2rem〜6rem をランダムに）
- テキストブロックを −5deg〜+5deg の範囲で回転
- 「切り抜き貼り付け」感：要素ごとに異なる背景色（用紙の色）を持つ
- ボーダーは手書き風の不揃いな線（SVGまたはCSS outline）
- テキストと画像の overlap を3箇所以上

---

## 構成セクション

1. **COVER** — イベント名（巨大・傾き・重なり）+ 日時・場所をスタンプ風に配置
2. **LINEUP** — 出演者リスト（タイプライター打ち込み風 / 異なるフォントサイズ混在）
3. **MANIFESTO** — 主催者の「宣言文」（コラム形式・傾き・蛍光マーカー風下線）
4. **COLLAGE** — 過去イベントの「切り貼り写真風」プレースホルダーグリッド（非均等・重なり）
5. **TICKET INFO** — チケット情報（スタンプ風ボックス）+ 手書き風「GET IT」CTA

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

- [ ] **タイプライター効果**：MANIFESTOセクションのテキストを1文字ずつ打ち込むアニメーション
- [ ] **コピー劣化グレイン**：SVG feTurbulence で「コピーを重ねた際の汚れ・掠れ」を全体に付与（opacity 0.05〜0.08）
- [ ] **スタンプ回転**：「SOLD OUT」「残りわずか」などのテキストを赤ボーダー楕円 + rotate(-15deg) で配置
- [ ] **ランダムズレ**：ページロード時にJSで要素の transform: rotate をランダム微調整（±3deg）

---

## 補足指示

- イベント名は仮称「STATIC FEST」を使用
- 出演者名・バンド名は架空の英語・日本語混在で8〜10件
- 本文コピーは口語・断言調（「来い。」「聴け。」「今だ。」）
- 背景のコピー用紙感はSVG feTurbulenceで付与（画像は不使用）
- CSSの filter: contrast(1.1) saturate(0.85) を全体に適用してゼロックス感を強調
- フッターなし——最後のセクションで潔く終わる
