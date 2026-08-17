---
title: キーマップの変更
description: VIA でのキーマップ変更と、ソースを編集する方法
---

# キーマップの変更

このキーボードは **VIA 対応** です。VIA を使用することで、再フラッシュせずにキーマップを変更できます。

## VIA で変更する

1. [VIA](https://usevia.app/) を開く
2. キーボードが自動認識されない場合は `Authorize device` から選択
3. キーを選んで割り当てを変更する

!!! warning "変更が保存されない場合"

    ブラウザが WebHID に対応している必要があります（Chrome / Edge を推奨）。

## マウス関連のキーコード

| 用途 | QMK キーコード |
| --- | --- |
| 左クリック | `KC_BTN1` |
| 右クリック | `KC_BTN2` |
| 中クリック | `KC_BTN3` |

## カスタムキーコード

本キーボード特有の設定等は以下のキーを使用して変更可能です。
スクロール以外、デフォルトではキーマップ内に設定していないため、必要に応じて割り当てて使用してください。

| 用途 | キーコード |
| --- | --- |
| EEPROM への設定保存 | `CUSTOM(0)` |
| EEPROM 設定初期化 | `CUSTOM(1)` |
| EEPROM 設定表示（HID CONSOLEに出力されます） | `CUSTOM(2)` |
| ポインタ速度変更（押しながら ↑/↓ を押して変更） | `CUSTOM(3)` |
| Sniper Layer のポインタ速度変更（同上） | `CUSTOM(4)` |
| スクロールバッファサイズ変更（同上） | `CUSTOM(5)` |
| 押している間 Sniper Mode へ | `CUSTOM(6)` |
| Sniper Mode への切替 | `CUSTOM(7)` |
| 押している間スクロール | `CUSTOM(8)` |
| スクロールモードへの切替 | `CUSTOM(9)` |
| スクロール方向のロック（なし / 水平 / 垂直） | `CUSTOM(10)` |
| スクロール方向の入替 | `CUSTOM(11)` |

## ソースを編集して変更する

より踏み込んだカスタマイズはキーマップのソースを編集します。

[GitHub](https://github.com/kazubu/holykeebs-qmk/tree/hk-kazubu/keyboards/ai03/altair_x)

```
keyboards/ai03/altair_x/
├── config.h          # 各種設定（感度の既定値など）
├── keyboard.json     # マトリクス・レイアウト定義
└── keymaps/
    └── via/
        └── keymap.c  # VIA 対応キーマップ
```

| 定数 | 内容 |
| --- | --- |
| `AML_THRESHOLD` | Auto Mouse Layer の感度 |
| `AML_TIMEOUT_MS` | Auto Mouse Layer の有効時間 |
| `AUTO_MOUSE_LAYER` | Auto Mouse Layer で有効になるレイヤー |
| `ALTTAB_LAYER` | このレイヤーにいる間に Tab キーを押すと Alt + Tab になるレイヤーを指定 |

編集後、[ファームウェアの書き込み](../build/05-firmware.md) の手順でビルド・書き込みします。

