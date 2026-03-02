# プロンプト05｜Cinematic Noir

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

1. HERO（min-height: 100vh）
   - 背景：フィルムブラック #0A0A0B（ベタ塗りのみ）
   - 上下に padding: 12vh を設けてレターボックス感を演出
   - H1を中央揃えで配置（唯一の中央揃え許可箇所）
   - H1の下に border-bottom: 1px solid #333333; を挟み、リード文を配置
   - リード文は max-width: 50ch; margin: 0 auto; で中央に留める

2. FEATURES（特徴リスト）
   - 背景：#0A0A0B（統一）
   - 3項目を左寄せで縦積み配置
   - 各項目の左端にブラッドレッド #8A0303 の縦線（border-left: 1px solid #8A0303; padding-left: 2rem）
   - 各項目間の余白は padding: 4rem 0;
   - セクション上部に「——」区切り線（border-top: 1px solid #333333）

3. CTA（センタリングブロック）
   - 背景：#0A0A0B（統一、背景変化なし）
   - ボタンは border: 1px solid #E3DEC6; padding: 1.2rem 4rem; のアウトラインスタイル
   - ボタンテキスト：セピアホワイト #E3DEC6 / Caudex / letter-spacing: 0.2em / uppercase
   - hover時：background: #E3DEC6; color: #0A0A0B; transition: 0.3s ease
   - ボタンの上下に広い余白（padding: 10vh 0）

4. FOOTER
   - 背景：#0A0A0B（統一）
   - border-top: 1px solid #333333;
   - テキスト：アッシュグレー #7A7669 / font-size: 0.75rem / letter-spacing: 0.1em
   - padding: 4rem 0; で下部にも余白を確保

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Caudex + Shippori Mincho）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止

【世界観】
- フィルムノワール / アート系映画ポスター / モノクロームの緊張感
- 「光と深い影、ドラマチックな緊張感を持たせたシネマティックな空間」
- キーワード：Monochromatic Drama / Wide Aspect / Whispering Text

【カラーパレット（HEXコードを厳守）】
- ページ背景：フィルムブラック #0A0A0B（全セクション統一、背景色の変化禁止）
- テキスト（メイン）：セピアホワイト #E3DEC6
- テキスト（サブ）：アッシュグレー #7A7669
- ボーダー：#333333（使用は最小限。線幅は常に 1px）
- アクセント（FEATURESの縦線のみ）：ブラッドレッド #8A0303
- 禁止色：#FFFFFF / #000000 / 彩度の高い原色 / グラデーション全般

【タイポグラフィ】
- H1：Caudex / clamp(2.2rem, 4.5vw, 4rem) / font-weight: 400 / letter-spacing: 0.2em / text-transform: uppercase / line-height: 1.3
- H2（セクション見出し）：Caudex / 0.7rem / font-weight: 400 / letter-spacing: 0.3em / text-transform: uppercase / color: #7A7669
- 本文：Shippori Mincho / 0.9rem / line-height: 2.6 / letter-spacing: 0.06em / color: #7A7669
- CTAボタン：Caudex / 0.85rem / letter-spacing: 0.25em / text-transform: uppercase / color: #E3DEC6
- FEATURES特徴テキスト：Shippori Mincho / 1rem / line-height: 2.2 / color: #E3DEC6（他の本文より明るく強調）

【レイアウト原則】
- コンテンツ最大幅：max-width: 680px; margin: 0 auto; padding: 0 2rem;
- セクション余白：padding: 10vh 2rem（最小） 〜 padding: 15vh 2rem（HERO）
- HERO・CTAは中央揃え（text-align: center）を使用（例外的に許可）
- FEATURESは text-align: left; を維持（左寄せ）
- 「暗闇」を強調するため、コンテンツ領域はあえて画面幅の50〜60%に留める

【ボーダー設計】
- ページ全体で border を多用しない（1px / #333333 を上限として最小限に留める）
- FEATURESの縦線：border-left: 1px solid #8A0303;（これのみブラッドレッドを使用）
- セクション区切り：border-top: 1px solid #333333;
- CTAボタン枠：border: 1px solid #E3DEC6;
- border-radius は最大 0px（角丸完全禁止）

【モーション・インタラクション】
- ページロード：ページ全体を opacity: 0; から opacity: 1; へ 1.2s ease で緩やかにフェードイン（映画の暗転明けを演出）
- FEATURESの縦線：初期状態 height: 0; → height: 100%; transition: 0.6s ease（スクロール進入時に線が伸びる）
- CTAボタン：hover時に background: transparent → #E3DEC6; color: #E3DEC6 → #0A0A0B; transition: 0.3s ease
- スクロール連動（IntersectionObserver）：各セクションが画面内に入ったときに opacity: 0; → opacity: 1; transition: 1.0s ease（テキストが霧の中から現れる演出）
- カーソル：cursor: crosshair; をbodyに適用（映画のクロスヘアを模倣）

【レスポンシブ設計（必須）】
- ブレークポイント：768px（タブレット）/ 480px（スマートフォン）
- 768px以下：max-width を 100% に解除、padding を 0 1.5rem に縮小
- 480px以下：H1のletter-spacingを 0.1em に縮小（過度な字間がレイアウトを崩すため）
- 全セクションで背景色 #0A0A0B を維持（モバイルでもダークモード統一）
- CTAのpadding: 8vh 1.5rem に縮小

【ライトモード非対応の明示】
- prefers-color-scheme: light への対応は不要
- OSのカラーモード設定に関わらず、常に #0A0A0B のダークモードで表示
- <meta name="color-scheme" content="dark"> を <head> 内に必ず記述

【アクセシビリティ（必須）】
- 全インタラクティブ要素に :focus-visible スタイルを設定（outline: 1px solid #E3DEC6; outline-offset: 6px）
- カラーコントラスト比：#E3DEC6 on #0A0A0B はWCAG AA基準（4.5:1以上）に準拠（確認済み：約10:1）
- アッシュグレー #7A7669 on #0A0A0B のコントラスト比は約3.8:1のため、本文（サブ）用途のみに限定し、重要情報はセピアホワイトを使用
- ページロードのフェードインはprefers-reduced-motion: reduce メディアクエリで無効化する

【完全禁止事項】
- 絵文字・FontAwesome等のアイコンフォント
- box-shadow（完全禁止、ノワールの闇を薄める）
- border-radius（完全禁止）
- グラデーション全般
- 背景色の変化（全セクション #0A0A0B 統一）
- カラフルな装飾・明るいカラーパレット
- Inter / Roboto / Arial / system-ui フォント
- アニメーションの高速化・派手な動き（world観を損なう）
```

---

## 改善ポイント解説

| 改善項目 | 旧バージョン | 新バージョン |
|---|---|---|
| セクション定義 | なし | Hero/Features/CTA/Footerを明示 |
| 「テキストは小さめに」 | 数値根拠なく抽象的 | 0.9rem / 0.85rem と数値で定義 |
| CTA設計 | 完全欠落 | アウトラインボタン + 余白設計を明示 |
| レターボックス実装 | 概念のみ | `padding: 12vh` と数値で指定 |
| モーション | 記載なし | 暗転明けフェードイン・縦線伸長を定義 |
| レスポンシブ | 記載なし | 768px/480px ブレークポイント明示 |
| ライトモード対応 | 記載なし | 非対応を明示 + `color-scheme: dark` を指示 |
| アクセシビリティ | 記載なし | #7A7669のコントラスト限界を明記・reduced-motion対応 |
| カーソル演出 | 記載なし | cursor: crosshair でシネマ感を追加 |
