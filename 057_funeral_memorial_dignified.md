# プロンプト057｜葬儀社・終活サービス

```
以下の要件に従って、ウェブページをHTML+CSS+JavaScript（単一ファイル）で作成してください。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ 葬儀社・終活サービス LP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ 目的
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

葬儀社または終活コンサルタントのLP。
「静寂・尊厳・余白」のデザインで、「不安を商売にしない誠実さ」を体現する。

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ フォント
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

- ブランド名・H1：Cinzel / weight 400 / letter-spacing 0.08em（碑文のような威厳）
- 引用・リード文：EB Garamond / Italic / size 1.1–1.2rem / line-height 1.9
- 本文：Noto Serif JP / weight 300 / size 0.85–0.9rem / line-height 2.2
- サービス番号：Cinzel / size 4rem / opacity: 0.18（装飾大型ローマ数字）

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ カラーパレット
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

--bg:    #F8F5F0  /* ウォームリネン */
--bg2:   #EDE8DF  /* ベージュ */
--dark:  #1A2340  /* ディープネイビー */
--deep:  #0E1628  /* フッター */
--ink:   #2E2E2E  /* ほぼブラック */
--mid:   #7A7268  /* ウォームグレー */
--gold:  #B8A878  /* ゴールドリーフ */

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ セクション構成 & 固有技術
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. **HERO** — 光の筋3本（呼吸アニメ）/ タイプライター見出し / 縦スクロールライン
2. **PROMISE** — 2カラム / 左ゴールドボーダー引用ブロック
3. **SERVICES** — 3×2グリッド / ローマ数字大型装飾ナンバリング / ホバー背景変化
4. **FLOW** — 縦ライン伸長（`scaleY`アニメ）/ 丸バッジ + ホバーで金色塗りつぶし
5. **STAFF** — 3カラム / grayscale→カラー ホバー
6. **VOICE** — 縦リスト / 左ゴールドボーダー / 左からスライドイン
7. **CONTACT** — ダーク背景 / 電話番号大型表示
8. **FOOTER** — 3カラム

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ アニメーション仕様（固有）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

// タイプライター見出し
const text = '最期のひとつを、
丁寧に。';
let i = 0;
function type(){
  if(i >= text.length) return;
  const ch = text[i];
  if(ch === '\n') el.appendChild(document.createElement('br'));
  else {
    const span = document.createElement('span');
    span.className = 'char';
    span.textContent = ch;
    el.appendChild(span);
  }
  i++;
  setTimeout(type, i < 9 ? 80 : 60);
}
setTimeout(type, 1600);

// 縦ライン伸長
const lineObs = new IntersectionObserver(entries=>{
  entries.forEach(e=>{ if(e.isIntersecting) e.target.classList.add('grown'); });
},{threshold:.1});

// CSS
.flow-line {
  transform-origin: top;
  transform: scaleY(0);
  transition: transform 1.5s cubic-bezier(.16,1,.3,1);
}
.flow-line.grown { transform: scaleY(1); }

━━━━━━━━━━━━━━━━━━━━━━━━━━━━
■ 禁止事項
━━━━━━━━━━━━━━━━━━━━━━━━━━━━

- 明るいポップな色（赤・黄・青の高彩度色）禁止
- アニメーション多用禁止（静けさが最優先）
- 過度な装飾・影・光エフェクト禁止
- 「今だけ」系のセールス文句 禁止
- 見出し左端などの縦線装飾（border-left）は一切使用禁止
- 絵文字・外部アイコンライブラリの使用禁止
```
