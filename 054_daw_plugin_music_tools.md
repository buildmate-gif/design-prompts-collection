# プロンプト046｜DAW Plugin & Music Tools LP — "Signal Chain"

## 音楽制作者・クリエイター向け｜DAWプラグイン・音楽ツールのLP

---

## ✅ 差分確認（既存44本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | DAWプラグイン・音楽ソフトウェアのLP | 音楽ツール・プラグインのLPは44本中ゼロ（024はコンサートイベントポスター = 別物） |
| **カラー** | ディープミッドナイトネイビー + シグナルオレンジ + ウォームオフブラック | ネイビー主体は004スイスグリッドがレッド×ネイビー系だが、#05091A の深いミッドナイトは未使用。オレンジ #FF6820 も既存オレンジ（#C45C1A, #E87B52）と異なるビビッド域 |
| **フォント** | Geist Mono (代替: Azeret Mono) × Plus Jakarta Sans × Noto Sans JP | テクノロジー×可読性のこの3本セットは未使用。モノスペースはJetBrains/Space/Roboto Mono使用済みのため Azeret Mono を採用 |
| **レイアウト** | 音響波形を模したSVGビジュアライザー帯レイアウト（装飾兼インフォグラフィック） | 波形ビジュアライザーをレイアウト要素として使うパターンは44本中未使用 |
| **アニメーション** | CSS @keyframes による波形アニメーション（sin波の棒グラフアニメ）+ ツールチップ出現（scale + opacity, transformOrigin: bottom） | 棒グラフ波形のCSSアニメーションは未使用。ツールチップのtransformOrigin指定も未使用 |
| **CSS装飾** | `clip-path: polygon()` によるダイヤモンド/角切りカード（border-radiusゼロ×非矩形） | clip-pathは040でfill用途に使用済みだが、カード形状のclip-pathは未使用 |

---

## 目的

音楽制作者（DTMer・トラックメイカー・エンジニア）向けのDAWプラグインまたは音楽制作ツールのLP。
「機材オタクが唸るスペックと、クリエイターの感性に刺さるビジュアル」を両立させる。
プロフェッショナルな音楽制作環境を連想させる、ダーク×エッジ×テクニカルな世界観。

> 参照世界観：iZotope / Soundtheory Gullfoss / Arturia のプロダクトページ的な
> 「テクノロジーが音楽を拡張する」という高揚感。

---

## フォント

```
- プロダクト名・H1：Plus Jakarta Sans / weight 800 / size clamp(3rem, 7vw, 7.5rem)
  letter-spacing: -0.04em / text-transform: uppercase
- スペック値・数値：Azeret Mono / weight 500 / size varies / color: シグナルオレンジ
- セクション見出し：Plus Jakarta Sans / weight 700 / size clamp(1.8rem, 3vw, 3rem)
- 本文：Noto Sans JP / weight 400 / size 0.92rem / line-height 1.9 / letter-spacing 0.04em
- ラベル・タグ：Azeret Mono / size 0.68rem / letter-spacing 0.2em / uppercase / color: --orange
```

**禁止：Inter / Roboto / Syne / Bebas Neue / Space Mono / JetBrains Mono / Outfit / system-ui**

---

## カラー

```css
--bg:      #05091A   /* ディープミッドナイトネイビー（スタジオの闇） */
--surface: #0D1428   /* カード・パネル背景 */
--panel:   #141C38   /* インナーパネル（UIコンポーネント風） */
--ink:     #E8EAF0   /* メインテキスト（ほぼ白） */
--mid:     #7A82A0   /* サブテキスト・キャプション */
--orange:  #FF6820   /* シグナルオレンジ（アクセント・CTA・波形） */
--orange2: #FF9558   /* オレンジライト（ホバー / グロー用） */
--line:    #1E2847   /* 区切り線 */
```

**禁止：グラデーション（linear/radial全般）/ 白（純白）/ ゴールド / グリーン系**
**例外許可：--orange に対するわずかな filter: drop-shadow（blur 8px以内）のみ**

---

## レイアウト

### 基本原則
- **ダークUI**：全セクション `--bg` ベース。背景色の変化は `--surface` / `--panel` の3段階のみ
- グリッド：12カラム（均等禁止）/ 主に `7:5` または `8:4` 比率
- カード形状：`clip-path: polygon(0 0, 100% 0, 100% calc(100% - 16px), calc(100% - 16px) 100%, 0 100%)` による右下角切りデザイン
- CTA：フルブリード帯（`--orange` 背景）/ テキストは `--bg`

### 波形ビジュアライザー帯
- HEROとFEATURES間にSVG波形バーのアニメーション帯（height: 80px）を挿入
- 60本の棒グラフがCSSアニメーションで独立した高さを往復（各barに異なる animation-duration: 0.6s〜1.4s）
- 色：--orange（中央付近のbarのみ）それ以外は --line

---

## セクション構成

```
1. HEADER（固定ナビ）
   - ロゴ（左）/ ナビリンク / 「GET PLUGIN」CTAボタン（--orange背景 / clip-path角切り）
   - 背景：--bg / border-bottom: 1px solid var(--line)

2. HERO（全画面）
   - 左側：プロダクト名（H1大）/ キャッチコピー / 対応DAW一覧タグ / CTAボタン×2
   - 右側：プラグインUIスクリーンショット プレースホルダー（aspect-ratio 4:3 / panel背景）
   - プレースホルダー内にUIコンポーネント風の擬似画面（Azeret Monoで数値表示）

3. 波形ビジュアライザー帯（セクション区切り兼装飾）

4. FEATURES（主要機能紹介）
   - 3機能を非均等グリッド（5fr / 7fr / 5fr ではなく 7fr / 5fr の2段）
   - 各カード：clip-path角切り + panel背景 + オレンジのライン装飾
   - スペック数値をAzeret Monoで大きく表示（例：「48kHz / 32-bit Float」）

5. SPEC TABLE（スペック表）
   - 罫線のみのテーブル（背景色なし）
   - 行ホバー：background が --panel に変化（0.15s ease）
   - 重要値のみ --orange でカラーリング

6. WORKFLOW（使用シーン / ワークフロー）
   - 左右交互2カラム（テキスト / ビジュアル）× 3セット
   - 既存021と区別：画像はstickyではなく、テキストと同時にフェード

7. PRICING（ライセンス）
   - 2〜3プラン / clip-path角切りカード
   - 推奨プラン：--orange ボーダー（2px）で強調（既存029はダーク反転 = 別手法）

8. DAW COMPATIBILITY（対応環境）
   - 対応DAWロゴのグレースケールバー（hover でカラー復元）

9. CTA（フルブリード）
   - --orange 背景 / H2 + ボタン

10. FOOTER
    - 最小限 / --surface 背景 / Azeret Monoでバージョン情報
```

---

## 必須ディテール（最低2つ実装）

- [ ] **波形アニメーション**：SVG + CSSで60本のbarsが独立した周期でheightを往復（`@keyframes wave-bar { 0%,100%{height:8px} 50%{height:48px} }` + 個別duration）
- [ ] **clip-path角切りカード**：全カードに `clip-path: polygon(...)` 右下カット適用
- [ ] **スペックツールチップ**：FEATURES内の数値にhoverでツールチップ出現（`transform: scale(0.8) translateY(4px) → scale(1) translateY(0)` / `transform-origin: bottom center`）
- [ ] **DAWロゴのグレースケール復元**：hover時 `filter: grayscale(0)` へ 0.3s transition

---

## アニメーション規則

```
OK：
  - @keyframes 波形（height変化）— 本作固有
  - scale + opacity（ツールチップ）— transform-originを指定し既存と区別
  - filter: grayscale transition
  - IntersectionObserver による1回限りのフェード（opacity: 0 → 1, 0.8s）
  - hover: background color変化

禁止：
  - translateY（既存多用のため禁止）
  - グリッチ
  - カウントアップ（025で使用済み）
  - clip-pathフィルアニメーション（040使用済み）
  - カスタムカーソル（036使用済み）
  - 視差
```

---

## 装飾ルール

```
OK：
  - clip-path: polygon() 角切り形状
  - border: 1px solid var(--line) または 2px solid var(--orange)
  - filter: drop-shadow（blur 8px以内、--orangeのみ）
  - Azeret Monoによるモノスペース数値表示

禁止：
  - border-radius（全禁止 / エッジの世界観）
  - box-shadow（drop-shadowで代替）
  - background-image / SVGテクスチャ
  - グラデーション
  - 絵文字・FontAwesome
```

---

## レスポンシブ設計

| ブレークポイント | 変更内容 |
|---|---|
| `1024px以下` | HERO：縦積み（テキスト上 / UI画面下）/ FEATURES：1カラム |
| `768px以下` | 波形バー本数を60本→30本に削減 / テーブル横スクロール許可 |
| `480px以下` | PRICING：1カラム縦積み / clip-pathの角切りサイズを8pxに縮小 |

---

## コンテンツ変数（差し替えてください）

```
- プロダクト名：[PLUGIN NAME]（例：SURGE / NOVA / ATLAS）
- キャッチコピー：[2行以内のコピー]
- 対応DAW：[Ableton Live / Logic Pro / Cubase / FL Studio ...]
- 主要機能3点：[機能名] / [スペック値] / [説明1〜2文]
- 価格プラン（2〜3段階）：[プラン名] / [価格] / [含まれる機能]
- 対応OS / CPU / RAM要件
- バージョン番号：[v X.X.X]
```

---

## 出力形式

```
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Plus Jakarta Sans + Azeret Mono + Noto Sans JP）のみ
- 外部CSSライブラリ・UIフレームワーク一切禁止
- JavaScriptはIntersectionObserver + ツールチップ制御のみ許可
```
