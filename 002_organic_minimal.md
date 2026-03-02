# プロンプト02｜Organic Minimal

## 改善バージョン（v2.0）

---

```
以下の要件に従って、ウェブページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ コンテンツ情報（必ず差し替えてください）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- ページタイトル（<title>タグ用）：[ページタイトル]
- H1見出し：[メインキャッチコピー]
- リード文：[2〜3文。サービス・人物・商品の説明]
- 特徴リスト：[特徴1] / [特徴2] / [特徴3]
- CTAボタンテキスト：[行動喚起テキスト]
- CTAリンク先URL：[URL または #]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ ページ構成（セクション定義）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
以下の順序でセクションを構築すること：

1. HERO（min-height: 90vh）
   - H1をイタリック体で左寄せ、全体の60%幅に収める
   - リード文はH1の右下にオフセット配置（margin-left: 30%程度）
   - 背景はリネンホワイト #FAF7F2 のみ、装飾なし

2. FEATURES（特徴リスト）
   - 3項目を縦に並べる（grid-template-columns: 1fr）
   - 各項目の間に border-bottom: 1px solid #D4CDC4; で区切る
   - 各項目に十分な上下余白（padding: 3rem 0）

3. CTA（センタリングブロック）
   - 背景色：テラコッタ #C87965
   - テキストは #FAF7F2（セピア系ホワイト）
   - ボタンはシンプルなアンダーラインリンク形式（枠なし）
   - padding: 6rem 2rem で余白を大きくとる

4. FOOTER
   - 極細ボーダー上部1本のみ（border-top: 1px solid #D4CDC4）
   - テキストはセージグリーン #8A9A86
   - padding: 4rem 2rem

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Cormorant Garamond + Zen Old Mincho）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止

【世界観】
- オーガニックコスメ / 植物園 / 静寂
- 「深呼吸したくなるような余白と、自然由来の温もり」
- キーワード：Botanical / Breathable Space / Quiet Luxury

【カラーパレット（HEXコードを厳守）】
- ページ背景：リネンホワイト #FAF7F2
- テキスト（メイン）：アースブラウン #4A3B32
- テキスト（サブ）：セージグリーン #8A9A86
- ボーダー：#D4CDC4（線幅は常に 1px）
- アクセント（CTA背景のみ）：テラコッタ #C87965
- 禁止色：#FFFFFF / #000000 / 彩度の高い原色 / グラデーション全般

【タイポグラフィ】
- H1：Cormorant Garamond / clamp(2.5rem, 5vw, 4.5rem) / font-style: italic / font-weight: 400 / line-height: 1.2
- H2（セクション見出し）：Zen Old Mincho / clamp(1rem, 2vw, 1.4rem) / font-weight: 400 / letter-spacing: 0.15em / text-transform: uppercase / color: #8A9A86
- 本文：Zen Old Mincho / 0.95rem / line-height: 2.2 / letter-spacing: 0.08em / color: #4A3B32
- CTAリンク：Cormorant Garamond / 1.2rem / font-style: italic / text-decoration: underline / text-underline-offset: 6px

【レイアウト原則】
- 最大コンテンツ幅：max-width: 900px; margin: 0 auto; padding: 0 2rem;
- セクション余白：padding: 8rem 2rem（最小）〜 padding: 12rem 2rem（HERO）
- テキストブロックは最大幅 60ch（文字数ベース）を超えないこと（max-width: 60ch）
- HEROのリード文オフセット：margin-left: clamp(2rem, 30%, 20rem)

【ボーダー設計】
- 使用する場所：FEATURESリスト区切り、FOOTER上部のみ
- 線幅は常に 1px、色は #D4CDC4
- border-radius は最大 2px。装飾目的のボーダーは使用禁止

【モーション・インタラクション】
- CTAリンク：hover時に color を #C87965 → #4A3B32 へ transition: 0.3s ease
- FEATURESリスト各項目：hover時に color: #4A3B32 → #C87965 へ transition: 0.3s ease
- スクロール連動：IntersectionObserver を使い、各セクションが画面内に入ったときに opacity: 0 → 1、transform: translateY(20px) → translateY(0) のフェードインを実装（transition: 0.8s ease）
- アニメーションは控えめに。派手な動きは世界観を壊すため禁止

【レスポンシブ設計（必須）】
- ブレークポイント：768px（タブレット）/ 480px（スマートフォン）
- 768px以下：HEROのリード文オフセット（margin-left）を 0 に戻し、左揃えに変更
- 480px以下：padding を 6rem 1.5rem に縮小、H1のclampを最小値優先
- FEATURESは全幅で縦積み（変更不要、元からgrid: 1fr）
- CTAセクションは全幅を維持

【アクセシビリティ（必須）】
- 全インタラクティブ要素に :focus-visible スタイルを設定（outline: 2px solid #C87965; outline-offset: 4px）
- カラーコントラスト比：#4A3B32 on #FAF7F2 はWCAG AA基準（4.5:1以上）に準拠（確認済み：約8:1）
- CTAリンクには aria-label を付与し、リンクの目的を明示
- フォームがある場合は label 要素を必ず使用

【完全禁止事項】
- 絵文字・FontAwesome等のアイコンフォント
- box-shadow の blur半径 8px 超
- border-radius 2px 超（角丸禁止）
- グラデーション全般
- 均等割りグリッドカード
- Inter / Roboto / Arial / system-ui フォント
- 背景への装飾画像・テクスチャ画像の使用
- アニメーションの連続ループ（世界観を損なうため）
```

---

## 改善ポイント解説

| 改善項目 | 旧バージョン | 新バージョン |
|---|---|---|
| セクション定義 | なし | Hero/Features/CTA/Footerを明示 |
| 余白指定 | `padding: 10rem以上` と曖昧 | 8rem〜12rem と範囲で明示 |
| CTA設計 | 完全欠落 | テラコッタ背景・アンダーラインリンク形式で定義 |
| オフセット実装 | 概念のみ | `clamp(2rem, 30%, 20rem)` と実装コードで指示 |
| モーション | 記載なし | IntersectionObserver + CSS transitionで定義 |
| レスポンシブ | 記載なし | 768px/480px ブレークポイント明示 |
| アクセシビリティ | 記載なし | WCAG AA・focus-visible・aria-label を追加 |
| border-radius | 16px以下と緩い | 2px以下に厳格化（Organicは角丸も最小限） |
