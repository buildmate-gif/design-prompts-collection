# プロンプト058｜Architecture Firm Portfolio — "Forma"
## 建築設計事務所ポートフォリオサイト

---

## ✅ 差分確認（既存55本との非重複チェック）

| 項目 | 本作の選択 | 非重複の根拠 |
|---|---|---|
| **テーマ** | 建築設計事務所の作品集 + サービスサイト | 028は会社紹介のみ。設計事務所ポートフォリオは55本中ゼロ |
| **カラー** | コンクリートホワイト #F0EDE8 × グラファイト #2E2E2E × 鉄錆オレンジ #C4622D × 製図ブルー #3A5A8C | 鉄錆×製図ブルー×グラファイトの組み合わせは未使用 |
| **フォント** | Archivo Narrow × Cormorant × Noto Sans JP | Archivo Narrowは全55本未使用 |
| **目玉CSS技術①** | `grid-template-areas`による間取り図的不規則グリッド（作品集） | grid-template-areasを使ったレイアウトは55本中未使用 |
| **目玉CSS技術②** | ホバーで`translateX(-100%)→translateX(0)`の横スライドオーバーレイ | 横方向スライドのオーバーレイは55本中未使用 |
| **目玉CSS技術③** | `clip-path: polygon(0 5%, 100% 0, 100% 95%, 0 100%)` による斜め帯PHILOSOPHYセクション | 斜め帯セクションは55本中未使用 |
| **インタラクション** | header `mix-blend-mode: multiply`（背景色に馴染むナビ） | mix-blend-modeナビは55本中未使用 |
| **レイアウト** | about-img `position: sticky; top: 5rem`（スクロール追従プロフィール写真） | sticky画像 × スクロールテキストの構成は55本中未使用 |

---

## 目的

建築設計事務所のポートフォリオ兼サービスサイト。
Tadao Ando / SANAA的な「余白が語る建築の哲学」をWebで体現する。

---

## フォント

```
- H1・大見出し：Cormorant / weight 300 / Italic em{color:var(--rust)}
- ナビ・ラベル・数値：Archivo Narrow / weight 500–700 / uppercase / letter-spacing 0.2em
- 本文：Noto Sans JP / weight 300 / size 0.84–0.88rem / line-height 2.2
```

**禁止：Inter / Roboto / Syne / Bebas Neue / system-ui**

---

## カラーパレット

```css
--bg:   #F0EDE8  /* コンクリートホワイト */
--bg2:  #E6E2DC  /* ウォームグレー */
--ink:  #2E2E2E  /* グラファイト */
--mid:  #7A7268  /* コンクリート中間 */
--rust: #C4622D  /* 鉄錆オレンジ（最大8回） */
--blue: #3A5A8C  /* 製図ブルー（CTAセクション） */
--dark: #2E2E2E  /* サービスセクション背景 */
```

---

## セクション構成 & 固有技術

1. **HERO** — 2カラム / `mix-blend-mode: multiply`ヘッダー / 右カラムに実績カウンター
2. **SELECTED WORKS** — `grid-template-areas`間取り図グリッド / 横スライドオーバーレイ
3. **PHILOSOPHY** — `clip-path polygon`斜め帯 / 3枚複合画像（右下をラスト色ブロックに）
4. **SERVICES** — ダーク背景 × 4カラム / 上ボーダーホバー（透明→rust）
5. **PROCESS** — 縦リスト / 大型数値（opacity 0.18）/ hover時padding-left拡張
6. **ABOUT** — 2カラム / `position:sticky`プロフィール写真 / プロフィールグリッド
7. **CTA** — 製図ブルー背景
8. **FOOTER** — 3カラム

---

## 禁止事項

- 建設業「らしい」黄色×黒のハザードカラー禁止
- 過度なドロップシャドウ・グロー禁止
- 均等割りカードレイアウト禁止
