# Scene 03 — Online Magazine / Article Detail
## 長文コンテンツ エディトリアルレイアウト

---

## 目的・コンテキスト

オンラインマガジンの記事詳細ページを生成してください。
長文コンテンツを「読み疲れさせずに最後まで読ませる」レイアウト設計を最優先とします。
BRUTUS / Casa BRUTUS の紙面をそのままWebに移植したような
「読む喜びのある」エディトリアルデザインを目指してください。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts のみ使用可
- JavaScript は控えめなマイクロインタラクションに限定（CSS優先）

---

## 世界観・トーン

- 雑誌の特集記事を読む体験
- 文章と写真が互いを引き立てる紙面構成
- キーワード：Reading Pleasure / Typographic Rhythm / Layered Depth

---

## カラーパレット

- ベース：アイボリー #F7F5F0 / ペーパーグレー #ECEAE4
- テキスト：チャコール #1C1C1A / ソフトグレー #707070
- アクセント（1色のみ）：バーント・シエナ #A0522D（引用・強調・章番号）
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止

---

## タイポグラフィ

- 見出し（H1）：Noto Serif JP + Cormorant Garamond（日英混在）
  - font-size: clamp(2.5rem, 5vw, 4.5rem)
  - letter-spacing: -0.02em / font-weight: 300
- リード文：Noto Serif JP / font-size: 1.2rem / line-height: 2.0
- 本文（body）：Noto Sans JP
  - font-size: 1rem / line-height: 1.9 / letter-spacing: 0.03em
- プルクオート：Cormorant Garamond italic / font-size: 1.6rem
- ラベル・カテゴリ：uppercase / font-size: 0.65rem / letter-spacing: 0.15em
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
  本文エリア：中央 7〜8col / サイドバー 3〜4col
- アシンメトリー必須
- section padding：最低 6rem（モバイル 3rem）
- 本文中に差し込む画像はテキストを跨いで overflow させる（overlap演出）
- 細いルーラー線（1px / opacity 0.08）で章・セクションを分割

---

## 構成セクション

1. **ARTICLE HEADER** — カテゴリラベル + 大型見出し + 著者・日付 + ヒーロー画像（全幅）
2. **LEAD** — 2〜3文のリード文（大きめフォント）
3. **BODY** — 章立て本文（章番号はバーント・シエナ）+ 途中に横断画像
4. **PULL QUOTE** — 印象的な一文を Cormorant Garamond で大きく引用
5. **RELATED ARTICLES** — 2件のみ（非均等グリッド）

---

## 装飾ルール（必須遵守）

### 使用可能

- 1px 極細ボーダー（border: 1px solid rgba(28,28,26,0.1)）
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

- [ ] **縦書きアクセント**：記事サイドバーに writing-mode: vertical-rl で章タイトルや連載名を表示
- [ ] **プルクオートのタイポグラフィ**：引用部分を Cormorant Garamond italic × 大型サイズ × アクセントカラーの装飾線で囲む
- [ ] **フォリオ番号**：章の切れ目に 01 / 02 / 03 の印刷物的ナンバリング
- [ ] **紙焼き質感**：ヒーロー画像と本文途中画像に SVG feTurbulence フィルムグレイン

---

## 補足指示

- 記事本文のサンプルテキストは日本語で3〜4段落分生成すること
- プレースホルダー画像は CSS で生成（グレースケール矩形 / aspect-ratio 指定）
- 読了時間の表示（例：読了目安 8分）をヘッダー部に小さく入れる
- SNSシェアボタンは不要
- 広告枠は一切入れない
