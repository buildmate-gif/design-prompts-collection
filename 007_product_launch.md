# Scene 02 — Product Launch LP
## スタートアップ 新サービス発表ページ

---

## 目的・コンテキスト

スタートアップが新プロダクトをローンチする際のランディングページを生成してください。
スクロールするたびに「次を見たくなる」演出設計を最優先とします。
テック感・AI感は排除し、モノクルやウォールストリートジャーナルのような
「知的で落ち着いたプレミアム感」を纏わせてください。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts のみ使用可
- JavaScript は控えめなマイクロインタラクションに限定（CSS優先）

---

## 世界観・トーン

- 高級時計ブランドの新作発表に近い緊張感
- 機能の羅列ではなく、「意志」を語るコピー
- キーワード：Precision / Intent / Unveil

---

## カラーパレット

- ベース：オフホワイト #F5F4F0 / ウォームグレー #E8E6E1
- テキスト：チャコール #1A1A1A / ミッドグレー #6B6B6B
- アクセント（1色のみ）：テール #2E6B6B（深みのある青緑）
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止

---

## タイポグラフィ

- 見出し（H1）：Cormorant Garamond
  - font-size: clamp(2.5rem, 6vw, 5rem)
  - letter-spacing: -0.02em / font-weight: 300
- 見出し（H2）：Playfair Display
  - font-size: clamp(1.5rem, 3vw, 2.5rem)
- 本文（body）：Outfit
  - font-size: 1rem / line-height: 1.85 / letter-spacing: 0.02em
- ラベル・キャプション：uppercase / font-size: 0.7rem / letter-spacing: 0.12em
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- アシンメトリー必須：黄金比（1:1.618）または白銀比（1:1.414）を意識
- section padding：最低 8rem（モバイル 4rem）
- テキストと画像の overlap を1箇所以上
- 細いルーラー線（1px / color: rgba(26,26,26,0.1)）でセクション分割

---

## 構成セクション

1. **HERO** — プロダクト名（大型セリフ体） + キャッチコピー1行 + CTAボタン
2. **THE PROBLEM** — 左: 課題の短文 / 右: ビジュアル（非均等グリッド）
3. **THE SOLUTION** — 機能を羅列せず、「体験の変化」を語る3段落
4. **PROOF** — 数値実績（大型数字 × セリフ体）
5. **CTA** — メールアドレス入力 or 申し込みボタン（最小限）

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

- [ ] **スクロール視差**：HEROセクションの背景要素に transform のみを使った parallax
- [ ] **大型数字演出**：実績セクションの数値を Cormorant Garamond で全幅に近い巨大サイズで表示
- [ ] **縦書きアクセント**：writing-mode: vertical-rl でサービスコンセプトワードを右端に配置
- [ ] **フォリオ番号**：各セクション左端に 01 / 02 / 03 の印刷物的ナンバリング

---

## 補足指示

- CTAボタンはアクセントカラー背景 + 白文字（border-radius 4px 以下）
- プロダクト名は仮称「Veil」を使用（差し替え前提）
- コピーは英語と日本語を意図的に混在させる
- フッターはシンプルに：ロゴ + ナビ + コピーライトの1行のみ
