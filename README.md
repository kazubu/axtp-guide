# AXTP Guide

ai03 Altair-X（RP2040 / QMK + VIA）に Sprintek SK8707-01 ポインティングスティックを追加した Mod（**A**ltair-**X** **T**rack**P**oint Mod）のビルドガイドと利用マニュアル。

公開先: https://kazubu.github.io/axtp-guide/

## ローカルでのプレビュー

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
mkdocs serve
```

http://127.0.0.1:8000/ で確認できます。ファイルを保存すると自動でリロードされます。

本番と同じビルドを確認する場合:

```bash
mkdocs build --strict
```

## ディレクトリ構成

```
mkdocs.yml                 サイト設定（ナビ・テーマ・多言語）
requirements.txt           ビルドに必要な Python パッケージ
.github/workflows/pages.yml  master への push で GitHub Pages へデプロイ
docs/
├── index.md               トップ（はじめに）
├── build/                 ビルドガイド
│   ├── 01-bom.md          部品リストと必要工具
│   ├── 02-pcb.md          基板の実装
│   ├── 03-trackpoint.md   SK8707-01 とマウント基板の組み込み
│   ├── 04-assembly.md     ケースの組み立て
│   └── 05-firmware.md     ファームウェアの書き込み
├── manual/                利用マニュアル
│   ├── usage.md           基本操作とレイヤー
│   ├── trackpoint.md      トラックポイントの設定
│   └── keymap.md          キーマップの変更
├── troubleshooting.md     トラブルシュート
├── faq.md                 FAQ
└── assets/
    ├── images/            画像置き場
    └── stylesheets/       追加 CSS
```

## 多言語（日本語 / 英語）

[mkdocs-static-i18n](https://github.com/ultrabug/mkdocs-static-i18n) の suffix 方式を使っています。

- 日本語（既定）: `docs/index.md`
- 英語: `docs/index.en.md`

英語版は現時点では見出しだけのスケルトンです。ページを追加するときは、まず日本語版のファイルを作り `mkdocs.yml` の `nav` に追加し、英語のタイトルを `nav_translations` に追記してください（`.en.md` は後から追加しても問題ありません）。

## 画像の追加

`docs/assets/images/` 以下にページ単位で置きます。

```
docs/assets/images/build/03-sk8707.jpg
```

Markdown からの参照（`build/` 配下のページの場合）:

```markdown
![SK8707 とマウント基板](../assets/images/build/03-sk8707.jpg){ loading=lazy }
```

画像はクリックで拡大表示されます（mkdocs-glightbox）。写真は横 1600px 程度に縮小してからコミットしてください。

## GitHub Pages の設定

初回のみ、GitHub リポジトリの **Settings > Pages > Build and deployment > Source** を **GitHub Actions** に設定してください。以降は `master` への push で自動デプロイされます。

## 執筆時のメモ

- 各ページの `TODO` と HTML コメントが未確定箇所です。実機の情報が確定したら埋めてください。
- 安全上の注意は `!!! warning` / `!!! danger`、手順の確認項目はチェックリスト（`- [ ]`）で書いています。
- キー表記は `++ctrl+c++` のように書くとキーキャップ風に表示されます（pymdownx.keys）。
