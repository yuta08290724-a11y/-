# CLAUDE.md

このファイルは、このリポジトリで作業するClaude Code（claude.ai/code）へのガイダンスを提供します。

## プロジェクト概要

**Bistro Lumiere**（架空のフレンチビストロ）の静的シングルページWebサイト。日本語コンテンツで、ビルドシステムなし。HTML・CSS・JavaScriptをブラウザで直接開くだけで動作します。

## ファイル構成

- `index.html` — ページ全体のマークアップ。セクション順: `header`（ナビ・ハンバーガー・ダークモード切替）→ `#home`（ヒーロー）→ `#about` → `#menu` → `#gallery` → `#contact`（予約フォーム）→ `footer`
- `style.css` — 参照されているが未作成。スタイリングのために作成が必要。
- `script.js` — 参照されているが未作成。ダークモード・ハンバーガーメニュー・スクロールアニメーションを実装する必要あり。

## サイトの起動方法

ビルド不要。`index.html` をブラウザで直接開くか、簡易サーバーを使用:

```bash
python3 -m http.server 8080
```

## アーキテクチャと規約

**フォント:** Google Fonts — `Playfair Display`（見出し・英語表示）と `Noto Sans JP`（日本語本文）。

**スクロールアニメーション:** 要素に `fade-in` / `fade-up` クラスを付与し、`delay-100`・`delay-200`・`delay-300` で遅延を制御。JavaScriptでIntersectionObserverを使い、要素がビューポートに入ったタイミングで表示用クラス（`is-visible` 等）を付与する想定。

**ダークモード:** `#theme-toggle` ボタンで切替。`<html>` の `data-theme` 属性か `<body>` の `.dark` クラスで制御する規約を推奨。

**レイアウト:** `.container` でコンテンツ幅を制限・中央寄せ。`.grid-2` はAboutセクションとContactセクションで使われる2カラムレイアウト。

**モバイルナビ:** `.hamburger` ボタンで `.nav-list` の表示を切替。

**メニューカード:** `.menu-card` は `.menu-icon`（絵文字）・見出し・料理名・`.price`・`.menu-desc` で構成。

**ギャラリー:** `.gallery-item` は `.img-placeholder`（画像未提供）とホバー時に表示する `.gallery-overlay` キャプションで構成。
