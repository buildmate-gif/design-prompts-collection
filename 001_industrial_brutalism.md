# プロンプト01｜Industrial Brutalism

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

1. HERO（全画面高）
   - H1を極大サイズで左寄せ配置
   - 右側または下部にリード文を配置
   - セクション全体を太いボーダーで囲む

2. FEATURES（特徴リスト）
   - 3項目を左右非対称グリッドで配置（例：幅比 2:1:1）
   - 各項目に連番（01 / 02 / 03）をBebas Neue風の大きな数字で表示
   - 各項目をボーダーで区切る

3. CTA（フルウィズブロック）
   - 画面端から端まで広がるベタ塗りブロック
   - 背景色：インダストリアルイエロー #FFD700
   - ボタンは存在せず、ブロック全体をクリッカブルにする（cursor: pointer）
   - テキストはアスファルトブラック #1C1C1C

4. FOOTER
   - 最小限の情報のみ（コピーライト等）
   - 上部に太いボーダーライン

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Syne + Noto Sans JP）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止

【世界観】
- 建築図面 / ブルータリズム / インダストリアルデザイン
- 「装飾を削ぎ落とし、機能と構造をむき出しにする無骨な美しさ」
- キーワード：Raw Material / Structural / Anti-Design

【カラーパレット（HEXコードを厳守）】
- ページ背景：セメントグレー #E0E0E0
- 要素背景（ダーク）：アスファルトブラック #1C1C1C
- テキスト（通常）：#1C1C1C
- テキスト（ダーク背景上）：#E0E0E0
- ボーダー：#1C1C1C（線幅 2px〜4px）
- アクセント：インダストリアルイエロー #FFD700
- 禁止色：#FFFFFF / #000000 / 彩度の高い原色 / グラデーション全般

【タイポグラフィ】
- H1：Syne / clamp(3rem, 8vw, 7rem) / font-weight: 800 / letter-spacing: -0.05em / text-transform: uppercase
- H2（セクション見出し）：Syne / clamp(1.5rem, 3vw, 2.5rem) / font-weight: 700 / text-transform: uppercase
- 連番ラベル：Syne / clamp(4rem, 10vw, 8rem) / font-weight: 800 / color: #E0E0E0（ダーク背景上）または #1C1C1C
- 本文：Noto Sans JP / 1rem / line-height: 1.6 / font-weight: 500
- フッター：Noto Sans JP / 0.8rem / letter-spacing: 0.1em

【レイアウト原則】
- CSS Grid または Flexbox を使用すること
- グリッド定義例（FEATURES）：grid-template-columns: 2fr 1fr 1fr;
- 要素間の余白は 2rem / 4rem / 8rem の倍数系列のみ使用
- 左右非対称（アシンメトリー）配置を必ず1箇所以上使うこと
- CTAセクションは width: 100vw; margin-left: calc(50% - 50vw); でフルウィズを実現

【ボーダー設計】
- セクション区切り：border-top: 3px solid #1C1C1C;
- カード・ブロック枠：border: 2px solid #1C1C1C;
- 強調枠（HEROなど）：border: 4px solid #1C1C1C;
- border-radius は最大 4px まで。それ以上禁止

【モーション・インタラクション】
- CSSのみで実装（JavaScriptアニメーション禁止）
- CTAブロック：hover時に background-color を #FFD700 → #1C1C1C、color を #1C1C1C → #FFD700 へ transition: 0.2s ease
- FEATURESカード：hover時に transform: translateY(-4px); transition: 0.15s ease
- ページロード時のフェードイン：@keyframes fadeInUp を使い、セクションごとにanimation-delayで0.1s刻みのズレを付ける

【レスポンシブ設計（必須）】
- ブレークポイント：768px（タブレット）/ 480px（スマートフォン）
- 768px以下：FEATURESのgridをgrid-template-columns: 1fr 1fr; に変更
- 480px以下：全セクションをgrid-template-columns: 1fr; に変更、H1はclampの最小値を優先
- フルウィズCTAはすべての幅で端から端まで伸びること

【アクセシビリティ（必須）】
- 全インタラクティブ要素に :focus-visible スタイルを設定（outline: 3px solid #FFD700;）
- カラーコントラスト比：テキストと背景のコントラストをWCAG AA基準（4.5:1以上）に準拠
- CTAブロックには role="link" と tabindex="0" を付与
- 画像を使用する場合は必ず alt 属性を記述

【完全禁止事項】
- 絵文字・FontAwesome等のアイコンフォント
- box-shadow の blur半径 8px 超
- border-radius 4px 超
- グラデーション全般
- 均等割りグリッドカード（必ず非対称に）
- Inter / Roboto / Arial / system-ui フォント
- インラインstyle属性の多用（styleタグ内にCSSをまとめること）
- !important の使用
```

---

## 改善ポイント解説

| 改善項目 | 旧バージョン | 新バージョン |
|---|---|---|
| セクション定義 | なし | Hero/Features/CTA/Footerを明示 |
| グリッド比率 | 「非対称」と抽象的 | `2fr 1fr 1fr` と具体的に指定 |
| モーション | 記載なし | hover・フェードインをCSSで定義 |
| レスポンシブ | 記載なし | 768px/480px ブレークポイント明示 |
| アクセシビリティ | 記載なし | WCAG AA・focus-visible を追加 |
| border-radius | 16px以下と緩い | 4px以下に厳格化 |
| CTA実装方法 | 概念のみ | 100vw フルウィズの実装コード指示 |
