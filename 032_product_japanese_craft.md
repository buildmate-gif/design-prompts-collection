# シーン7：商品 / プロダクト紹介ページ プロンプト（v4）

---

## 使い方
以下のコードブロック内のプロンプトをそのままコピーして、[　]内のプレースホルダーを差し替えてください。

---

```
以下の要件に従って、商品／プロダクト紹介ページをHTML+CSS（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━
■ コンテンツ情報（差し替えてください）
━━━━━━━━━━━━━━━━━━━━━━
- 商品名 / プロダクト名：[名前]
- キャッチコピー：[一言キャッチ]
- 商品概要：[2〜3文]
- 特徴・仕様：[特徴1：説明] / [特徴2：説明] / [特徴3：説明]
- 素材・製法（あれば）：[説明]
- 価格：[価格]
- CTA文言：[購入・問い合わせなど]
- ブランド名：[名前]

━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- HTML + CSS + JavaScript（単一ファイル）
- 外部フォント：Google Fonts（Shippori Mincho + Raleway）のみ使用

【世界観・参照スタイル】
- 京都の老舗工芸品店 / SIMPLICITY / 中川政七商店のブランドサイトを参照
- 「作り手の息づかいが聞こえる、もの静かな商品ページ」
- Wabi-sabi Craft / 手仕事の痕跡 / 余白が語る価値

【カラーパレット（厳守）】
- ベース：和紙ホワイト #F9F5EE / 薄墨 #EDE7D8
- テキスト：濃墨 #1A1510 / 中墨 #6E6258
- ボーダー：#C8B99A
- アクセント：1色のみ（錆鉄 #6E3B2A）
- 禁止：純白 #FFFFFF、純黒 #000000、原色、派手なグラデーション

【タイポグラフィ】
- 商品名（H1）：Shippori Mincho / clamp(2rem, 5vw, 4rem) / font-weight: 500 / letter-spacing: 0.12em（漢字・かな中心を想定）
- 特徴見出し（H2）：Shippori Mincho / clamp(1.2rem, 2.5vw, 1.8rem) / font-weight: 400
- 英字キャッチ：Raleway / clamp(0.8rem, 1.5vw, 1rem) / font-weight: 300 / uppercase / letter-spacing: 0.2em
- 本文：Shippori Mincho / 1rem / line-height: 2.1 / letter-spacing: 0.06em
- 価格：Raleway / clamp(1.8rem, 3vw, 2.8rem) / font-weight: 300 / letter-spacing: 0.08em
- ラベル：Raleway / uppercase / 0.65rem / letter-spacing: 0.22em

【レイアウト原則】
- 縦長・縦読みを意識したシングルカラム中心
- ヒーロー：商品名を縦書き（writing-mode: vertical-rl）で右寄せ、左側に画像プレースホルダー
- 特徴紹介：各特徴を1画面ずつ使う「ゆっくり読ませる」セクション積み
- 余白を極限まで広くとる（section padding: 最低 14rem）
- 価格と購入ボタンは最小限の要素だけ、ページ最下部にシンプルに

【ページ構成（この順番で実装）】
1. Hero：縦書き商品名 + 英字キャッチ + 画像プレースホルダー
2. Concept：商品概要を短く、行間を広く
3. Features：特徴を1項目ずつ大きな余白で縦積み
4. Material：素材・製法の説明（画像プレースホルダー + テキスト）
5. Purchase：価格 + CTAボタン + ブランド名

【装飾・インタラクション】
- ページ全体：SVG feTurbulence で極薄の和紙テクスチャ（opacity: 0.04）
- 各セクション：IntersectionObserver で opacity のみのフェードイン（translateY禁止、静かに現れる）
- 画像プレースホルダー：ホバーでわずかにscale(1.015)（transition: 1.2s ease）
- CTAボタン：ボーダーのみ、ホバーで錆鉄の背景色がゆっくり塗りつぶし（transition: 0.6s）

【完全禁止（厳守）】
- 絵文字・アイコン（FontAwesome含む）一切禁止
- box-shadow の blur 半径 8px 超
- border-radius 16px 超
- 彩度の高いグラデーション
- 均等割り3カラムカード
- Inter / Roboto / Arial / system-ui
- 紫・青のグラデーション

【レスポンシブ】
- モバイル（375px〜）/ タブレット（768px〜）/ デスクトップ（1280px〜）
- モバイルでは縦書きを横書きに切り替え（writing-mode: horizontal-tb）
- section paddingはモバイルで 6rem に縮小
```
