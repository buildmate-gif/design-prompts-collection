# プロンプト49｜Juku — Intellectual Trust

## 既存50本との差別化チェック

| 項目 | 既存の使用状況 | 本プロンプトの選択 | 重複なし |
|------|--------------|-----------------|---------|
| **カラー** | ネイビー系は031(ダークネイビー #0E1C2E)のみ。しかし「くすんだ青みスレート×ウォームオイスター×プラチナアクセント」の組み合わせは未登場 | スレートネイビー #1C2B3A × オイスター #F0EDE4 × プラチナブルー #4A7A9B | ✅ |
| **フォント** | Tenor Sans は全50本で未使用。Noto Serif JP との組み合わせも未登場 | Tenor Sans + Noto Serif JP | ✅ |
| **レイアウト** | 縦タイムライン(028)・スイスグリッド(004)・マガジン(008)等あり。「左1/3固定サイドバー＋右2/3スクロールコンテンツ」の分割型は未使用 | 左サイドバー固定・右コンテンツスクロール型（ドキュメント風） | ✅ |
| **CSS装飾** | clip-pathリビールアニメは全50本で未使用 | clip-path: inset() を使ったテキスト・画像リビール（スクロール連動） | ✅ |
| **世界観** | 30-50代夫婦×進学塾は全50本で完全未開拓。「子供の将来を託せる信頼性」を知性と実績で訴える | 受験情報誌・大学パンフレット的な「知性派ドキュメント」スタイル | ✅ |

---

```
以下の要件に従って、中学受験・高校受験・大学受験対応の進学塾ホームページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ コンテンツ情報（必ず差し替えてください）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- 塾名：[塾の名前]
- キャッチコピー：[メインキャッチコピー（例：「子どもの未来を、本気で考える。」）]
- サブコピー：[2〜3文。実績・指導方針・ターゲット層の説明]
- 合格実績数値3点：[例：東大合格者数] / [例：国公立大合格率] / [例：創業年数・指導実績]
- 指導の特長3点：[特長1タイトルと説明] / [特長2タイトルと説明] / [特長3タイトルと説明]
- コース名と概要：[コース1名・対象・概要] / [コース2名・対象・概要] / [コース3名・対象・概要]
- 講師プロフィール（簡易）：[代表挨拶または講師の紹介文 2〜3文]
- 無料相談CTAテキスト：[例：「無料学習相談を予約する」]
- CTAリンク先URL：[URL または #]
- 住所・電話番号・営業時間：[任意]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ ページ構成（セクション定義）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
以下の順序でセクションを構築すること。

0. GLOBAL LAYOUT（全体構造）
   - デスクトップ（1024px以上）は左右2カラム分割レイアウトを採用する
     - 左カラム（width: 28vw・max-width: 320px）：position: sticky; top: 0; height: 100vh;
     - 左カラム内：塾名・キャッチコピー・目次ナビ・CTAボタンを縦並びで表示
     - 右カラム（flex: 1）：各セクションのコンテンツが縦に続く
   - 左カラム背景：スレートネイビー #1C2B3A
   - 右カラム背景：オイスター #F0EDE4
   - モバイル（1024px未満）は通常の縦積みレイアウトに切り替え

1. LEFT SIDEBAR（固定サイドバー）
   - 上部に塾名（Tenor Sans / 1.1rem / letter-spacing: 0.15em / uppercase / オイスター #F0EDE4）
   - その下に1px horizontal rule（border-color: rgba(240,237,228,0.2)）
   - キャッチコピー（Noto Serif JP / 0.95rem / line-height: 1.8 / オイスター #F0EDE4 / opacity: 0.85）
   - セクション目次ナビ（各セクション名・Tenor Sans / 0.75rem / letter-spacing: 0.1em）
     - 現在表示中セクションはアクティブ状態：左にプラチナブルー #4A7A9B の2px縦線＋テキスト明度アップ
     - IntersectionObserverでアクティブセクションを自動更新
   - 最下部にCTAボタン（Tenor Sans / 0.8rem / uppercase / letter-spacing: 0.1em）
     - 背景 #4A7A9B・テキスト #F0EDE4・border: 1px solid #4A7A9B・border-radius: 2px
     - hover時に背景 #F0EDE4・テキスト #1C2B3A に反転

2. HERO（右カラム最上部）
   - 背景：オイスター #F0EDE4
   - 大きな数値「実績」の視覚的見せ方：
     合格実績3点を横並びで表示。各数値に Tenor Sans / 5rem / #1C2B3A を使用
     数値の上に英語ラベル（Tenor Sans / 0.65rem / letter-spacing: 0.2em / #4A7A9B）
     数値の下に日本語説明（Noto Serif JP / 0.8rem / #7A7268）
   - 数値にスクロール発火のカウントアップアニメーションを適用
   - HEROセクション下部にサブコピー（Noto Serif JP / 1.1rem / line-height: 2 / #2A2018）
   - 右端に極細の縦ライン（border-right: 1px solid #C4B9A8）でセクション区切り感を演出

3. PHILOSOPHY（指導方針）
   - セクション見出し：英語小見出し（Tenor Sans / 0.7rem / uppercase / letter-spacing: 0.2em / #4A7A9B）
     ＋日本語大見出し（Noto Serif JP / 2rem / #1C2B3A）の2行構成
   - 指導の特長3点を縦積みで表示。各項目：
     - 左端に番号（Tenor Sans / 3rem / #4A7A9B / opacity: 0.3）
     - 番号右にタイトル（Noto Serif JP / 1.2rem / bold / #1C2B3A）＋説明文
     - 各項目の間に border-bottom: 1px solid #D4CEC4
   - 各項目を clip-path: inset(0 100% 0 0) → inset(0 0% 0 0) のリビールアニメで表示
     （IntersectionObserverで発火、transition: clip-path 0.7s cubic-bezier(0.4, 0, 0.2, 1)）

4. RESULTS（合格実績・数字で語る）
   - セクション背景：スレートネイビー #1C2B3A（右カラム内でセクション背景のみ変更）
   - セクション見出し：Tenor Sans / uppercase / letter-spacing: 0.2em / オイスター #F0EDE4
   - 合格校名リストをマーキー（横スクロール）形式で表示
     - 2行構成（上段：難関大学名 / 下段：中学・高校名）
     - 各行を逆方向にスクロール（上段：右→左 / 下段：左→右）
     - フォント：Tenor Sans / 0.85rem / letter-spacing: 0.15em / オイスター #F0EDE4
     - CSS animation: marquee 20s linear infinite（@keyframes）
     - JavaScript不要・CSSのみで実装
   - マーキー上下に border-top/bottom: 1px solid rgba(240,237,228,0.15)

5. COURSES（コース紹介）
   - セクション背景：オイスター #F0EDE4 に戻す
   - 見出しは3と同形式（英語小見出し＋日本語大見出し）
   - コース3種をカード形式で縦積み表示
   - 各カード：background: #FFFFFF・border-left: 3px solid #4A7A9B・padding: 2rem・border-radius: 2px
   - カード内：コース名（Tenor Sans / 1rem / uppercase / #1C2B3A）・対象（Noto Serif JP / 0.85rem / #4A7A9B）・概要（Noto Serif JP / 0.95rem / #2A2018）
   - カードhover時：border-left-color が #1C2B3A に変化・box-shadow: 0 4px 20px rgba(28,43,58,0.1)
   - transition: all 0.3s ease

6. TEACHER（講師・代表紹介）
   - セクション背景：#EAE6DC（オイスターより少し深め）
   - 見出しは3と同形式
   - プロフィールテキスト（Noto Serif JP / 1rem / line-height: 2.2 / #2A2018）を大きめに表示
   - テキスト左端に border-left: 2px solid #4A7A9B・padding-left: 2rem
   - 講師名（Tenor Sans / 1.4rem / letter-spacing: 0.1em / #1C2B3A）を末尾に

7. CTA（無料相談）
   - セクション背景：スレートネイビー #1C2B3A
   - 中央に大見出し（Tenor Sans / 1.8rem / uppercase / letter-spacing: 0.15em / オイスター #F0EDE4）
   - サブテキスト（Noto Serif JP / 1rem / line-height: 1.9 / オイスター #F0EDE4 / opacity: 0.8）
   - CTAボタン：
     - background: transparent・border: 1px solid #F0EDE4・color: #F0EDE4
     - Tenor Sans / 0.85rem / uppercase / letter-spacing: 0.15em
     - padding: 1.2rem 3.5rem・border-radius: 2px
     - hover時：background: #F0EDE4・color: #1C2B3A・transition: 0.3s

8. FOOTER
   - 背景：#111820（ネイビー最暗部）
   - 塾名（Tenor Sans / 0.9rem / letter-spacing: 0.2em / #F0EDE4）
   - 住所・電話番号・営業時間（Noto Serif JP / 0.8rem / rgba(240,237,228,0.5)）
   - border-top: 1px solid rgba(240,237,228,0.1)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Tenor Sans + Noto Serif JP）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止
- 画像ファイル一切使用禁止（すべてCSS・SVGで表現）

【世界観】
- 受験情報誌・大学パンフレット・高級教育機関のWebサイトを参照
- 「子供の将来を任せられる」という信頼と知性を、余白・タイポグラフィ・色調で訴える
- 保護者（30-50代夫婦）が「ここなら安心して子供を預けられる」と感じる落ち着きと格を持つ
- キーワード：Intellectual / Trustworthy / Documentary / Quiet Confidence

【カラーパレット（HEXコードを厳守）】
- スレートネイビー：#1C2B3A（メイン：サイドバー・ダークセクション背景）
- オイスター：#F0EDE4（ベース：右カラム背景・ライトテキスト）
- プラチナブルー：#4A7A9B（アクセント：強調・ライン・数値色）
- ディープオイスター：#EAE6DC（セカンダリ背景）
- アンカー：#2A2018（本文テキスト）
- ミッドトーン：#7A7268（サブテキスト・キャプション）
- ルール：#C4B9A8（区切り線）
- フッター最暗部：#111820
- 禁止：純白 #FFFFFF・純黒 #000000・原色・グラデーション（単色ベタのみ）

【フォント設定】
- 見出し・ラベル・英語テキスト：Tenor Sans（uppercase・letter-spacing必須）
- 本文・日本語テキスト・説明：Noto Serif JP
- 日本語本文：font-size 0.95rem / line-height 2 / letter-spacing 0.04em
- Tenor Sans 使用時：letter-spacing: 0.12em 以上を必ず設定

【形状ルール】
- border-radius は最大4px（直角に近いシャープな形状で知性を演出）
- pill形状（border-radius: 50px等）は一切禁止
- box-shadow：0 4px 20px rgba(28,43,58,0.08) を上限として使用

【アニメーション（2種のみ使用）】
1. clip-pathリビール：PHILOSOPHYセクションの各項目。
   clip-path: inset(0 100% 0 0) → inset(0 0% 0 0)
   transition: clip-path 0.8s cubic-bezier(0.4, 0, 0.2, 1)
   IntersectionObserver（threshold: 0.2）で発火。stagger: nth-child × 0.15s delay
2. CSSマーキー：RESULTSセクションの合格校横スクロール。
   @keyframes marquee { from { transform: translateX(0) } to { transform: translateX(-50%) } }
   CSSのみ・JavaScriptなし

【JavaScript要件（最小限）】
- IntersectionObserver①：左サイドバーのアクティブナビ自動更新
- IntersectionObserver②：PHILOSOPHYセクションのclip-pathリビール発火
- カウントアップ：HEROの数値にスクロール発火（requestAnimationFrameで実装）

【レスポンシブ】
- ブレークポイント：1024px
- 1024px以上：左サイドバー固定 + 右コンテンツの2カラムレイアウト
- 1024px未満：サイドバーを非表示→ページ上部にコンパクトなヘッダー（スレートネイビー背景）に切り替え
- モバイルH1：clamp(1.6rem, 5vw, 2.2rem)

【禁止事項】
- 丸みのある装飾・バブル・balloon型UI 禁止（子ども向けデザインとの明確な差別化）
- アイコン・イラスト・SVG装飾 禁止（テキストと線のみで構成）
- 色の急激な変化・グラデーション 禁止（セクション内の背景は単色のみ）
- カラフルな複数色使い 禁止（3色パレット厳守）
```

---

## 使用イメージ・ターゲット

| 項目 | 内容 |
|------|------|
| **ターゲット** | 30〜50代の夫婦（教育熱心な保護者） |
| **ページ用途** | 中学・高校・大学受験対応の進学塾メインHP |
| **トーン** | 信頼・知性・実績・静かな自信 |
| **保護者への訴求** | 「数字と実績で語る、本物の進学塾」 |
| **差別化** | 感情訴求でなく、知性と実績で選ばれる塾 |
