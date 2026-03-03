# プロンプト46｜Kids Juku — Adventure Map RPG

## 既存50本との差別化チェック

| 項目 | 既存の使用状況 | 本プロンプトの選択 | 重複なし |
|------|--------------|-----------------|---------|
| **カラー** | ダークネイビー背景は031で使用済み。しかし「ロールプレイングゲーム風マップ」の深緑×ブラウン×オレンジの組み合わせは未登場 | フォレストグリーン #2D6A2D × パーチメント #F2E8C8 × アドベンチャーオレンジ #E87820 | ✅ |
| **フォント** | Press Start 2P（ゲームフォント）は未使用。M PLUS Rounded 1c も未使用 | Press Start 2P + M PLUS Rounded 1c | ✅ |
| **レイアウト** | タイムライン縦ライン（028）・グリッドペーパー（033）は使用済み。「RPGマップ型進行ルート」は未使用 | 地図上の道筋を辿るステップ表示（疑似マップルート） | ✅ |
| **CSS装飾** | floating・bounce・カウントアップ・SVGラインアニメは使用済み。ピクセルチラツキ（step()関数）は未使用 | CSS animation steps() によるドット点滅 + スクロール連動ルート描画 | ✅ |
| **世界観** | レトロスペース（014）・ターミナル（033）はゲーム隣接だが全年齢向け。子ども×RPG×学習マップは完全未開拓 | 「まなびの冒険マップ」——勉強の旅を地図で表現するRPG風学習塾HP | ✅ |

---

```
以下の要件に従って、学習塾のホームページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ コンテンツ情報（必ず差し替えてください）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
- 塾名：[塾の名前]
- キャッチコピー：[メインキャッチコピー（例：「きみの冒険、ここから始まる。」）]
- サブコピー：[2〜3文。対象学年・強み・雰囲気の説明]
- 冒険の関門（特徴）3点：[関門1の名前と説明] / [関門2の名前と説明] / [関門3の名前と説明]
- 開講科目：[例：国語・算数・英語・理科・社会]
- 体験授業CTA：[ボタンテキスト（例：「冒険をはじめる（無料体験）」）]
- CTAリンク先URL：[URL または #]
- 住所・電話番号：[任意]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ ページ構成（セクション定義）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━
以下の順序でセクションを構築すること。

1. HEADER（固定ナビ）
   - 背景：パーチメント #F2E8C8（羊皮紙風）
   - 上部と下部に border: 2px solid #8B6914; （地図の縁取り風）
   - 塾名を左側に Press Start 2P / 0.9rem / #2D6A2D で表示（ゲームロゴ感）
   - 右側にナビリンク（M PLUS Rounded 1c / 0.9rem / #5C3A0A）
   - ナビリンクは hover時に背景 #2D6A2D・文字色 #F2E8C8 に変化（border-radius: 4px）

2. HERO（冒険の始まり・タイトル画面風）
   - 背景：フォレストグリーン #2D6A2D
   - 羊皮紙テクスチャ感をCSSで再現：
     background-image: repeating-linear-gradient(
       0deg, transparent, transparent 40px, rgba(139,105,20,0.06) 40px, rgba(139,105,20,0.06) 41px
     );
   - 中央に大きなタイトルボード（パーチメント #F2E8C8 背景・border: 3px solid #8B6914・border-radius: 8px・padding: 3rem 4rem）
   - ボード内：H1（Press Start 2P / 2rem / #E87820）+ 改行 + サブコピー（M PLUS Rounded 1c / 1.1rem / #5C3A0A）
   - ボード下部にCTAボタン：#E87820 背景・#F2E8C8 テキスト・border: 3px solid #8B6914・border-radius: 4px
   - ボード四隅にピクセル風の装飾（4px×4px のドット列）を::before / ::afterで描く
   - 右下に「▼ SCROLL TO START」を Press Start 2P / 0.6rem / #F2E8C8 で表示
   - 「▼」マークを steps(2) で点滅させる（CSS animation、opacity 1→0→1、1s、infinite）

3. ADVENTURE MAP（学習ルート：冒険マップ型）
   - セクション背景：パーチメント #F2E8C8
   - セクション見出し：「まなびの冒険マップ」（Press Start 2P / 1.2rem / #2D6A2D / 中央揃え）
   - 画面中央に縦方向の「道（PATH）」を表現：
     width: 8px / background: #8B6914 / position: absolute / 中央配置
   - 道の上に3〜5つの「チェックポイント」を縦に配置。交互に左右オフセット（±200px）
   - 各チェックポイント：
     - 丸いバッジ（diameter: 80px・border-radius: 50%・background: #E87820・border: 4px solid #8B6914）
     - バッジ内に番号（Press Start 2P / 1.2rem / #F2E8C8）
     - バッジ横に吹き出しボックス（background: #FFFFFF・border: 2px solid #8B6914・border-radius: 8px）
     - 吹き出し内に特徴タイトル（M PLUS Rounded 1c / 1.1rem / bold / #2D6A2D）+ 説明文
   - JavaScript（IntersectionObserver）でスクロール時に各チェックポイントを順番にフェードイン

4. SUBJECTS（科目：アイテム図鑑風）
   - セクション背景：フォレストグリーン #2D6A2D
   - セクション見出し：「かいてき どうぐ ずかん」（Press Start 2P / 1rem / #F2E8C8）
   - 科目ごとに「アイテムカード」を表示（3〜5カード/行のグリッド）
   - カード：パーチメント #F2E8C8 背景・border: 2px solid #8B6914・border-radius: 6px・padding: 1.5rem
   - カード上部：科目を連想するシンプルなSVGアイコン（鉛筆・ソロバン・英字など、30×30px）
   - カード中央：科目名（Press Start 2P / 0.75rem / #E87820）
   - カード下部：一言説明（M PLUS Rounded 1c / 0.85rem / #5C3A0A）
   - hover時：transform: translateY(-4px) + box-shadow 強調（0 8px 24px rgba(0,0,0,0.2)）

5. TESTIMONIAL / VOICE（保護者・生徒の声：ふきだし会話風）
   - セクション背景：パーチメント #F2E8C8
   - セクション見出し：「ぼうけんしゃの こえ」（Press Start 2P / 1rem / #2D6A2D / 中央揃え）
   - 3件の声を左右交互の「会話吹き出し」風で表示
   - 奇数（左）：border: 2px solid #2D6A2D・背景 #FFFFFF・左下三角
   - 偶数（右）：border: 2px solid #E87820・背景 #FFF8E8・右下三角
   - 各吹き出し下部に差出人（M PLUS Rounded 1c / 0.85rem / #8B6914）
   - 実際の声はコンテンツ情報として差し替え可能なプレースホルダー文を入れる

6. CTA（冒険への招待）
   - セクション背景：#E87820（アドベンチャーオレンジ）
   - 中央に太い border: 4px solid #8B6914 の枠（border-radius: 8px・background: #F2E8C8）
   - 枠内：大見出し（Press Start 2P / 1.2rem / #2D6A2D）+ サブテキスト（M PLUS Rounded 1c） + ボタン
   - ボタン：#2D6A2D 背景・#F2E8C8 テキスト・border: 3px solid #F2E8C8・border-radius: 4px・Press Start 2P / 0.8rem
   - 枠の四隅に剣のSVGアイコン（シンプルな十字型、#8B6914）を配置

7. FOOTER
   - 背景：#1A3D1A（ダークグリーン）
   - 塾名（Press Start 2P / 0.8rem / #F2E8C8）＋住所・電話番号（M PLUS Rounded 1c / #A8C8A8）
   - 上部に border-top: 3px solid #8B6914;

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Press Start 2P + M PLUS Rounded 1c）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止
- 画像ファイル一切使用禁止（すべてCSS・SVGで表現）

【世界観】
- レトロRPGの「冒険マップ」を学習の旅になぞらえた、ゲーム好きな子どもに刺さるデザイン
- 「勉強＝クリアすべきクエスト」という楽しいフレームで塾の魅力を伝える
- 保護者にも「楽しそう・でもちゃんとしてる」と伝わる品質感を保つ
- キーワード：Adventure / Quest / Map / Pixel Craft / Learn & Level Up

【カラーパレット（HEXコードを厳守）】
- フォレストグリーン：#2D6A2D（メインカラー：背景・ボーダー・見出し）
- パーチメント：#F2E8C8（羊皮紙ベース：背景・カード）
- アドベンチャーオレンジ：#E87820（アクセント：CTA・バッジ・見出し強調）
- マップブラウン：#8B6914（ボーダー・地図線・枠線）
- ダークブラウン：#5C3A0A（本文・サブテキスト）
- ダークグリーン：#1A3D1A（フッター背景）
- テキスト白：#F2E8C8（ダーク背景上）
- 禁止：純白 #FFFFFF（吹き出し内カードのみ可）、純黒 #000000

【フォント設定】
- ゲーム風タイトル・ナビ・ボタン：Press Start 2P（英数字・カタカナ見出しに適用）
- 本文・日本語テキスト・説明：M PLUS Rounded 1c
- 日本語本文：font-size 0.95rem / line-height 1.9 / letter-spacing 0.02em
- Press Start 2P 使用時は letter-spacing: 0.05em で可読性を確保

【形状ルール】
- ピクセルアート感を演出するため border-radius は最大8pxに抑える（CTAボタンも4〜8px）
- 丸いバッジ（チェックポイント）のみ border-radius: 50% を許容
- box-shadow：0 4px 12px rgba(0,0,0,0.15) を標準として使用

【アニメーション（2種のみ使用）】
1. blink（点滅）：▼ SCROLL テキストに適用。opacity 1→0の steps(2)、1s、infinite
2. fadeInUp：チェックポイント各項目に適用。IntersectionObserverで発火。opacity 0→1 + translateY 20px→0、0.5s ease

【JavaScript要件】
- IntersectionObserver でスクロール時にマップチェックポイントを順番にアニメーション表示
- 発火タイミング：threshold: 0.3（要素が30%見えた時点でクラス付与）
- 一度発火したら再発火しない（observer.unobserve()）

【レスポンシブ】
- ブレークポイント：768px
- モバイル時：チェックポイントの左右オフセットをなくし縦一列中央揃え
- H1は clamp(1rem, 4vw, 2rem)（Press Start 2P は英数字が大きくなりすぎるため）
- アイテムカードは2列グリッドに変更

【禁止事項】
- 絵文字（emoji）の使用禁止（SVGで代替）
- グリッチ・過度なパーティクル・発光ネオン系禁止（ネオン系は012使用済みのため）
- box-shadow blur 20px超 禁止
- 派手なグラデーション禁止（repeating-linear-gradientの縦線のみ許可）
- Press Start 2P を 1.5rem超で使用禁止（日本語の豆腐文字対策）
```

---

## 使用イメージ・ターゲット

| 項目 | 内容 |
|------|------|
| **ターゲット** | 小学生〜中学生とその保護者（特にゲーム好きな子ども） |
| **ページ用途** | 学習塾・個別指導塾のメインLP・ホームページ |
| **トーン** | ワクワク感・ゲーム的達成感・「勉強が冒険になる」 |
| **保護者へのメッセージ** | 子供が自分から「行きたい」と言う塾 |
| **差別化** | 「楽しい」だけでなく「成長の道筋が見える」安心感も同時に演出 |

## 045との使い分け

| | 045（Storybook Pop） | 046（Adventure Map RPG） |
|---|---|---|
| **対象年齢イメージ** | 幼稚園〜小学校低学年 | 小学校中・高学年〜中学生 |
| **保護者の印象** | 温かく安心できる場所 | 子どもが自分から行きたがる場所 |
| **カラー感** | 明るいパステル3色 | 渋めの自然色×アクセントオレンジ |
| **フォント感** | 丸みのある可愛らしさ | ゲーム機的レトロ感 |
