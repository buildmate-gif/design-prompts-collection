# プロンプト045｜Contemporary Art Gallery — "The White Cube, Unfolded"

## コレクター・美術ファン向け｜現代アートギャラリーHP

---

## ✅ 差分確認（既存44本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | 現代アートギャラリーHP | ギャラリー・美術館サイトは44本中ゼロ（最近接は006ポートフォリオダークだが、個人 vs 機関という別文脈） |
| **カラー** | ピュアホワイト軸 + ウルトラマリン + チャコールブラック | ホワイト主体の潔癖なホワイトキューブ系パレットは未使用。ウルトラマリン #2B45C8 はブルー系統で未使用色域 |
| **フォント** | PP Neue Montreal (Gmarket Sans代替) × Instrument Serif × Noto Sans JP | この3本の組み合わせは未使用。セリフ×サンセリフのコントラスト設計が既存と異なる |
| **レイアウト** | スタック型フルスクリーン縦走査（各展示作品が1ビューポート＝1作品） | 既存に「作品1点＝1スクリーン」のフルスクリーンスタックレイアウトなし |
| **アニメーション** | スクロール連動の作品番号カウンター（固定サイドバー）+ 水平スライン出現 | サイドに固定した「作品進捗インジケーター」は未使用。横線のslide-inはscaleXと異なるleft→rightのwidthアニメーション |
| **CSS装飾** | mix-blend-mode: multiply による色重ね / letter-spacing 極限緩め / caption フローティングテキスト | mix-blend-mode活用は44本中未使用 |

---

## 目的

現代アートギャラリーのコーポレートサイト（トップページ）。
「ホワイトキューブを、デジタルに展開する」——物理的なギャラリー空間の静けさ・緊張感・知的な余白を
ウェブ上で再現する。コレクターや美術ファン、プレスが訪れる高品質なポータル。

> 参照世界観：David Zwirner / Hauser & Wirth / Pace Gallery の公式サイト的な気品と、
> Dries Van Noten的な「言葉を尽くさない信頼」。

---

## フォント

```
- ギャラリー名・H1：Instrument Serif / weight 400 (Regular) / Italic使用可
  size: clamp(3.5rem, 7vw, 8rem) / letter-spacing: 0.02em
- セクション番号・ラベル：Gmarket Sans (代替: Barlow) / weight 300
  size: 0.65rem / letter-spacing: 0.4em / uppercase / color: アクセント
- 本文・説明文：Noto Sans JP / weight 300 / size: 0.9rem / line-height: 2.3 / letter-spacing: 0.08em
- 作品キャプション：Instrument Serif Italic / size: 0.85rem / color: #6A6A6A
```

**禁止：Inter / Roboto / Arial / Syne / Cormorant Garamond / Playfair Display / system-ui**

---

## カラー

```css
--bg:        #FAFAFA   /* ホワイトキューブ白（純白禁止・わずかにウォーム） */
--ink:       #111111   /* ほぼブラック（pure #000000は禁止） */
--mid:       #6A6A6A   /* キャプション・補足テキスト */
--rule:      #D8D8D8   /* ルール線（極細1px） */
--ultra:     #2B45C8   /* ウルトラマリン（アクセント・1ページ最大3回） */
--ultra-dim: #E8ECF8   /* ウルトラマリン薄め（ホバー背景） */
```

**禁止：グラデーション全般 / ベージュ系（既存で多用済み）/ ゴールド系 / テラコッタ系 / 蛍光色**
**許可：mix-blend-mode: multiply による色の重なり表現**

---

## レイアウト

### 基本原則
- **1作品 = 1スクリーン** スタック型レイアウト（展示ウォーク体験の再現）
- section height: 100vh × 作品数（スクロールで作品を"歩く"）
- 余白は最低限 `padding: 0 10vw`（左右の壁）
- グリッドは使わない：各スクリーンはabsolute/fixedによる精密配置
- テキストと画像の overlap は意図的に「ラベルが画像に食い込む」形で1〜2箇所

### サイドバー（固定）
- 右端に `position: fixed` で縦配置の展示番号インジケーター
- 現在のスクリーン番号がウルトラマリンで点灯（JS: IntersectionObserver）
- `writing-mode: vertical-rl` は既存使用済みのため **禁止** → 代わりに縦並びdot + 数字

---

## セクション構成

```
1. HEADER（固定ナビ）
   - ギャラリー名（左）+ ナビリンク（中）+ "VISIT / CONTACT"（右）
   - border-bottom: 1px solid var(--rule) / 背景なし（透過）
   - スクロール後に白背景が0.3sでfade-in

2. ENTRY（全画面Hero）
   - ギャラリー名：Instrument Serif 大 / 左寄せ / 下方
   - 現在開催中の展覧会タイトルを右上に浮かせる（position: absolute）
   - 背景：白のみ（画像なし）/ 空間の緊張を余白で表現

3. NOW ON VIEW（スタック型 × 展示作品数分）
   - 各スクリーン：左60%に作品プレースホルダー / 右に作品情報
   - 作品タイトル：Instrument Serif Italic / 大きめ
   - アーティスト名・年・素材：ラベルフォーマット（0.65rem / letter-spacing: 0.3em）
   - 画像下に細い線が左→右へ伸びる（widthアニメーション: 0→100%, 0.8s ease）

4. UPCOMING（次回展示告知）
   - 全面ウルトラマリン背景（--ultra）/ テキストは白
   - このセクションのみ背景色あり（コントラストで緊張を作る）
   - 開幕日のカウントダウンなし（代わりに「OPENING XX.XX.XXXX」表記）

5. ARTISTS（在籍アーティスト）
   - 名前のみをタイポグラフィ的に並べるグリッド（画像なし）
   - hover時：名前に下線が左から伸び、右に小さな矢印が出現

6. ABOUT / PRESS
   - 2カラム: テキスト（左）+ 受賞・掲載メディアロゴ（右、グレースケール）

7. FOOTER
   - ギャラリー住所 / 開館時間 / SNS
   - border-top: 1px solid var(--rule)
```

---

## 必須ディテール（最低2つ実装）

- [ ] **スクロール連動インジケーター**：右固定サイドバーのdotがウルトラマリンで点灯（IntersectionObserver）
- [ ] **Widthアニメーション細線**：各作品スクリーンに入った瞬間、作品下のルール線がwidth:0→100%へ伸長（0.8s ease-out）
- [ ] **mix-blend-mode重ね**：ウルトラマリン背景セクションで白テキストをmix-blend-mode: overlayでわずかに溶け込ませる
- [ ] **ナビ遅延fader**：スクロール開始後50px経過でheaderに `background: rgba(250,250,250,0.95)` が 0.3s でfade-in

---

## アニメーション規則

```
OK：
  - widthアニメーション（0 → 100%, ease-out）
  - opacity fade（0 → 1, 1.0s, ease）
  - IntersectionObserver によるクラス付与
  - mix-blend-mode の静的使用
  - hover: color変化 / underline展開（既存はscaleX = transform軸。本作はwidthで実装し区別）

禁止：
  - translateY（既存多用のため完全禁止）
  - グリッチ / カウントアップ / 視差
  - カスタムカーソル
  - keyframes fadeInUp
```

---

## 装飾ルール

```
OK：
  - border: 1px solid var(--rule)（極細）
  - mix-blend-mode: multiply / overlay
  - letter-spacing: 0.4em 以上のエクストリーム緩め（ラベル系のみ）
  - ネガポジ反転セクション（ウルトラマリン背景）

禁止：
  - box-shadow（全て禁止）
  - border-radius（全て禁止・ギャラリー空間に曲線なし）
  - 背景画像・テクスチャ
  - SVGノイズ
  - グラデーション
  - 絵文字・アイコンフォント
```

---

## レスポンシブ設計

| ブレークポイント | 変更内容 |
|---|---|
| `1024px以下` | 右サイドインジケーターを非表示 / 左右パディングを 6vw に縮小 |
| `768px以下` | NOW ON VIEW：1カラム（作品上・テキスト下に積み替え） / UPCOMING：余白50%縮小 |
| `480px以下` | H1 clampの最小値優先 / ARTISTS：2カラム名前リスト |

---

## コンテンツ変数（差し替えてください）

```
- ギャラリー名：[GALLERY NAME]
- 現在の展覧会タイトル：[EXHIBITION TITLE]
- アーティスト名：[ARTIST NAME]
- 会期：[YYYY.MM.DD — YYYY.MM.DD]
- 作品3点（タイトル / 制作年 / 素材 / サイズ）
- 在籍アーティスト名（6〜12名）
- ギャラリー住所 / 開館時間
- 次回展示開幕日
```

---

## 出力形式

```
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Instrument Serif + Noto Sans JP）のみ
- 外部CSSライブラリ・UIフレームワーク一切禁止
- JavaScriptはIntersectionObserverとスクロールイベントのみ許可
```
