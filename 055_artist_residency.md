# プロンプト047｜Artist Residency HP — "Room to Make"

## 若手アーティスト向け｜クリエイター支援・アーティストレジデンスのHP

---

## ✅ 差分確認（既存44本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | アーティストレジデンス / クリエイター支援HP | 支援・滞在制作プログラム系は44本中ゼロ。最近接は026リクルート有機的だが、採用 vs 芸術支援は別文脈 |
| **カラー** | チョークホワイト + テラブラウン + スプリンググリーン | ベージュ×テラコッタは多数使用済み。本作は「古い校舎・アトリエ」感の #F5F0E8 ×テキスタイル感の緑 #3D6B4F を採用。既存のグリーン（#4A5C3A / #2E6B6B / #1A6640 / #2A7A3A / #2E7D32）と異なるミドルトーン |
| **フォント** | Bodoni Moda × Work Sans × Noto Sans JP | Bodoni Modaは44本中未使用（セリフ体でCormorant/Spectral/Caudex/Lora/Playfair等と差別化）。Work Sansも未使用 |
| **レイアウト** | タイムライン型縦走査レジデンシースケジュール + ホリゾンタルテープカット仕切り | タイムライン縦走査で「期間を体感させる」構成は44本中未使用 |
| **アニメーション** | スクロール連動の線描アニメーション（SVG stroke-dashoffset、pathを描く）+ テキストの文字単位スプリット出現 | stroke-dasharrayは022で使用済みだが、本作はdashoffset(path描画)で実装し区別。文字単位スプリットは全44本未使用 |
| **CSS装飾** | 紙テープ風の斜め切り仕切り（`clip-path: polygon(0 0, 100% 0, 100% 85%, 0 100%)`）+ 手書きSVG下線の常時表示 | 斜め切りseperatorsは全44本未使用 |

---

## 目的

若手・中堅アーティストを支援するレジデンスプログラム（滞在型制作支援）のHPトップページ。
「作ることのために、場所・時間・コミュニティがある」という安心と高揚を伝える。
応募を検討するアーティスト、支援者（財団・企業スポンサー）、メディアが主な読者。

> 参照世界観：ARCUS Project / Cité internationale des arts / 山中湖ALGAE 的な
> 「制作の真剣さと、人が交差する豊かさ」。アカデミックすぎず、トレンド追従でもない。
> 古いアトリエの日差しと、新しい思考の気配。

---

## フォント

```
- ブランド名・H1：Bodoni Moda / weight 400 Italic / size clamp(3rem, 7vw, 7rem)
  letter-spacing: 0.01em（Bodoni固有のエレガントなセリフを生かす）
- セクション見出し（英語）：Work Sans / weight 700 / size clamp(1.6rem, 3vw, 2.8rem)
  letter-spacing: -0.02em / text-transform: uppercase
- 本文・日本語：Noto Sans JP / weight 400 / size 0.92rem / line-height 2.2 / letter-spacing 0.07em
- ラベル・期間表記：Work Sans / weight 300 / size 0.68rem / letter-spacing 0.25em / uppercase
- アーティスト名：Bodoni Moda Italic / size 1.1rem
```

**禁止：Inter / Roboto / Cormorant Garamond / Playfair Display / Lora / Spectral / Fraunces / system-ui**

---

## カラー

```css
--bg:       #F5F0E8   /* チョークホワイト（石灰壁・キャンバスプライマー） */
--bg2:      #EDE5D8   /* アトリエフロア（少し暗いベージュ） */
--ink:      #1E1710   /* ほぼブラック（焦げ茶の深み） */
--mid:      #7A6E60   /* テキストの中間色 */
--green:    #3D6B4F   /* スプリンググリーン（窓から見える庭） */
--green-lt: #C8DDD0   /* グリーンの薄め（ホバー背景・バッジ） */
--line:     #D0C8BE   /* 仕切り線 */
--tape:     #F0D090   /* 養生テープ色（アクセント装飾）*/
```

**禁止：純白 / 純黒 / ネオン / グラデーション / ゴールド / ブルー系（世界観から逸脱）**

---

## レイアウト

### 基本原則
- コンテンツ幅：`max-width: 1080px; margin: auto;` / 左右 `padding: 0 6vw`
- グリッド比率：`7:5`（テキスト多め：ビジュアル）または `5:7`（ビジュアル強調）を交互に
- セクション区切り：斜め切り仕切り `clip-path: polygon(0 0, 100% 0, 100% calc(100% - 40px), 0 100%)` で --bg ↔ --bg2 を切り替え
- border-radius：最大 `4px`（アトリエ感 = 直線的だが完全に鋭利ではない）

### タイムライン（レジデンスプログラムスケジュール）
- 縦型タイムライン：中央に `2px solid var(--line)` の縦線
- 左右交互に月・イベント内容を配置
- 各ノード：`width: 12px; height: 12px; background: var(--green); border-radius: 50%` の丸印
- スクロールに連動してSVG縦線が上から下へ stroke-dashoffset で描かれる

### ホリゾンタルテープ装飾
- 見出しセクション前に `--tape` 色の養生テープ風水平帯（height: 8px / opacity: 0.7 / slight rotation: -0.3deg）
- ランダム配置感を演出（`:nth-child` で幅と位置を変える）

---

## セクション構成

```
1. HEADER（固定ナビ）
   - ロゴ（Bodoni Moda Italic / 左）/ テキストナビ / 「APPLY NOW」CTA（--green背景）
   - border-bottom: 1px solid var(--line) / 背景 --bg

2. HERO（全画面 / --bg背景）
   - 左下：プログラム名（H1 Bodoni Italic 大）+ タグライン（Work Sans）
   - 右：直近期のアーティスト作品プレースホルダー（縦長 3:4 / 斜め切りのframe）
   - 養生テープ装飾を左端に1本
   - 下部に「SCROLL TO EXPLORE ↓」を小さく（Work Sans 0.65rem / letter-spacing 0.3em）

3. ABOUT（斜め切り仕切り + --bg2背景）
   - 2カラム：左にコンセプト文 / 右にSVG描画アニメーション（家・スタジオの簡易図 or 抽象線画）
   - SVGはスクロールで stroke-dashoffset が描かれる

4. TIMELINE（レジデンスプログラムスケジュール）
   - 縦型タイムライン（中央縦線）× 年間スケジュール（6〜8ノード）
   - 縦線がスクロール連動でpath描画

5. RESIDENTS（過去参加アーティスト）
   - 非均等カード（3種類のサイズ混在）× 6〜9名
   - カードに：アーティスト名（Bodoni Italic）/ 出身国 / 制作ジャンル / 参加年
   - hover：--green-lt 背景に変化（0.3s ease）

6. STUDIO（スタジオ・設備紹介）
   - 左右交互 2カラム × 3セット（斜め切り仕切りで区切る）
   - アイコン禁止 → 設備名を大きく / 数値をWork Sansモノで表示

7. APPLY（応募案内）
   - --bg2 背景 / 斜め切り（逆方向: polygon(0 15%, 100% 0, 100% 100%, 0 100%)）
   - 応募条件リスト（Work Sans / 箇条書き風だがbullet禁止 → 左端に--greenの2px縦線で代替）
   - CTAボタン：--green 背景 / border-radius 4px / hover で --ink 背景に transition 0.4s

8. SUPPORTERS（支援者・パートナー）
   - ロゴグレースケール並び（hover でカラー復元）
   - 養生テープ装飾を見出し前に

9. FOOTER
   - アクセス / 問い合わせ先 / SNS
   - border-top: 2px solid var(--tape)（テープ色の太めライン）
```

---

## 必須ディテール（最低2つ実装）

- [ ] **SVGパス描画アニメーション**：ABOUT内のSVGスケッチがスクロールで `stroke-dashoffset: length → 0` へ（030のStrokeDasharrayとは異なる用途・描画演出）
- [ ] **タイムライン縦線描画**：縦SVG lineが上から下へ `stroke-dashoffset` で伸長（IntersectionObserver連動）
- [ ] **テキストスプリット出現**：H1の文字を `<span>` 単位に分割し、各文字が 0.03s ずつ遅れて `opacity: 0 → 1` と `letter-spacing: 0.3em → 0.01em` で出現（translateY禁止）
- [ ] **斜め切り仕切り**：セクション間に `clip-path: polygon(...)` で斜め切りの視覚的段差を作る

---

## アニメーション規則

```
OK：
  - stroke-dashoffset 描画アニメーション（path / line）
  - テキストスプリット（文字単位 opacity + letter-spacing 変化）
  - IntersectionObserver による1回限りのトリガー
  - hover: background / color 変化
  - filter: grayscale → grayscale(0) transition

禁止：
  - translateY（既存多用のため全禁止）
  - fadeInUp keyframes
  - グリッチ / カウントアップ
  - カスタムカーソル / 視差
  - clip-pathフィルアニメーション（040使用済み）
```

---

## 装飾ルール

```
OK：
  - clip-path: polygon() 斜め切り（セクション仕切り）
  - 養生テープ帯（--tape色 / height 6-10px / 微妙なrotation）
  - border: 1px solid var(--line)
  - border-left: 2px solid var(--green)（応募条件リストの代替bullet）
  - border-radius 最大 4px

禁止：
  - border-radius 4px超
  - box-shadow blur 8px超
  - グラデーション
  - SVGノイズテクスチャ（038使用済み）
  - 絵文字 / アイコンフォント
  - 均等カードグリッド（必ず非均等に）
```

---

## レスポンシブ設計

| ブレークポイント | 変更内容 |
|---|---|
| `1024px以下` | RESIDENTS カード：2カラムに縮小 |
| `768px以下` | ABOUT / STUDIO：1カラム縦積み / タイムライン：左端に縦線・全アイテム右側に配置（交互をやめる） |
| `480px以下` | 斜め切りの角度を `20px` に縮小 / テキストスプリットは無効化（パフォーマンス配慮）|

---

## コンテンツ変数（差し替えてください）

```
- プログラム名：[RESIDENCY NAME]
- タグライン：[2〜3文のコンセプト]
- 滞在期間：[XX weeks / XX months]
- 定員：[XX名 / 期]
- 提供内容：[スタジオ] / [宿泊] / [制作費補助] / [メンター制度]
- 過去参加アーティスト（6〜9名）：名前 / 出身 / ジャンル / 参加年
- 年間スケジュール（6〜8ノード）：日付 / イベント名
- 応募締め切り：[YYYY.MM.DD]
- 支援者・パートナー名（5〜8団体）
- 所在地 / アクセス
```

---

## 出力形式

```
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Bodoni Moda + Work Sans + Noto Sans JP）のみ
- 外部CSSライブラリ・UIフレームワーク一切禁止
- JavaScriptはIntersectionObserver + テキストスプリット分割のみ許可
```
