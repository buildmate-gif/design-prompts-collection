# Scene C — Organic Botanical LP
## 植物・土・手書き感のランディングページ

---

## 目的・コンテキスト

自然食品・ハーブティー・オーガニックスキンケアブランドのLPを生成してください。
「デジタルなのに土の匂いがする」不思議な体験を設計します。
手書き文字・紙の質感・植物の不規則な曲線——機械的な完璧さを意図的に排除し、
「作った人の手が見える」温かみのある世界観を構築してください。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts：Caveat / Klee One / Shippori Mincho など手書き・筆記体系フォント
- JavaScript：ゆっくりした視差 + スクロール連動フェイドイン

---

## 世界観・トーン

- 週末の朝、陽の当たるキッチンで摘みたてのハーブをクラフト紙に包む感覚
- 不完全さが「誠実さ」を証明する
- キーワード：Organic / Handmade / Earthy / Tender / Grown

---

## カラーパレット

- ベース：生成り #F4EFE3 / クリーム #EAE3D2
- テキスト：ウォームブラウン #3D2B1F / アッシュグリーン #4A5C3A
- アクセント（2色まで許容）：テラコッタ #C4693A / セージグリーン #8A9E7A
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止
- ※ 全体的に「退色した・褪せた」トーンで統一すること

---

## タイポグラフィ

- 見出し（H1）：Caveat または Klee One（手書き感のあるフォント）
  - font-size: clamp(2.5rem, 6vw, 5rem)
  - letter-spacing: 0.03em / font-weight: 400
  - 行ごとにわずかに傾き（transform: rotate(−0.5deg)〜+0.5deg）
- 中見出し（H2）：Shippori Mincho または Klee One
  - font-size: clamp(1.3rem, 2.5vw, 2rem)
- 本文（body）：Noto Sans JP
  - font-size: 0.95rem / line-height: 2.1 / letter-spacing: 0.04em
- ラベル・タグ：手書き風フォント / font-size: 0.75rem / 回転あり
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- 「整然」ではなく「自然に積み重なった」アシンメトリー必須
- section padding：最低 8rem（モバイル 4rem）——余白が「土の広がり」を表現
- テキストボックスを少し傾ける（transform: rotate(−1deg)〜+1deg）要素を2箇所以上
- 直線の代わりに不規則な曲線（border-radius: 40% 60% 55% 45% / 40% 55% 60% 45%）を使う
- SVG の手書き風ライン（stroke-dasharray）でセクション区切りを表現

---

## 構成セクション

1. **HERO** — ブランド名（手書きフォント・傾き）+ キャッチコピー + 季節感のある短文
2. **STORY** — 創業者の思い（手書き風テキストボックス + 傾いたレイアウト）
3. **PRODUCTS** — 商品3〜4点（非均等・重なり・傾き）+ 短い説明文
4. **INGREDIENTS** — 原材料・素材へのこだわり（SVG手書きライン区切り）
5. **ORDER CTA** — 温かみのある注文ボタン + 一言メッセージ

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
- border-radius 16px 超（ただし有機的曲線形状は除く）
- linear-gradient / radial-gradient の彩度が高いもの
- 均等割り3カラムカード
- Inter / Roboto / Arial / system-ui
- 紫・青のグラデーション

---

## 「忘れられないディテール」（最低2つ必須実装）

- [ ] **手書き風SVGライン**：セクション間の区切りに stroke-dasharray アニメーションで「今書いている」ような線を引く
- [ ] **有機形状のプレースホルダー**：商品画像エリアを不規則な blob 形状（SVGクリップパス）にする
- [ ] **傾いたスタンプ**：「NEW」「季節限定」などを手書きフォント + 楕円ボーダーで傾けて配置
- [ ] **紙テクスチャ**：SVG feTurbulence で背景全体にクラフト紙のような凹凸感を付与（opacity 0.04〜0.06）

---

## 補足指示

- ブランド名は仮称「MOSSGARDEN」を使用
- 商品名・素材名は架空の日本語で構わない
- 本文コピーは日本語で温かみのある口調（「〜です」ではなく「〜だと思うのです」）
- フォントの「揺らぎ」を表現するため、同じフォントでもセクションごとにwightを変える
- SNS・カートボタンなし——「問い合わせ」「直接注文」のみ
