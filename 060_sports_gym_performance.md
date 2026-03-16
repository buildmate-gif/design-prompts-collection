# プロンプト060｜Sports Gym & Personal Training LP — "Apex"

## スポーツジム・パーソナルトレーニング LP

---

## ✅ 差分確認（既存55本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | スポーツジム・パーソナルトレーニング施設のLP | 全55本中スポーツ・フィットネス系はゼロ。アウトドア（045/046）は「屋外自然系」であり完全別文脈 |
| **カラー** | ヴォルカニックブラック #111111 × シグナルレッド #D42B2B × カーボングレー #4A4A4A × アイスホワイト #E8EAF0 | 赤系は031等で使用済みだが、この深いチャコール×赤×アイスホワイトの組み合わせは未使用 |
| **フォント** | Bebas Neue × Rajdhani × Noto Sans JP | Bebas Neue（ポスター的コンデンス）+ Rajdhani（スポーツ計測器的）の組み合わせは全55本未使用 |
| **レイアウト** | 右サイドの赤いストライプ装飾 + 左下コンテンツのフルブリードヒーロー | 縦ストライプ装飾は全55本未使用 |
| **アニメーション** | カウントアップ数値アニメーション（IntersectionObserver + requestAnimationFrame）| 実装の精度・float対応含む数値カウントアップは55本中未使用 |
| **データビジュアライゼーション** | 実績数値の大型表示グリッド（4カラム）| データ成果を大型グリッドで表示する構成は55本中未使用 |

---

## 目的

パーソナルジム・スポーツパフォーマンスジムのLP。
Nike Training / Whoop 的な「データで証明する身体哲学」の世界観。

「派手なネオンジム」でなく、「タイム・数値・記録への真摯な信頼」を体現する。
「3ヶ月で-12.4kg」「94%の目標達成率」など、具体的なデータが主役。

---

## フォント

```
- ブランド名・H1：Bebas Neue / size clamp(4rem, 9vw, 10rem) / letter-spacing 0.02em
  「ポスター的インパクト」で視覚的パンチを与える
- 数値・スペック・ナビ・ラベル：Rajdhani / weight 500–700
  size varies / letter-spacing 0.12–0.30em / text-transform: uppercase
- 本文（日本語）：Noto Sans JP / weight 300 / size 0.80–0.85rem / line-height 1.9
```

**禁止：Inter / Roboto / Noto Sans 通常使用 / system-ui / 細すぎるフォント**

---

## カラーパレット

```css
--bg:      #111111   /* ヴォルカニックブラック：ジムの暗がり */
--bg2:     #1A1A1A   /* カーボンダーク */
--surface: #222222   /* カード・パネル背景 */
--ink:     #F0F0EE   /* アイスホワイト：メインテキスト */
--mid:     #888884   /* カーボングレー：サブテキスト */
--red:     #D42B2B   /* シグナルレッド：CTA・アクセント */
--carbon:  #4A4A4A   /* カーボン：ボーダー・区切り */
--ice:     #E8EAF0   /* ほぼ白：大見出し */
--accent:  #FF3333   /* ビビッドレッド：ホバー・強調 */
```

---

## レイアウト

- ヘッダー：固定 / 半透明ダーク + backdrop-filter / 右端にCTAボタン
- ヒーロー：フルブリード暗背景 + 左コンテンツ + 右側統計（絶対配置）+ 右端縦ストライプ
- 実績ストリップ：赤背景 × 4項目横並び（減量・筋肉量・達成率・会員数）
- プログラム：3×2グリッド / 上ボーダーホバー（透明→赤）
- 実績データ：4カラムグリッド / 大型数値カウントアップ
- トレーナー：3カラム / 顔写真 + スペック + 資格タグ
- 料金：3カラム / 中央featured（赤ボーダー）

---

## セクション構成

1. **HERO** — 「限界を超えろ。」/ フルブリード / 統計数値サイドバー
2. **RESULTS STRIP** — 赤背景の実績数値帯（4項目）
3. **PROGRAMS** — 6プログラム（パーソナル・アスリート・ダイエット・リハビリ・シニア・オンライン）
4. **RESULT DATA** — 4カラムのカウントアップ数値グリッド
5. **TRAINERS** — 3名のトレーナー紹介 + 資格タグ
6. **MEMBER VOICE** — 3件の成果報告（-14kg / +40kg / 腰痛完全解消）
7. **PRICING** — 3プラン（Starter / Performance / Elite）
8. **CTA** — 赤背景 / 無料体験予約訴求

---

## アニメーション仕様

```javascript
// カウントアップ数値アニメーション
const countObs = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting && !e.target.classList.contains('counted')) {
      e.target.classList.add('counted');
      const target = parseFloat(e.target.dataset.target);
      const isFloat = target % 1 !== 0;
      let start = 0;
      const duration = 1800;
      const step = (timestamp) => {
        if (!start) start = timestamp;
        const progress = Math.min((timestamp - start) / duration, 1);
        const val = progress * target;
        e.target.textContent = isFloat ? val.toFixed(1) : Math.floor(val);
        if (progress < 1) requestAnimationFrame(step);
        else e.target.textContent = isFloat ? target.toFixed(1) : target;
      };
      requestAnimationFrame(step);
    }
  });
}, { threshold: 0.5 });
document.querySelectorAll('.count-up').forEach(el => countObs.observe(el));
```

---

## 禁止事項

- ネオン蛍光系のギラギラしたジムデザイン禁止
- 筋肉写真の過度なコラージュ・ごちゃごちゃしたレイアウト禁止
- ポップアップ・バナーの氾濫禁止
- 「今だけ！」「◯◯%OFF！」のセール表現禁止（データと実績が主役）
