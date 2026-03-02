# プロンプト03｜70s Retro Pop

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
   - 背景色：マスタードイエロー #E1AD01
   - H1をBebas Neueで極大サイズ（clamp上限）、全幅表示
   - リード文を右下に配置（grid or absolute）
   - 外枠全体を border: 4px solid #2C2C2C; で囲む

2. FEATURES（特徴リスト）
   - 背景色：アイボリー #F4F1EA
   - 3項目を左右非対称グリッドで配置（grid-template-columns: 1fr 2fr）の繰り返し
   - 各項目の左側に大きな連番（01/02/03）をBebas Neueで表示
   - 全体を太いボーダーで囲み、各項目間にも border-bottom: 3px solid #2C2C2C;

3. CTA（フルウィズブロック）
   - 背景色：ブリックレッド #D9534F
   - テキスト・ボタンは #F4F1EA（アイボリー）
   - ボタンは border: 3px solid #F4F1EA; padding: 1rem 3rem; のアウトラインスタイル
   - hover時にボタン背景を #F4F1EA、文字色を #D9534F に反転

4. FOOTER
   - 背景色：インクブラック #2C2C2C
   - テキスト：アイボリー #F4F1EA
   - border-top: 5px solid #E1AD01;（マスタードイエローのアクセントライン）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ デザイン要件
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

【出力形式】
- 単一HTMLファイル（style・scriptタグをhead内またはbody末尾にインライン記述）
- 外部リソース：Google Fonts（Bebas Neue + Dela Gothic One + Noto Sans JP）のみ許可
- 外部CSSライブラリ・UIフレームワーク一切禁止

【世界観】
- 70年代レコードジャケット / ヴィンテージマガジン / シルクスクリーン印刷
- 「大胆な色使いとタイポグラフィで、懐かしくも力強いポップさを演出」
- キーワード：Retro Groovy / Bold Block / Print Aesthetic

【カラーパレット（HEXコードを厳守）】
- ベース：アイボリー #F4F1EA（FEATURESの背景）
- テキスト：インクブラック #2C2C2C
- ボーダー：インクブラック #2C2C2C（太め 3px〜5px）
- アクセント1（HERO背景）：マスタードイエロー #E1AD01
- アクセント2（CTA背景）：ブリックレッド #D9534F
- 使用比率ルール：イエロー:レッド = 7:3（イエローをメインとして多用、レッドはCTAのみ）
- 禁止色：#FFFFFF / #000000 / 彩度の高い原色 / グラデーション全般

【タイポグラフィ】
- H1：Bebas Neue / clamp(5rem, 12vw, 10rem) / letter-spacing: 0.03em / line-height: 0.9
- 連番ラベル（01/02/03）：Bebas Neue / clamp(5rem, 10vw, 8rem) / color: #E1AD01（アイボリー背景上）または #2C2C2C
- H2（セクション見出し）：Dela Gothic One / clamp(1.2rem, 2.5vw, 2rem) / letter-spacing: 0.05em
- 本文：Noto Sans JP / 1rem / line-height: 1.8 / font-weight: 700
- CTAボタン：Dela Gothic One / 1.1rem / letter-spacing: 0.1em

【レイアウト原則】
- FEATURESグリッド定義：grid-template-columns: 120px 1fr;（連番幅固定 + テキスト可変）
- 全セクションを太いボーダーで囲む（border: 3px solid #2C2C2C;）
- 隣接セクションのボーダーが重ならないよう margin: -1px 0; で調整
- CTA：width: 100vw; margin-left: calc(50% - 50vw); でフルウィズを実現

【ボーダー設計】
- HERO外枠：border: 4px solid #2C2C2C;
- FEATURES各項目区切り：border-bottom: 3px solid #2C2C2C;
- CTAボタン：border: 3px solid #F4F1EA;
- FOOTER上部：border-top: 5px solid #E1AD01;
- border-radius は最大 0px（角丸完全禁止）

【モーション・インタラクション】
- CTAボタン：hover時に background-color: transparent → #F4F1EA、color: #F4F1EA → #D9534F へ transition: 0.15s ease
- FEATURESの連番：hover時に transform: scale(1.05); transition: 0.2s ease
- ページロード時：H1をスタンプ押印風に演出。初期状態 opacity: 0; transform: scale(1.1); → opacity: 1; transform: scale(1); transition: 0.4s ease で収縮させる
- リード文・FEATURESは animation-delay: 0.2s 刻みでフェードイン

【レスポンシブ設計（必須）】
- ブレークポイント：768px（タブレット）/ 480px（スマートフォン）
- 768px以下：FEATURESグリッドを grid-template-columns: 80px 1fr; に変更（連番幅を縮小）
- 480px以下：FEATURESグリッドを grid-template-columns: 1fr; に変更、連番を上部に配置
- H1サイズはclampの最小値（5rem）を下限とし、それ以下には縮小しない
- 全セクションのborderはモバイルでも維持

【アクセシビリティ（必須）】
- 全インタラクティブ要素に :focus-visible スタイルを設定（outline: 3px solid #E1AD01; outline-offset: 2px）
- カラーコントラスト比：#2C2C2C on #E1AD01 はWCAG AA基準（4.5:1以上）に準拠
- CTA背景 #D9534F 上の #F4F1EA テキストはコントラスト比 4.5:1以上を確認して使用
- CTAリンクには aria-label を付与

【完全禁止事項】
- 絵文字・FontAwesome等のアイコンフォント
- box-shadow の blur半径 8px 超
- border-radius 0px 超（角丸は世界観を壊す）
- グラデーション全般
- 均等割りグリッドカード（連番+テキストの非対称構造を必ず維持）
- Inter / Roboto / Arial / system-ui フォント
- マスタードイエローとブリックレッドの同一セクション内での混在
```

---

## 改善ポイント解説

| 改善項目 | 旧バージョン | 新バージョン |
|---|---|---|
| セクション定義 | なし | Hero/Features/CTA/Footerを明示 |
| 背景色の使い分け | 「ブロックごとに切り替える」と曖昧 | セクションごとに具体的なHEXを割り当て |
| カラー使用比率 | 「2色まで使用可」のみ | イエロー7:レッド3の比率ルールを明示 |
| グリッド定義 | 「大きな番号を並べる」と抽象的 | `grid-template-columns: 120px 1fr` と具体化 |
| モーション | 記載なし | スタンプ押印アニメーション+hoverを定義 |
| レスポンシブ | 記載なし | 768px/480px ブレークポイント明示 |
| アクセシビリティ | 記載なし | WCAG AA・focus-visible を追加 |
| border-radius | 16px以下と緩い | 0px（完全禁止）に厳格化 |
