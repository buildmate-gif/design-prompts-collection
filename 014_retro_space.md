# Scene D — Retro Future Space UI
## 1970年代NASAポスター × SF映画 ランディングページ

---

## 目的・コンテキスト

宇宙開発スタートアップまたは科学技術系イベントの告知LPを生成してください。
1970〜80年代のNASAポスター・ソビエト宇宙開発プロパガンダ・2001年宇宙の旅——
「未来を信じていた時代の美学」を現代のWebに蘇らせます。
幾何学的な完璧さ・オレンジと黒のコントラスト・宇宙の広大さと孤独感を共存させてください。

---

## 出力形式

- HTML + CSS（単一ファイル）
- Google Fonts：Orbitron / Exo 2 / Share Tech Mono など宇宙・SF系フォント
- JavaScript：軌道アニメーション（CSS keyframes）+ カウントダウン

---

## 世界観・トーン

- ミッションブリーフィングルームの空気
- 「人類はまだ諦めていない」という静かな高揚感
- キーワード：Retro / Cosmic / Mission / Orbit / Horizon

---

## カラーパレット

- ベース：宇宙の深黒 #0A0A08 / 深宇宙 #141210
- テキスト：ミッションオレンジ #E8640A / スターホワイト #EDE8DC
- アクセント（2色まで許容）：レーダーグリーン #2E7D32 / スペースゴールド #C8960A
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止
- ※ オレンジは「灼熱の大気圏再突入」のような深みを持つトーンにすること

---

## タイポグラフィ

- 見出し（H1/ミッション名）：Orbitron
  - font-size: clamp(2rem, 6vw, 5.5rem)
  - letter-spacing: 0.15em / font-weight: 700 / text-transform: uppercase
- サブ見出し（H2）：Exo 2 / font-size: clamp(1rem, 2.5vw, 1.8rem) / letter-spacing: 0.1em
- 本文（body）：Share Tech Mono または Exo 2
  - font-size: 0.9rem / line-height: 1.8 / letter-spacing: 0.05em
- データ・座標値：Share Tech Mono / font-size: 0.75rem / color: アクセントカラー
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- アシンメトリー必須：左右に異なる「重力」を持たせる配置
- section padding：最低 8rem（モバイル 4rem）
- 幾何学的要素（同心円・グリッド線・放射状ライン）をCSSで描画
- テキストと幾何学図形の overlap を2箇所以上
- 細い点線ボーダー（border: 1px dashed rgba(232,100,10,0.3)）で「計測グリッド」を表現

---

## 構成セクション

1. **MISSION BRIEF** — ミッション名（ALL CAPS）+ 打ち上げカウントダウン + 座標データ風テキスト
2. **OBJECTIVE** — ミッションの目的（左: データパネル / 右: 巨大な同心円グラフィック）
3. **TIMELINE** — 垂直タイムライン（点線 + 年号 + 短いメモ）
4. **CREW / TEAM** — チームメンバー（非均等グリッド・モノクロプレースホルダー）
5. **LAUNCH CTA** — 「LAUNCH SEQUENCE INITIATED」風のボタン + カウントダウン再表示

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

- [ ] **軌道アニメーション**：CSSのみで同心円上を点が周回する軌道アニメーション（animation: orbit）
- [ ] **打ち上げカウントダウン**：T-MINUS XX:XX:XX 形式のリアルタイムカウントダウン（Share Tech Mono）
- [ ] **スキャンライン効果**：背景に薄い横線（repeating-linear-gradient）でCRTモニター感を演出
- [ ] **座標テキスト**：緯度・経度・高度の架空データをページ各所に小さく散りばめる（opacity 0.3〜0.4）

---

## 補足指示

- ミッション名は仮称「MISSION: HORIZON VII」を使用
- データ・座標はすべて架空の数値
- コピーは英語主体（日本語サブテキストを一部混在させる）
- 背景に極めて薄い星フィールド（CSSのbox-shadowで点を散りばめる）を実装
- ボタンは「INITIATE」「CONFIRM」等のミッション語彙を使用
