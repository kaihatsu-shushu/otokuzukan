# お得図鑑 — 公開ファイル

このフォルダの中身を、そのまま GitHub Pages に置く。

公開先: https://kaihatsu-shushu.github.io/otokuzukan/
リポジトリ: https://github.com/kaihatsu-shushu/otokuzukan

| ファイル | 役割 | 必須か |
|---|---|---|
| `privacy.html` | プライバシーポリシー。**App Storeに提出が必要** | 必須 |
| `index.html` | 入り口のページ（アプリの紹介とポリシーへのリンク） | あった方がよい |
| `reference-prices.json` | 「めやす」の値段。アプリが**週1回まで**取りに行く | 任意（無くても動く） |

## 置いたあとにやること

1. `privacy.html` のURLを、App Store Connect の「プライバシーポリシーURL」に入れる
   → `https://kaihatsu-shushu.github.io/otokuzukan/privacy.html`
2. `reference-prices.json` のURL → **アプリ側に記入済み**（`app/web/js/main.js`）

## めやすの値段を新しくする手順（毎月）

作業用の道具は `scratchpad/stats/` にある（`xlsx.py` / `build_ref.py` / `convert.py` / `build_all.mjs`）。
詳しい取り方は vault の `Knowledge/seifu-toukei-download.md`。

1. 農水省の野菜（週次・xlsx）を落とす
2. 総務省の食品の表（月次・e-Stat）を落とす。**statInfId は毎月変わる**ので、ページから拾い直す
3. 変換して `reference-prices.json` を作り直す
4. このフォルダに置き換えて、公開先に反映する（アプリの更新も審査も要らない）

`updated` が4ヶ月より古くなると、アプリはめやすを**表示しなくなる**（古い値を出し続けないため）。
