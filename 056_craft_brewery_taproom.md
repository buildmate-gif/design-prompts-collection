# プロンプト056｜Craft Brewery & Taproom — "Iron Kettle"
## クラフトビール醸造所・タップルーム LP

---

## ✅ 差分確認（既存55本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | クラフトビール醸造所・タップルームのブランドサイト | 飲食系は012・042のみ。醸造所のブランドストーリー系は55本中ゼロ |
| **カラー** | スモークチャコール #1A1208 × アンバー #C8860A × クリームフォーム #F0E8C8 | ダークブラウン系 + アンバーの組み合わせは全55本未使用 |
| **フォント** | Oswald × Libre Baskerville × Noto Sans JP | Oswald（コンデンスゴシック）は全55本未使用 |
| **目玉CSS技術①** | SVGキャンバスによるバブルアニメーション（`requestAnimationFrame` + 発泡感）| Canvas APIを使ったビジュアル演出は55本中未使用 |
| **目玉CSS技術②** | `scroll-snap-type: x mandatory` による横スクロールビールリスト | 横スナップスクロールのコンテンツリストは55本中未使用 |
| **目玉CSS技術③** | `clip-path: polygon()` による斜め帯区切り（PROCESSセクション） | 斜め帯セクション区切りは55本中未使用 |
| **レイアウト** | スティッキー画像 × スクロールコンテンツの左右対比（TAPROOM） | Sticky画像 + 右側スクロールコンテンツの組み合わせは未使用 |
| **インタラクション** | ビールカード傾きホバー（`rotate(-.5deg)` + `translateY`） | 傾きを伴うカードホバーは55本中未使用 |

---

## 目的

クラフトビール醸造所（兼タップルーム）のブランドサイト。
BrewDog / Mikkeller的な「反骨と誠実」の世界観。
化学添加物を使わない職人ビールの哲学と、発酵の時間の重みを伝える。

---

## フォント

```
- ブランド名・H1：Oswald / weight 700 / uppercase / letter-spacing -0.02em
- 引用・キャッチ：Libre Baskerville / Italic / weight 400
- 本文：Noto Sans JP / weight 300 / line-height 2.0
- ラベル：Oswald / weight 400 / size 0.62rem / letter-spacing 0.38em
```

**禁止：Inter / Roboto / 青・紫系フォントカラー / 丸みデザイン**

---

## カラーパレット

```css
--bg:    #1A1208  /* スモークチャコール */
--bg2:   #241A0E  /* ダークモルト */
--surf:  #2E2215  /* タンク金属 */
--ink:   #F4EDD8  /* クリームフォーム */
--mid:   #A08860  /* 麦芽色 */
--amber: #C8860A  /* アンバー：CTA・アクセント */
--foam:  #F0E8C8  /* 泡白：大見出し */
```

---

## セクション構成 & 固有技術

1. **HERO** — 2カラム / SVGバブルCanvas + 統計サイドバー
2. **PHILOSOPHY** — 2カラム / 六角形バッジ装飾 / parallax-wrap
3. **ON TAP NOW** — `scroll-snap-type: x mandatory` 横スクロール / ドラッグ対応 / 傾きカード
4. **THE CRAFT** — `clip-path polygon` 斜め帯区切り / 4ステップアイコングリッド
5. **TAPROOM** — `position: sticky` 左固定画像 × 右スクロールコンテンツ / 営業時間テーブル
6. **EVENTS** — 縦リスト + ホバーでpadding-left拡張
7. **CTA** — フルブリード画像 + アンバーオーバーレイ
8. **FOOTER** — 3カラム

---

## アニメーション仕様（固有）

```javascript
// SVGバブル（Canvasアニメーション）
function animate(){
  ctx.clearRect(0, 0, canvas.width, canvas.height);
  bubbles.forEach((b,i) => {
    ctx.beginPath();
    ctx.arc(b.x, b.y, b.r, 0, Math.PI*2);
    ctx.strokeStyle = `rgba(200,134,10,${b.opacity})`;
    ctx.lineWidth = 1;
    ctx.stroke();
    b.y -= b.speed;
    b.x += b.drift;
    if(b.y + b.r < 0) bubbles[i] = createBubble();
  });
  requestAnimationFrame(animate);
}

// ドラッグスクロール（横スクロールリスト）
el.addEventListener('mousedown', e=>{ isDown=true; startX=e.pageX-el.offsetLeft; scrollLeft=el.scrollLeft; });
el.addEventListener('mousemove', e=>{ if(!isDown)return; el.scrollLeft=scrollLeft-(e.pageX-el.offsetLeft-startX); });
```

---

## 禁止事項

- 明るい背景（白・ライトグレー）禁止
- 青・紫系カラー禁止
- 丸みのある「かわいい」デザイン要素禁止
- 均等割りカードのAIっぽいレイアウト禁止
