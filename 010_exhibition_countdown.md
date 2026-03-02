# Scene 05 — Event & Exhibition Announcement
## 期間限定 展覧会・イベント 告知ページ

---

## 目的・コンテキスト

アートギャラリーや文化施設が開催する展覧会・イベントの告知LPを生成してください。
「期間限定」という緊張感・儚さを視覚的に表現し、
来場意欲を高める没入型のビジュアル体験を設計してください。
カウントダウン演出で「今しか見られない」感を演出します。

---

## 出力形式

- HTML + CSS + JavaScript（単一ファイル）
- Google Fonts のみ使用可
- JavaScript：カウントダウン + スクロール視差 + テキストフェイドイン

---

## 世界観・トーン

- 深夜の美術館のような静寂と興奮
- 終わりが迫る緊迫感を「引き算の演出」で表現
- キーワード：Ephemeral / Tension / Now

---

## カラーパレット

- ベース：深みのある墨 #121210 / ダークグレー #1C1B18
- テキスト：クリームホワイト #EDE8DC / フォググレー #8A8680
- アクセント（1色のみ）：くすんだバーミリオン #B84A2E（カウントダウン・CTA）
- ※ 純白 #FFFFFF・純黒 #000000・原色・派手なグラデーション 禁止

---

## タイポグラフィ

- 見出し（H1/展覧会名）：Cormorant Garamond
  - font-size: clamp(3rem, 8vw, 7rem)
  - letter-spacing: -0.03em / font-weight: 300
- 日付・会期：Cormorant Garamond / font-size: clamp(1.2rem, 2.5vw, 2rem)
- 本文（body）：DM Sans
  - font-size: 0.95rem / line-height: 1.9 / letter-spacing: 0.03em
- ラベル・カテゴリ：uppercase / font-size: 0.65rem / letter-spacing: 0.18em
- ※ Inter / Roboto / Arial / system-ui 禁止

---

## レイアウト原則

- 12カラム CSS Grid（均等割り禁止）
- アシンメトリー必須
- section padding：最低 8rem（モバイル 4rem）
- テキストと画像・背景の overlap を1箇所以上
- 細いルーラー線（1px / opacity 0.15 / ライト色）でセクション分割

---

## 構成セクション

1. **HERO（全画面）** — 展覧会名（大型セリフ体）+ 会期日程 + カウントダウンタイマー
2. **CONCEPT** — キュレーターテキスト（左: 縦書き章番号 / 右: 横書き本文）
3. **WORKS** — 出展作品紹介（非均等グリッド / モノクロプレースホルダー）
4. **VENUE & ACCESS** — 会場情報（極限まで削ぎ落とした最小限テキスト）
5. **CLOSING CTA** — チケット予約ボタン（アクセントカラー）+ カウントダウン再表示

---

## カウントダウン仕様

- 対象日時：イベント終了日（差し替え前提で架空日時を設定）
- 表示形式：DD日 HH時間 MM分 SS秒
- フォント：Cormorant Garamond / 大型 / letter-spacing: 0.1em
- 更新間隔：1秒
- 終了後テキスト：「THE EXHIBITION HAS ENDED」

---

## 装飾ルール（必須遵守）

### 使用可能

- 1px 極細ボーダー（border: 1px solid rgba(237,232,220,0.15)）
- backdrop-filter: blur(12px) / 半透明背景
- SVG feTurbulence によるノイズテクスチャ（opacity 0.04〜0.06）
- テキストアニメーション：opacity + translateY（0.7s ease、stagger）
- ホバー：下線 transform: scaleX / 文字色の subtle なシフト

### 完全禁止

- 絵文字・アイコン（FontAwesome 含む）一切禁止
- box-shadow の blur 半径 8px 超
- border-radius 16px 超
- linear-gradient / radial-gradient の彩度が高いもの
- 均等割り3カラムカード
- Inter / Roboto / Arial / system-ui
- 紫・青のグラデーション

---

## 「忘れられないディテール」（最低2つ必須実装）

- [ ] **スクロール視差**：HERO の背景要素（展覧会ビジュアル）に transform のみの parallax 演出
- [ ] **テキストマスク画像**：展覧会タイトルを作品画像でクリップするタイポグラフィ表現
- [ ] **縦書きアクセント**：CONCEPT セクションに writing-mode: vertical-rl で展覧会サブタイトルを右端配置
- [ ] **フォリオ番号**：各セクションに 01 / 02 / 03 の印刷物的ナンバリング（ライト色）

---

## 補足指示

- 展覧会名は仮称「VOID」を使用（差し替え前提）
- アーティスト名は架空の英語名・日本語名を混在させる
- 本文コピーは日本語と英語を段落単位で混在
- チケット予約ボタンは1つのみ（複数のCTA禁止）
- SNSシェア・ハッシュタグ欄は不要
