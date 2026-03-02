# プロンプト04｜Swiss Grid / Typographic

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

1. HEADER（固定ナビゲーション）
   - 高さ：60px
   - 左：ロゴテキスト（Space Grotesk / font-weight: 700）
   - 右：CTAテキストリンク（インターナショナルレッド #DA291C）
   - 下部に border-bottom: 1px solid #050505;
   - position: sticky; top: 0; z-index: 100; background: #FDFDFD;

2. HERO（min-height: 85vh）
   - display: grid; grid-template-columns: 1fr 3fr;（1:3の非対称配置）
   - 左カラム：縦書き風のラベルテキスト（transform: rotate(-90deg)）
   - 右カラム：H1極大表示 + リード文（max-width: 55ch）
   - H1とリード文の間に border-bottom: 1px solid #888888; を挟む

3. FEATURES（特徴リスト）
   - display: grid; grid-template-columns: 2fr 4fr 2fr;（2:4:2の非対称3カラム）
   - 左カラム：連番（01/02/03）とラベル
   - 中央カラム：特徴テキスト（本文サイズ）
   - 右カラム：空白（意図的な余白として活用）
   - 各行は border-top: 1px solid #050505; で区切る

4. CTA（フルウィズブロック）
   - 背景色：インターナショナルレッド #DA291C
   - テキスト・ボタン：#FDFDFD
   - ボタン：border: 2px solid #FDFDFD; padding: 1rem 3rem; border-radius: 0;
   - hover時：background: #FDFDFD; color: #DA291C;

5. FOOTER
   - display: grid; grid-template-columns: 3fr 1fr;（3:1の非対称配置）
   - border-top: 2px solid #050505;
   - テキスト：スチールグレー #888888 / font-size: 0.8rem

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Space Grotesk + M PLUS 1p）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止

【世界観】
- スイス・スタイル / 国際タイポグラフィー様式 / ヘルベチカの美学
- 「数学的なグリッドと極端なフォントサイズ比率による、究極の機能美」
- キーワード：Strict Grid / High Contrast / Information Design

【カラーパレット（HEXコードを厳守）】
- ページ背景：スノーホワイト #FDFDFD
- テキスト（メイン）：ジェットブラック #050505
- テキスト（サブ）：スチールグレー #888888
- ボーダー：#050505（線幅 1px〜2px）
- アクセント（CTAおよびH2のみ）：インターナショナルレッド #DA291C
- 禁止色：純白 #FFFFFF / 純黒 #000000 / 原色（赤以外） / グラデーション全般

【タイポグラフィ】
- H1：Space Grotesk / clamp(3.5rem, 8vw, 7rem) / font-weight: 700 / letter-spacing: -0.04em / line-height: 0.95
- H2（セクション見出し）：Space Grotesk / 0.75rem / font-weight: 600 / letter-spacing: 0.15em / text-transform: uppercase / color: #DA291C
- 連番ラベル：Space Grotesk / clamp(0.7rem, 1vw, 0.85rem) / font-weight: 600 / letter-spacing: 0.1em / color: #888888
- 本文：M PLUS 1p / 0.9rem / line-height: 1.6 / font-weight: 400 / color: #050505
- フッター：M PLUS 1p / 0.75rem / color: #888888

【グリッドシステム（必須）】
- ベースグリッド：display: grid; grid-template-columns: repeat(12, 1fr); gap: 0;（12カラム）
- HEROは grid-column: 1 / -1;（全幅）を使い、内部グリッドで 1:3 を実現
- FEATURESは grid-column: 1 / -1; を使い、内部グリッドで 2:4:2 を実現
- すべてのテキストは text-align: left;（右揃え・中央揃え禁止）

【ボーダー設計】
- HEADER下部：border-bottom: 1px solid #050505;
- FEATURES各行上部：border-top: 1px solid #050505;
- CTA上下：border-top: 2px solid #DA291C; border-bottom: 2px solid #DA291C;
- FOOTER上部：border-top: 2px solid #050505;
- border-radius は完全禁止（0px）

【モーション・インタラクション】
- CTAボタン：hover時に background: transparent → #FDFDFD、color: #FDFDFD → #DA291C へ transition: 0.15s ease
- FEATURESの各行：hover時に background: #FDFDFD → rgba(218,41,28,0.04) へ transition: 0.2s ease
- ページロード：H1を transform: translateX(-20px); opacity: 0; から translateX(0); opacity: 1; へ 0.5s ease で表示（数学的な横移動）
- HEADERは scroll-behavior と連動してページ上部以外では background: rgba(253,253,253,0.95); + backdrop-filter: blur(4px); に変化

【レスポンシブ設計（必須）】
- ブレークポイント：1024px（タブレット横）/ 768px（タブレット縦）/ 480px（スマートフォン）
- 1024px以下：HEROの1:3グリッドを1:2に変更
- 768px以下：HEROの内部グリッドを解除し、縦積みに変更（縦書きラベルは非表示）
- 480px以下：FEATURESの2:4:2グリッドを1カラムに変更、右カラム（空白）を削除
- 全幅ベースグリッドはすべての幅で維持

【アクセシビリティ（必須）】
- 全インタラクティブ要素に :focus-visible スタイルを設定（outline: 2px solid #DA291C; outline-offset: 4px）
- カラーコントラスト比：#050505 on #FDFDFD はWCAG AAA基準（7:1以上）に準拠
- スチールグレー #888888 on #FDFDFD のコントラスト比は 3.7:1（AA Large基準を満たす大きなテキストのみに使用）
- HEADERは <nav> 要素を使用し、aria-label="メインナビゲーション" を付与
- CTA要素には role と aria-label を適切に設定

【完全禁止事項】
- 絵文字・FontAwesome等のアイコンフォント
- box-shadow（完全禁止、スイス・スタイルの美学に反する）
- border-radius（完全禁止）
- グラデーション全般（ベタ塗りのみ）
- 均等割りグリッドカード（必ず非対称比率で）
- 中央揃え・右揃えテキスト（左揃え厳守）
- Inter / Roboto / Arial / system-ui フォント
- インターナショナルレッドの多用（H2カラーとCTA背景のみ）
```

---

## 改善ポイント解説

| 改善項目 | 旧バージョン | 新バージョン |
|---|---|---|
| セクション定義 | なし | Header/Hero/Features/CTA/Footerを明示 |
| グリッド実装 | 「12カラムを意識」と抽象的 | `repeat(12, 1fr)` の実装コードで指定 |
| 非対称比率 | 「1:3や2:4」と例示のみ | 各セクションで具体的な比率を定義 |
| アクセシビリティ | WCAG基準への言及なし | #888888のコントラスト比の限定条件を明記 |
| スクロール挙動 | 記載なし | HEADERのblur効果をscrollと連動定義 |
| モーション | 記載なし | 横移動フェードイン + hover効果を定義 |
| レスポンシブ | 記載なし | 3段階ブレークポイントを明示 |
| 赤の使用制限 | 「H2のカラーのみ」と記載あるが曖昧 | CTAとH2のみ、多用禁止と明確化 |
