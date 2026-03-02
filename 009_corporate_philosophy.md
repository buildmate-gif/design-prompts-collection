# Scene 04 — Corporate Site / About & Philosophy
## 老舗ブランド・設計事務所 理念ページ

---

## 目的・コンテキスト

老舗ブランドまたは建築設計事務所の「About / Philosophy」ページを生成してください。
創業の思想・職人的こだわり・時代を超える価値観を伝えるページです。
「重量感と余白が共存する」MONOCLE的な佇まいを目指してください。
訪問者が「ここに仕事を頼みたい」と感じる信頼の醸成が目的です。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts のみ使用可
- JavaScript は控えめなマイクロインタラクションに限定（CSS優先）

---

## 世界観・トーン

- 創業100年の時計工房のような静かな矜持
- 言葉を選んで語る誠実さ
- キーワード：Craft / Legacy / Quiet Authority

---

## カラーパレット

- ベース：温かみのあるリネン #F2EFE8 / ダストグレー #DDD9D2
- テキスト：ディープチャコール #1A1916 / ウォームグレー #706C65
- アクセント（1色のみ）：ダークモス #4A5C3A（深みのある緑）
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止

---

## タイポグラフィ

- 見出し（H1）：Noto Serif JP + Cormorant Garamond
  - font-size: clamp(2.5rem, 6vw, 5rem)
  - letter-spacing: -0.02em / font-weight: 300
- 中見出し（H2）：Noto Serif JP / font-size: clamp(1.3rem, 2.5vw, 2rem)
- 本文（body）：Noto Sans JP
  - font-size: 1rem / line-height: 2.0 / letter-spacing: 0.04em
- 数字・年号：Cormorant Garamond / font-size: 3〜5rem / font-weight: 300
- ラベル：uppercase / font-size: 0.65rem / letter-spacing: 0.2em
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- アシンメトリー必須：[4col 余白 + 縦書き] + [8col 本文] などの構成
- section padding：最低 10rem（モバイル 5rem）
- テキストと画像の overlap を1箇所以上
- 細いルーラー線（1px / opacity 0.12）で章分割

---

## 構成セクション

1. **OPENING** — 創業年（大型数字）+ 一行の理念コピー（日本語セリフ体 全幅）
2. **OUR STORY** — 縦書き章タイトル + 横書き本文（左右非対称）
3. **PHILOSOPHY** — 3つの価値観（均等割り禁止・重なり・ズレを演出）
4. **PEOPLE** — 代表者の言葉（縦書き引用）+ モノクロ写真プレースホルダー
5. **FOOTER** — 住所・連絡先 + 細いルーラー線

---

## 装飾ルール（必須遵守）

### 使用可能

- 1px 極細ボーダー（border: 1px solid rgba(26,25,22,0.12)）
- backdrop-filter: blur(12px) / 半透明背景
- SVG feTurbulence によるノイズテクスチャ（opacity 0.03〜0.05）
- テキストアニメーション：opacity + translateY（0.8s ease、staggered / 遅め設定）
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

- [ ] **縦書きアクセント**：OUR STORY セクションの章タイトルを writing-mode: vertical-rl で左端に配置
- [ ] **大型年号**：創業年または重要な年（例: 1921）を Cormorant Garamond で画面横幅いっぱいに薄く表示（opacity 0.06）
- [ ] **フォリオ番号**：各セクションの右下または左下に 01 / 02 / 03 のナンバリング
- [ ] **紙焼き質感**：代表者写真プレースホルダーに SVG feTurbulence フィルムグレイン

---

## 補足指示

- 本文コピーは日本語で記述（3〜4段落）
- 創業ストーリーは架空のもので構わない
- ナビゲーションは固定ヘッダー（透明背景 / スクロールで半透明に変化）
- CTAは「お問い合わせ」のみ（テキストリンク形式、最小限）
- 地図・SNSリンクは不要
