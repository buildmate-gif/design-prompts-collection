# プロンプト059｜Medical Clinic LP — "Mori Clinic"
## クリニック・内科・生活習慣病 LP

---

## ✅ 差分確認（既存55本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | 個人クリニック・内科・生活習慣病のLP | 全55本中医療系テーマは皆無 |
| **カラー** | リネンホワイト #F5F0E8 × モスグリーン #4A6B5A × テラコッタスモーク #C47A5A | 医療×温かみコンセプトでのテラコッタ使用は新規 |
| **フォント** | Lora × Plus Jakarta Sans × Noto Sans JP | Plus Jakarta Sansは全55本未使用 |
| **目玉CSS技術①** | `rotateY(180deg)`による診療科目カード3Dフリップ（6枚） | 3Dカードフリップは55本中未使用 |
| **目玉CSS技術②** | スクロール量に応じたナビゲーションリンクのアクティブ切り替え（IntersectionObserver） | セクション連動ナビアクティブは55本中未使用 |
| **目玉CSS技術③** | ヘッダーの`scrolled`クラス切り替え（スクロール後にshadow付与） | スクロール追従ヘッダーの動的class切り替えは未使用 |
| **アニメーション** | `badgePop`（scale .8→1）+ `pulse`（dot点滅）| バッジ出現 + ドット点滅の組み合わせは55本中未使用 |
| **レイアウト** | hero-float-card の`floatCard`浮遊アニメーション | 患者数バッジの浮遊アニメは55本中未使用 |

---

## 目的

個人クリニックのLP。「AIが必ず作る青×白の典型的医療サイト」を否定する。
北欧の小さな診療所のような温もりと清潔感を両立させる。

---

## フォント

```
- クリニック名・H1：Lora / weight 400–500 / em{color:var(--moss)}
- ナビ・ラベル・ボタン：Plus Jakarta Sans / weight 500–700
- 本文：Noto Sans JP / weight 300 / line-height 2.3
```

**禁止：典型的医療青（#0077FF系）/ Roboto / Inter / 冷たい純白**

---

## カラーパレット

```css
--bg:    #F5F0E8  /* リネンホワイト */
--bg2:   #EDE8DF  /* ウォームベージュ */
--green: #EFF4EF  /* ペールグリーン */
--ink:   #2A2420  /* ウォームブラック */
--mid:   #7A7870  /* グレーブラウン */
--terra: #C47A5A  /* テラコッタスモーク：CTA */
--moss:  #4A6B5A  /* モスグリーン：信頼 */
```

---

## セクション構成 & 固有技術

1. **HEADER** — スクロール追従 + セクション連動ナビアクティブ（IntersectionObserver）
2. **HERO** — 2カラム / `badgePop`バッジアニメ + `floatCard`浮遊カード
3. **INFO STRIP** — モスグリーン横断帯 × 4項目
4. **CONCEPT** — 2カラム / 左テラコッタボーダー引用ブロック
5. **DEPT** — 3×2 フリップカード（`rotateY(180deg)` 3D flip）
6. **VISIT FLOW** — 4ステップ / hover時circle色変化 + scale(1.1)
7. **DOCTOR** — 2カラム / sticky写真 / 経歴リスト
8. **HOURS** — インタラクティブ診療時間テーブル（行ホバーハイライト）

---

## アニメーション仕様（固有）

```css
/* 3Dカードフリップ */
.flip-card { perspective: 1000px; }
.flip-inner {
  transform-style: preserve-3d;
  transition: transform .7s cubic-bezier(.16,1,.3,1);
}
.flip-card:hover .flip-inner { transform: rotateY(180deg); }
.flip-front, .flip-back { backface-visibility: hidden; }
.flip-back { transform: rotateY(180deg); }

/* スクロール連動ナビ */
const sectionObs = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      navLinks.forEach(a=>a.classList.remove('active'));
      const active = document.querySelector(`nav a[data-section="${e.target.id}"]`);
      if(active) active.classList.add('active');
    }
  });
},{threshold:.4});
```

---

## 禁止事項

- 医療系ブルー（#0000FF〜#4FC3F7系）すべて禁止
- 冷たい純白（#FFFFFF）禁止
- 「最新設備」「最高水準」等の威圧的表現禁止
