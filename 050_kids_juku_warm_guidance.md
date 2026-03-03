# プロンプト50｜Juku — Warm Guidance

## 既存50本との差別化チェック

| 項目 | 既存の使用状況 | 本プロンプトの選択 | 重複なし |
|------|--------------|-----------------|---------|
| **カラー** | インディゴ系は全50本で未使用。「深いインディゴ×スモーキーアンバー×ミルクホワイト」の組み合わせは完全未登場 | ディープインディゴ #2C3E6B × スモーキーアンバー #C8924A × ミルクホワイト #F8F5EF | ✅ |
| **フォント** | Marcellus（ローマン体・カーニング美しい）は全50本で未使用。Noto Sans JP との組み合わせも未登場 | Marcellus + Noto Sans JP | ✅ |
| **レイアウト** | Z字・F字・縦積み・左右交互・グリッド等多数使用済み。「横長カードが縦に積み重なるタイムライン年表型」は未使用 | 年表（タイムライン）型で子供の成長ステージを表現する縦フロー | ✅ |
| **CSS装飾** | clip-pathリビール(049)・marquee(049)使用。カーソルカスタマイズ＋ホバー時のインク染み広がりエフェクトは未使用 | before擬似要素のscale(0)→scale(1) によるインクスプレッドhover（ボタン・リンク） | ✅ |
| **世界観** | 049が「実績・知性・ドキュメント」。本作は同じ30-50代夫婦×進学塾でも「子供に寄り添う伴走型・家族の物語」で対照的な訴求 | 合格実績より「子供の成長を共に喜ぶ先生」を中心に据えた、温もりある知性派デザイン | ✅ |

---

```
以下の要件に従って、進学塾のホームページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ コンテンツ情報（必ず差し替えてください）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- 塾名：[塾の名前]
- キャッチコピー：[例：「もう一人の先生として、ともに歩む。」]
- サブコピー：[2〜3文。個別指導・伴走スタイル・保護者との連携について]
- 成長ステージ（学年・時期）4〜5段階：[ステージ1：例「小4〜小5 基礎固め期」] / [ステージ2] / ...
- 各ステージの指導内容説明：[各ステージに対応した1〜2文の説明]
- 保護者との連携施策3点：[例：月次面談] / [例：進捗レポート] / [例：保護者セミナー]
- 生徒・保護者の声（3件）：[声の内容・差出人]
- 無料相談CTAテキスト：[例：「お子さまのことを話してみませんか」]
- CTAリンク先URL：[URL または #]
- 住所・電話番号・営業時間：[任意]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ ページ構成（セクション定義）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
以下の順序でセクションを構築すること。

1. HEADER（固定・薄い）
   - 背景：ミルクホワイト #F8F5EF に border-bottom: 1px solid #D8D0C0
   - 左：塾名（Marcellus / 1.2rem / letter-spacing: 0.08em / インディゴ #2C3E6B）
   - 右：ナビリンク（Noto Sans JP / 0.82rem / #5A5248）
   - ナビリンクのhover：インクスプレッドエフェクト
     - a タグに position: relative・overflow: hidden を設定
     - ::before に background: #2C3E6B・border-radius: 50%・transform: scale(0)・opacity: 0
     - hover時に scale(3)・opacity: 0.1（transition: transform 0.4s ease, opacity 0.4s ease）
     - テキスト色は hover時 #2C3E6B に変化

2. HERO（全画面高）
   - 背景：ミルクホワイト #F8F5EF
   - レイアウト：画面を左右50%に分割
     - 左：大きなキャッチコピー（Marcellus / 3.5rem / line-height: 1.3 / #2C3E6B）
             その下にサブコピー（Noto Sans JP / 1rem / line-height: 2 / #5A5248）
             CTAボタン（インクスプレッドhover付き）
     - 右：シンプルな幾何学的SVG構成（小さな正円を不規則に配置した「星座」的なパターン）
            円サイズはランダム（4px〜16px）・インディゴ #2C3E6B・opacity: 0.12〜0.25
            JavaScriptで動的に生成（10〜15個の円を座標ランダムで配置）
   - 左右の中央境界に border-right: 1px solid #D8D0C0

3. JOURNEY（成長ステージ：年表型タイムライン）
   - セクション背景：ミルクホワイト #F8F5EF
   - セクション見出し：英語ラベル（Marcellus / 0.75rem / uppercase / letter-spacing: 0.2em / #C8924A）
                       ＋日本語見出し（Noto Sans JP / 1.8rem / font-weight: 700 / #2C3E6B）
   - 画面中央に縦軸ライン（width: 1px / background: #D8D0C0 / position: absolute）
   - 4〜5ステージを縦軸に沿って交互（左右）に配置
   - 各ステージカード：
     - background: #FFFFFF・border: 1px solid #D8D0C0・border-radius: 4px
     - padding: 2rem 2.5rem・max-width: 380px
     - 縦軸との接続：水平線（border-top: 1px solid #D8D0C0）で縦軸からカードへ繋ぐ
     - 縦軸上の接点：circle（diameter: 10px・background: #C8924A・border-radius: 50%）
     - ステージ名（Marcellus / 1rem / uppercase / letter-spacing: 0.1em / #C8924A）
     - 学年・時期（Noto Sans JP / 0.8rem / #7A6E62）
     - 説明文（Noto Sans JP / 0.93rem / line-height: 1.9 / #2C2018）
   - スクロール時に各カードが opacity 0→1 + translateX(±30px→0) でフェードイン
     （左配置のカードは左から、右配置は右から）
     IntersectionObserver（threshold: 0.25）で発火

4. PARTNERSHIP（保護者との連携）
   - セクション背景：ディープインディゴ #2C3E6B
   - 見出し形式は3と同様（英語ラベル：#C8924A / 日本語見出し：#F8F5EF）
   - 連携施策3点を横並びカードで表示（gap: 2rem・flexbox）
   - 各カード：
     - background: rgba(248,245,239,0.06)
     - border: 1px solid rgba(248,245,239,0.2)
     - border-radius: 4px・padding: 2.5rem 2rem
     - 上部に大きな数字（Marcellus / 3rem / #C8924A / opacity: 0.5）
     - 施策名（Marcellus / 1rem / uppercase / letter-spacing: 0.1em / #F8F5EF）
     - 説明（Noto Sans JP / 0.88rem / line-height: 1.9 / rgba(248,245,239,0.75)）
   - カードhover時：background: rgba(248,245,239,0.1)・transition: 0.3s

5. VOICE（保護者・生徒の声）
   - セクション背景：#EEE8DC（ウォームグレイッシュ）
   - 見出し形式は3と同様
   - 3件の声を縦積みで表示。各声のブロック：
     - 引用符「"」を Marcellus / 4rem / #C8924A / opacity: 0.3 で大きく左上に配置
     - 声テキスト（Noto Sans JP / 1rem / line-height: 2.1 / #2C2018）を大きめに
     - 差出人（Marcellus / 0.8rem / uppercase / letter-spacing: 0.1em / #7A6E62）
     - 各ブロック間に border-bottom: 1px solid #C8BAA8（最後のブロックには不要）
     - 各ブロックに max-width: 680px・margin: 0 auto

6. CTA（無料相談）
   - セクション背景：ミルクホワイト #F8F5EF
   - 中央揃えで余白たっぷり（padding: 8rem 2rem）
   - 上部に英語ラベル（Marcellus / 0.7rem / uppercase / letter-spacing: 0.25em / #C8924A）
   - 大見出し（Noto Sans JP / 2rem / font-weight: 700 / #2C3E6B / line-height: 1.7）
   - サブテキスト（Noto Sans JP / 1rem / line-height: 2 / #5A5248 / max-width: 500px / margin: 0 auto）
   - CTAボタン（インクスプレッドhover付き）：
     - background: #2C3E6B・color: #F8F5EF
     - Marcellus / 0.9rem / letter-spacing: 0.12em
     - padding: 1.2rem 4rem・border-radius: 2px
     - ::before でインクスプレッドエフェクト（background: #C8924A）

7. FOOTER
   - 背景：#1E2A3C（インディゴ最暗部）
   - 塾名（Marcellus / 1rem / letter-spacing: 0.15em / #F8F5EF）
   - 住所・電話・営業時間（Noto Sans JP / 0.8rem / rgba(248,245,239,0.45)）
   - border-top: 1px solid rgba(248,245,239,0.1)
   - コピーライト（Noto Sans JP / 0.75rem / rgba(248,245,239,0.3)）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Marcellus + Noto Sans JP）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止
- 画像ファイル一切使用禁止（すべてCSS・SVGで表現）

【世界観】
- 「子供の成長を一緒に喜ぶ」温かみある教師と保護者の関係性を視覚化する
- 受験一辺倒でなく、「人として成長させてくれる塾」という信頼と温もり
- 30-50代の保護者が「ここの先生は子供のことを本気で考えている」と感じるトーン
- キーワード：Companion / Growth Journey / Warm Intelligence / Long-term Trust

【カラーパレット（HEXコードを厳守）】
- ディープインディゴ：#2C3E6B（メインカラー：見出し・CTAボタン・暗セクション背景）
- スモーキーアンバー：#C8924A（アクセント：ラベル・装飾・タイムライン接点・引用符）
- ミルクホワイト：#F8F5EF（ベース背景・ライトテキスト）
- ウォームグレイッシュ：#EEE8DC（セカンダリ背景：VOICE）
- アンカー：#2C2018（本文テキスト）
- ミッドトーン：#5A5248（サブテキスト）
- ルール：#D8D0C0（区切り線・カードボーダー）
- フッター最暗部：#1E2A3C
- 禁止：純白 #FFFFFF・純黒 #000000・原色・蛍光色・グラデーション

【フォント設定】
- 見出し・英語ラベル・装飾テキスト：Marcellus（uppercase・letter-spacing必須）
- 本文・日本語テキスト：Noto Sans JP
- 日本語本文：font-size 0.95rem / line-height 2 / letter-spacing 0.03em
- Marcellus 使用時：letter-spacing: 0.08em 以上を必ず設定

【形状ルール】
- border-radius は最大4px（シャープ）
- pill形状（border-radius: 20px超）は禁止
- box-shadow：必要最低限（0 2px 12px rgba(44,62,107,0.08) 以下）

【アニメーション（2種のみ使用）】
1. インクスプレッドhover：ナビリンク・CTAボタンに適用。
   ::before { background: #2C3E6B（またはCTAでは#C8924A）; border-radius: 50%;
   transform: scale(0); transition: transform 0.4s ease, opacity 0.4s; }
   :hover::before { transform: scale(3); opacity: 0.12; }
2. fadeInSide：JOURNEYセクションの各ステージカードに適用。
   左配置：translateX(-30px)→0 / 右配置：translateX(30px)→0
   opacity: 0→1 / transition: 0.6s ease / IntersectionObserver発火

【JavaScript要件（最小限）】
- HEROの星座SVGをランダム座標で動的生成（10〜15個の円・位置・サイズをランダム）
- IntersectionObserver：JOURNEYセクションのfadeInSide発火

【レスポンシブ】
- ブレークポイント：768px
- HERO：768px未満でカラムを縦積みに変更（星座SVGは非表示）
- JOURNEY：768px未満でタイムラインを縦一列中央揃え（左右交互をやめる）
- PARTNERSHIP：768px未満でカードを縦積みに変更
- H1：clamp(2rem, 5vw, 3.5rem)

【禁止事項】
- 丸いアイコン・バッジ・吹き出し型UI 禁止（049と同様に子ども向けとの差別化）
- 過度なアニメーション禁止（落ち着いた信頼感を損なう）
- パステル系カラー・明るすぎる色調 禁止
- 英語のみの見出し 禁止（必ず日本語大見出しとセットで）
```

---

## 使用イメージ・ターゲット

| 項目 | 内容 |
|------|------|
| **ターゲット** | 30〜50代の夫婦（子供の成長に寄り添いたい保護者） |
| **ページ用途** | 個別指導型・少人数制進学塾のメインHP |
| **トーン** | 温もり・誠実さ・長期的な信頼関係 |
| **保護者への訴求** | 「数字より、先生と子供の関係を選ぶ」 |
| **差別化** | 049（実績・知性・ドキュメント型）との対照 |

## 049との使い分け

| | 049（Intellectual Trust） | 050（Warm Guidance） |
|---|---|---|
| **訴求軸** | 合格実績・数字・知性 | 成長の旅・伴走・温もり |
| **カラー印象** | クールなネイビー×プラチナ | 深みインディゴ×アンバー |
| **レイアウト** | 左サイドバー固定・ドキュメント型 | タイムライン年表・フロー型 |
| **フォント印象** | セリフのTenor Sans：格・静けさ | ローマンのMarcellus：品・温もり |
| **向いている塾** | 大手・実績型・データで選ばれたい塾 | 小規模・個別型・関係性で選ばれたい塾 |
