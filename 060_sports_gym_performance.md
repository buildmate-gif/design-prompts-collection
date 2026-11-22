# プロンプト060｜スポーツジム・パーソナルトレーニング

```
以下の要件に従って、ウェブページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ スポーツジム・パーソナルトレーニング LP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ 目的
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

パーソナルジム・スポーツパフォーマンスジムのLP。
「データで証明する身体哲学」— 数値と実績が主役。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ フォント
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

- H1・ブランド名：Bebas Neue / clamp(5rem,10vw,12rem) / letter-spacing 0.02em
- 数値・ラベル・ナビ：Rajdhani / weight 500–700 / uppercase / letter-spacing 0.12–0.32em
- 本文：Noto Sans JP / weight 300 / size 0.80–0.85rem / line-height 1.9

**禁止：Inter / Roboto / system-ui / 細すぎるフォント**

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ カラーパレット
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

--bg:   #111111  /* ヴォルカニックブラック */
--bg2:  #1A1A1A  /* カーボンダーク */
--surf: #222222  /* パネル背景 */
--ink:  #F0F0EE  /* アイスホワイト */
--mid:  #888884  /* カーボングレー */
--red:  #D42B2B  /* シグナルレッド */
--ice:  #E8EAF0  /* ほぼ白 */

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ セクション構成 & 固有技術
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. **HERO** — フルブリードブラック / 縦ストライプ / 縦回転マーキー / 右側統計
2. **RESULTS STRIP** — 赤背景の実績数値帯（4項目）
3. **PROGRAMS** — 3×2グリッド / 上ボーダーホバー / 背景グラデーション疑似要素
4. **RESULT DATA** — 4カラム / カウントアップ数値（ease-out cubic / float対応）
5. **TRAINERS** — 3カラム / grayscale(40%)→0% ホバー / translateY(-8px)浮き上がり
6. **VOICE** — 3カラム / 左赤ボーダー
7. **PRICING** — 3カラム / 3D perspective ホバー傾き（`rotateX(4deg)`）
8. **CTA** — 赤背景 / 巨大透かし文字「APEX」（opacity 0.07）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ アニメーション仕様（固有）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

// ease-out cubic カウントアップ（float対応）
const countObs = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting && !e.target.classList.contains('counted')){
      e.target.classList.add('counted');
      const target = parseFloat(e.target.dataset.target);
      const isFloat = parseInt(e.target.dataset.float) === 1;
      let startTime = null;
      const duration = 1800;
      function step(ts){
        if(!startTime) startTime = ts;
        const p = Math.min((ts - startTime)/duration, 1);
        const eased = 1 - Math.pow(1-p, 3); // ease-out cubic
        const val = eased * target;
        e.target.textContent = isFloat ? val.toFixed(1) : Math.floor(val);
        if(p < 1) requestAnimationFrame(step);
        else e.target.textContent = isFloat ? target.toFixed(1) : target;
      }
      requestAnimationFrame(step);
    }
  });
},{threshold:.5});

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ 禁止事項
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

- ネオン蛍光系のギラギラしたジムデザイン禁止
- 「今だけ！」「◯◯%OFF！」のセール表現禁止
- ポップアップ・バナーの氾濫禁止
- 見出し左端などの縦線装飾（border-left）は一切使用禁止
- 絵文字・外部アイコンライブラリの使用禁止
```
