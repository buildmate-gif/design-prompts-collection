# Scene 01 — Minimal Portfolio Site
## フォトグラファー／デザイナー向け ミニマル・ポートフォリオ

---

## 目的・コンテキスト

フォトグラファーまたはグラフィックデザイナーの個人ポートフォリオLPを生成してください。
作品そのものが主役であり、UI は極限まで存在を消します。
訪問者が「気づいたらスクロールしていた」体験を設計してください。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts のみ使用可
- JavaScript は控えめなマイクロインタラクションに限定（CSS優先）

---

## 世界観・トーン

- 写真集をめくるような静謐さ
- 余白が「語る」デザイン
- 作家性を感じさせるが、主張しすぎない
- キーワード：Silence / Grain / Presence

---

## カラーパレット

- ベース：深みのあるオフブラック #141412 / ダークチャコール #1E1D1A
- テキスト：クリームホワイト #EDE9E0 / ミッドグレー #8A8680
- アクセント（1色のみ）：くすんだゴールド #B8975A
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止

---

## タイポグラフィ

- 見出し（H1）：Cormorant Garamond または Playfair Display
  - font-size: clamp(3rem, 7vw, 6rem)
  - letter-spacing: -0.03em
  - font-weight: 300
- 本文（body）：DM Sans または Outfit
  - font-size: 0.9rem / line-height: 1.9 / letter-spacing: 0.04em
- ラベル・キャプション：uppercase / font-size: 0.65rem / letter-spacing: 0.18em
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
  例：[2col 余白] + [8col 画像] + [2col 余白] / [1col 番号] + [6col 見出し] など
- アシンメトリー必須
- section padding：最低 10rem（モバイル 5rem）
- テキストと画像の overlap を1箇所以上
- 細いルーラー線（1px / opacity 0.1）でセクション分割

---

## 構成セクション

1. **HERO** — 画像全面 + 作家名を左下に極小配置
2. **SELECTED WORKS** — 縦長作品グリッド（非均等配置）
3. **ABOUT** — 縦書き日本語アクセント + 短い英文プロフィール
4. **CONTACT** — 最小限のフォームまたはメールリンク

---

## 装飾ルール（必須遵守）

### 使用可能

- 1px 極細ボーダー（border: 1px solid rgba(237,233,224,0.15)）
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

- [ ] **テキストマスク画像**：大型見出しのテキストに作品写真をクリップするタイポグラフィ表現
- [ ] **縦書きアクセント**：writing-mode: vertical-rl による日本語サブタイトル（右端に配置）
- [ ] **ページ番号フォリオ**：各セクションに 01 / 02 / 03 の印刷物的ナンバリング
- [ ] **紙焼き質感**：画像に SVG feTurbulence でフィルムグレイン効果

---

## 補足指示

- プレースホルダー画像は CSS で生成（グレースケール矩形 / aspect-ratio 指定）
- 日本語・英語のバイリンガル表記を随所に混在させる
- ナビゲーションは固定ヘッダーではなく、ページ内アンカーのみ
- フッターは1行のみ（コピーライト表記）
