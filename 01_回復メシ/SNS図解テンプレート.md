# 回復メシ専用 SNS図解テンプレート
> GPT Image 2.0 図解プロンプト生成ガイド
> 毎回このテンプレートを参照して5投稿分のプロンプトを出力する

---

## 全体構成

- **形式**：2×2グリッド1枚画像 × 5投稿 = 計5枚
- **サイズ**：2160×2160px（4パネルを2×2で配置）
- **対象**：30〜40代の忙しい男性
- **世界観**：「忙しい男の回復メシ」
- **出力目標**：「これ明日やろう」と思わせる図解

---

## グリッドレイアウト

```
┌─────────────────┬─────────────────┐
│  ① 問題提起     │  ② 科学の現実   │
│  黒背景×黄文字  │  白背景×フロー図│
├─────────────────┼─────────────────┤
│  ③ 実践方法     │  ④ 結論・愛の鞭 │
│  黒背景×STEP    │  黒背景×強MSG  │
└─────────────────┴─────────────────┘
各パネル 1080×1080px → 合計 2160×2160px
```

---

## プロンプト構造（1投稿 = 1プロンプト）

```
Create a single 2160x2160px image divided into a 2x2 grid of 4 panels,
each panel 1080x1080px. Japanese SNS infographic style for busy men aged 30-40.
Theme: 「忙しい男の回復メシ」

--- PANEL TOP-LEFT: 問題提起 ---
Background: dark (#1a1a1a). Layout: top = short benefit headline (white, small).
Center-left: LARGE ultra-bold Japanese main headline in yellow (#FFD600).
Left: symptom checklist ✔ ×4 items in white. Bottom: solution preview in orange (#FF6B00).
Content:
- Top: {{短いベネフィット}}
- Headline: {{大見出し（2〜3行）}}
- Checklist: ✔ {{症状1}} / ✔ {{症状2}} / ✔ {{症状3}} / ✔ {{症状4}}
- Bottom: → {{解決策の予告}}

--- PANEL TOP-RIGHT: 科学の現実 ---
Background: white (#ffffff). Layout: top = slide title in orange.
Center: vertical arrow flow diagram with rounded rect nodes and ↓ arrows.
Right side: supplementary explanation in small dark gray.
Food node: orange border. Mechanism nodes: gray border. Result node: green border.
Content:
- Flow: {{食材（¥価格）}} ↓ {{仕組み1}} ↓ {{仕組み2}} ↓ {{最終効果}}
- Right note: {{補足解説}}

--- PANEL BOTTOM-LEFT: 実践方法 ---
Background: dark (#111111). Layout: top = yellow slide title.
Center: 3 STEP cards (yellow circle number + action + detail + price badge, dark gray bg).
Bottom bar: yellow background, black text, bold stats.
Content:
- STEP 1: {{商品名}} ¥{{価格}} → {{効果}}
- STEP 2: {{商品名}} ¥{{価格}} → {{効果}}
- STEP 3: {{商品名}} ¥{{価格}} → {{効果}}
- Bottom bar: 合計¥{{合計}} / 調理ゼロ / 最短{{N}}日で体感

--- PANEL BOTTOM-RIGHT: 結論・愛の鞭 ---
Background: black (#000000). Text centered.
Top: orange bordered tag. Center: ultra-large headline white + orange accent.
Below: body message in gray (#bbbbbb) stacked lines.
Bottom: orange CTA button, black text, rounded rect.
Content:
- Headline: {{核心メッセージ（2行）}}（orange accent on key word）
- Body: {{本質}} / {{行動}} / {{未来の姿}}
- CTA: {{行動喚起（10文字以内）}}🔥

--- GLOBAL STYLE RULES ---
- Ultra-bold Japanese Gothic font (Noto Sans JP Black or equivalent)
- High contrast, masculine, SNS-optimized for mobile
- Numbers large, prices prominent, minimal white space
- No cute elements, no minimal design, no pastel colors
- No feminine design elements
- 4px white separator lines between panels

IMPORTANT: No real brand logos, no real store signs (7-Eleven,
Lawson, FamilyMart, etc.), no real product packaging.
Use only generic convenience store-style designs and
fictional product packaging throughout.
```

---

## 毎回の出力フォーマット

```
## 🖼️ 投稿①【型名】GPT Image 2.0 プロンプト

[2160×2160px 2×2グリッド プロンプト全文]

---

## 🖼️ 投稿②【型名】GPT Image 2.0 プロンプト

[プロンプト全文]

---
（5投稿分繰り返し）
```

---

## NG一覧（毎回チェック）

- かわいい系デザイン
- ミニマルすぎるレイアウト
- 説明文だらけ（読む気が失せる）
- 女性向けカラー（ピンク・パステル）
- 抽象的・スピリチュアルな表現
- 実在ブランドロゴ・店舗看板・商品パッケージ
