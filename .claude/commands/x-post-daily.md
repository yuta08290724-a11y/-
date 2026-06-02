# x-post-daily — トッティーX投稿チーム起動

あなたはジェット_リモートです。今日の日付：$CURRENT_DATE

以下のフェーズを順番に実行してください。

---

## Phase 1：全自動フェーズ（確認なし・一気通貫）

### Step 1：雲雀（三層リサーチ）

三層でネタを収集してください。

**一次：Obsidian ネタ帳**
- Super Memory / identity_memory_search でキーワード「ネタ」「投稿候補」「メモ」を検索
- 今日使えそうなネタを抽出
- 検索結果が空の場合は「結果なし」と表示してスキップ

**二次：X検索（hermes 3クエリ）**
- scrape_social で以下の3クエリを実行（確認不要）
  1. 今日のトレンドワード × 食 / シェフ / 料理
  2. バズっている食系投稿のパターン
  3. 競合アカウントの最新投稿
- 旬のネタ・フック・言い回しをリストアップ
- 各クエリの検索結果が空の場合は「結果なし」と表示してスキップ

**三次：Super Memory（過去の勝ちパターン）**
- identity_memory_search で「バズ」「高エンゲージ」「勝ちパターン」を検索
- 再現できる要素を抽出
- 検索結果が空の場合は「結果なし」と表示してスキップ

---

### Step 2：ツナ（X投稿生成）

Step 1の素材をもとに **5スロット** の投稿を生成してください（確認スキップ）。

各投稿フォーマット：
```
【投稿 No.X】
本文（140字以内、絵文字あり、改行で読みやすく）
---
ハッシュタグ：#〇〇 #〇〇
フック種別：[共感 / 驚き / 学び / 笑い / 感動]
```

5本すべて異なるフックで作ること。

---

### Step 3：獄寺（品質採点）

5投稿を以下の **6軸** で採点してください（確認スキップ）。各軸 1〜10点。

| 軸 | 説明 |
|---|---|
| フック力 | 冒頭1行で止まるか |
| 共感度 | 読者が「わかる」と思うか |
| 拡散性 | RTされやすい構造か |
| ブランド一致 | トッティーらしいか |
| 行動喚起 | いいね・返信・保存を促すか |
| 独自性 | 他と被っていないか |

**合計点（MAX 60点）** と **推奨投稿順位（1位〜5位）** を表示。

---

## Phase 1 完了 → 承認待ち

以下の形式で5投稿＋スコア一覧を表示し、**「Phase 2 に進みますか？（Drive保存 / 図解生成）」** と聞いてください。

```
━━━━━━━━━━━━━━━━━━━━
📋 本日の投稿候補（$CURRENT_DATE）
━━━━━━━━━━━━━━━━━━━━

🥇 推奨1位：[タイトル or 冒頭] ／ 合計 XX点
🥈 推奨2位：[タイトル or 冒頭] ／ 合計 XX点
🥉 推奨3位：[タイトル or 冒頭] ／ 合計 XX点
4位：[タイトル or 冒頭] ／ 合計 XX点
5位：[タイトル or 冒頭] ／ 合計 XX点

━━━━━━━━━━━━━━━━━━━━
▼ 各投稿の全文・採点詳細
（ここに全文と6軸スコア表示）
━━━━━━━━━━━━━━━━━━━━

Phase 2 に進みますか？
A) Drive保存 ＋ 図解生成（両方）
B) Drive保存のみ
C) 図解生成のみ
D) 終了
```

---

## Phase 2：要承認フェーズ

ユーザーの選択に応じて実行してください。

### Step 4：Google Drive保存（A or B を選択した場合）

mcp__cd6dedb6（Google Drive）を使い、以下に保存：
- フォルダ：`X投稿／$CURRENT_DATE`
- ファイル名：`x-posts-$CURRENT_DATE.md`
- 内容：5投稿の全文＋採点結果

### Step 5：笹川（図解生成）（A or C を選択した場合）

推奨1位の投稿を **4パネル2×2カルーセル形式** で図解化してください。

#### 必須フォーマット（毎回固定）

`generate_image` を `provider: gpt-image-2 / quality: high / resolution: 2K / aspect_ratio: 1:1 / background: true` で呼び出し、以下の構成で生成すること。

> **【絶対禁止ルール】毎回必ずプロンプトに含めること**
> - 実在する企業ロゴ・ブランドロゴ 一切禁止
> - 実在する店舗看板・チェーン店名 一切禁止
> - 実在する商品パッケージ・商標 一切禁止
> - コンビニ風の架空デザイン・汎用商品パッケージのみ使用

```
Single square image divided into a 2x2 grid with thin white dividing lines.
Masculine, high-contrast, cinematic SNS infographic.
Japanese text must be pixel-perfect.

STRICT RULES — APPLY TO EVERY PANEL WITHOUT EXCEPTION:
- NO real company logos or brand marks of any kind
- NO real store signage, chain store names, or recognizable retail branding
- NO real product packaging or trademarks
- USE ONLY generic convenience-store-style fictional design
- USE ONLY generic unlabeled product packaging

PANEL 1 (top-left) — 問題提起:
[今日の投稿テーマに合わせた「読者が抱えているあるある問題」を描写]
Dark moody cinematic background with dark overlay.
Yellow highlight label at top: 問題を一言で表すキャッチコピー
Huge white bold Japanese text: 問題の核心（逆説・否定形が効果的）
Orange checkmark checklist: 読者あるある4項目
Bottom dark card with orange border: 解決の予告一行

PANEL 2 (top-right) — 解説・科学:
Clean white or very light background.
Dark navy bold title: なぜそうなるのかの理由
Flow diagram or 4-column layout with generic food/item illustrations.
Each item: [素材/行動] → 効果 → 結果
All converge → bold conclusion text
Right sidebar gray box: キーメッセージ / 赤字サブテキスト

PANEL 3 (bottom-left) — 実践リスト:
Dark green or dark themed header with white bold title.
Subtitle: 金額・手間・時間などの具体的メリット
4 white cards with colored left border:
各カード: [イラスト] 品名 / 説明テキスト / orange 価格や数値
Footer strip: 合計・時間などの数字を黄色大文字で
Bottom colored banner: 行動を促すキャッチコピー

PANEL 4 (bottom-right) — 結論・愛の鞭:
Dark cinematic photo with determined human figure, heavy dark overlay.
Top small white: トッティーの肩書き一言「厨房15年のシェフが断言する」
Center: white / yellow giant / white の3段構成で核心メッセージ
Middle semi-transparent dark card: 選択を迫る問いかけ → orange bold 決断ワード
Bottom very large bold white: 命令形・断言形の3行メッセージ
Bottom checklist: 得られる変化4項目

STYLE: Masculine. High contrast. Cinematic. Bold heavy typography.
No cute or feminine elements. Smartphone-readable.
Thin bright white 4px dividing lines between all 4 panels.
```

生成後は `task_status` でポーリングして完了を確認すること。

2. 保存先：Drive の同フォルダ内 `X投稿図解$CURRENT_DATE.png`

完了後「本日の準備完了です！」と報告。
