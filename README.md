# WeFeeArts — 赤魔龍の実験場 (Jekyll / GitHub Pages)

個人サイトのソース一式。GitHub Pages のユーザーサイトとして公開する想定。

- 公開URL: https://akamaryuu.github.io/
- リポジトリ名: `akamaryuu.github.io`（ユーザーサイトなのでこの名前が必須）

## 記事の書き方（運用フロー）

1. `_posts/` に `YYYY-MM-DD-slug.md` を追加する
2. 先頭に front matter を付ける:

```yaml
---
layout: post
title: "記事タイトル"
date: 2026-11-11 12:00:00 +0900
categories: [notes]   # tech=講師の現場から / guild=ギルド日誌 / notes=赤魔龍の雑記
description: "一覧に出る一文要約"
---
```

3. コミットして push すると、GitHub Pages が自動でビルドして公開する（数分）

代筆フロー: ネタを一言もらう → Muse が MD の下書きを作成 → 本人が確認 → Muse がコミット → 公開。

## 構成

- `_config.yml` — サイト設定、連載の定義、看板リンク
- `_layouts/` — default / home（記事一覧）/ post（記事）
- `_includes/` — ヘッダー・フッター（看板リンクはここ）
- `assets/css/main.css` — オリジナルテーマ（外部テーマ不使用）
- `index.md` — トップ（記事一覧）
- `series.md` — 連載一覧ページ
- `about.md` — プロフィール＋リンク集（看板のハブ）

## 看板リンクについて

- 仕事用Pagesへの導線は `_config.yml` の `links.work` にURLを入れると、
  ヘッダー・フッター・Aboutに自動で出る（空の間は非表示）。
- note / X / YouTube は設定済み。

## ローカルで確認したい場合

```bash
bundle install
bundle exec jekyll serve
# http://127.0.0.1:4000/
```

※ GitHub Pages のセーフモードで動くプラグインだけを使っているので、
ローカル環境がなくても push すれば Pages 側でビルドされる。
