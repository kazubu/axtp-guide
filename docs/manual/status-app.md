---
title: レイヤー状態の通知アプリ
description: QMK Keyboard Status でレイヤーをマウスポインタとタスクトレイの色に表示する
---

# レイヤー状態の通知アプリ

[QMK Keyboard Status](https://github.com/kazubu/QMK_KeyboardStatus) は、いま有効になっているレイヤーを **マウスポインタの色** と **タスクトレイアイコンの色** で知らせる Windows 用のアプリです。

Auto Mouse Layer はキー操作なしでレイヤーが切り替わるため、いまマウスレイヤーにいるのかどうかが分かりにくくなりがちです。このアプリを常駐させておくと、ポインタの色でレイヤーの状態がひと目で分かります。

## 動作環境

| 項目 | 内容 |
| --- | --- |
| OS | Windows |
| キーボード側 | `companion_hid` モジュールを含む QMK ファームウェア |

!!! success "配布ファームウェアはそのまま使えます"

    [Releases](https://github.com/kazubu/axtp-guide/releases) で配布している VIA 対応ファームウェアは、[bskaplou/qmk_modules](https://github.com/bskaplou/qmk_modules) の `companion_hid` モジュールを有効にしてビルドしています。ファームウェアを入れ直す必要はありません。

## インストール

1. [Releases](https://github.com/kazubu/QMK_KeyboardStatus/releases) から `release.zip` をダウンロードする
2. 任意のフォルダに展開する
3. 実行ファイルを起動する（タスクトレイに常駐します）

## 設定

タスクトレイアイコンの右クリックメニューから **Layer Settings...** を開くと、レイヤーごとに次の項目を設定できます（最大 16 レイヤー）。

| 項目 | 内容 |
| --- | --- |
| レイヤー名 | 一覧に表示する名前 |
| カーソル色 | そのレイヤーのときのマウスポインタの色 |
| アイコン色 | そのレイヤーのときのタスクトレイアイコンの色 |
| 色変更の有効 / 無効 | レイヤーごとに色を変えるかどうか |

レイヤー番号は [基本操作とレイヤー](usage.md) のレイヤー構成表に対応します。Auto Mouse Layer で自動的に有効になるレイヤー 5 (Mouse) にだけ目立つ色を割り当てておくと、意図せずマウスレイヤーに入ったままの状態に気づきやすくなります。

## ソースからビルドする

Visual Studio で `QMKStatus.sln` を開いてビルドします。詳細は [リポジトリ](https://github.com/kazubu/QMK_KeyboardStatus) を参照してください。

## ファームウェアを自分でビルドする場合

[ファームウェアの書き込み](../build/05-firmware.md) の手順でソースからビルドする場合は、キーマップの `keymap.json` に次の指定が含まれていることを確認してください。

```json
"modules": ["bskaplou/companion_hid"]
```

この指定がないとレイヤーの通知が送られず、アプリ側で状態を検出できません。
