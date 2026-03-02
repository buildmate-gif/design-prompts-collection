# Scene A — Brutalist Dashboard
## 荒削り・工業的・データ主役UI

---

## 目的・コンテキスト

データ分析ツールまたは開発者向けモニタリングダッシュボードを生成してください。
「美しく整える」ことを一切せず、情報の密度と構造の剥き出しの美学を追求します。
ブルータリスト建築のように「素材そのものを見せる」UIを設計してください。
訪問者が「これは本物の道具だ」と感じる実用性の緊張感を最優先とします。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts：モノスペースフォントのみ（Roboto Mono / Space Mono / JetBrains Mono）
- JavaScript：リアルタイム風のデータ更新アニメーション（数値のカウントアップ等）

---

## 世界観・トーン

- Unix端末 × コンクリート打ち放し
- 装飾は一切施さない——構造が装飾になる
- キーワード：Raw / Grid / Brutal / Density / System

---

## カラーパレット

- ベース：コンクリートグレー #2C2C2C / チャコール #1A1A1A
- テキスト：ライムグリーン #39FF14（ターミナル発光色）/ オフホワイト #E8E8E8
- アクセント（2色まで許容）：ウォーニングイエロー #F5C400 / エラーレッド #CC2200
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止
- ※ グリーンは「発光」ではなく「くすみ」を意識したトーンに調整すること

---

## タイポグラフィ

- 全フォント：JetBrains Mono または Space Mono（モノスペース統一）
- 見出し（H1）：font-size: clamp(1.2rem, 2.5vw, 2rem) / font-weight: 700 / text-transform: uppercase
- データ数値：font-size: clamp(2rem, 5vw, 4rem) / font-weight: 400 / letter-spacing: -0.02em
- ラベル・キャプション：font-size: 0.65rem / letter-spacing: 0.1em / text-transform: uppercase
- ※ セリフ体・装飾フォント完全禁止
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- アシンメトリー必須：データパネルのサイズを意図的に不揃いにする
- section padding：最低 1rem（余白は最小限——密度を上げる）
- 太いボーダーライン（border: 3px solid #E8E8E8）でパネルを区切る
- グリッド線が見えることを「デザインの一部」として積極的に活用
- テキストと要素の overlap を1箇所以上

---

## 構成セクション

1. **HEADER BAR** — システム名（ALL CAPS） + 現在時刻（リアルタイム） + ステータスインジケーター
2. **KEY METRICS** — 4つの大型数値パネル（非均等サイズ）+ ブリンクするアラート
3. **DATA STREAM** — ターミナル風ログ出力エリア（疑似リアルタイムスクロール）
4. **GRID CHARTS** — ASCIIアート風バーチャートまたはCSSのみのグラフ
5. **SYSTEM STATUS** — テーブル形式のステータス一覧（border-collapseで区切り線むき出し）

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

- [ ] **ターミナルブリンク**：カーソルのブリンクアニメーション（点滅 0.8s step-end）をヘッダーおよびログエリアに実装
- [ ] **リアルタイム時計**：JavaScript で秒単位更新するデジタル時計（モノスペース）
- [ ] **カウントアップ数値**：ページロード時に0から目標値までアニメーションするメトリクス数値
- [ ] **ASCIIボーダー装飾**：パネルの角や区切りに手打ち風ASCII文字（+---+）を使った装飾

---

## 補足指示

- システム名は仮称「CORE/SYS」を使用
- データはすべて架空の数値で構わない
- 日本語テキストは最小限（ラベル類のみ）——英語・数値主体
- ローディング演出（progress bar）を1箇所入れること
- モバイル対応：パネルを縦積みにするだけでよい（スマホでも「道具感」を維持）
