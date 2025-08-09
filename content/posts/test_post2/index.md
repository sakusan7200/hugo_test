+++
title = 'Test_post2'
date = 2025-08-09T02:52:51+09:00
draft = true
tags=["hugo", "Tailwind"]
+++

# HUGO環境構築はまったポイントスペシャル

## 環境
+ WSL上にHUGOをインストール
+ 編集はWindows側のVSCodeから
+ テーマは「TailwindCSS」を使用

## ほんへ
### バージョンの相性
```bash
sudo apt install hugo
```
では後々うまくいかなかった。
代わりに
```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.128.0/hugo_extended_0.128.0_linux-amd64.deb
sudo dpkg -i hugo_extended_0.128.0_linux-amd64.deb
```
でインストール。

### 日本語
手順は複雑だった。\
`hugo.toml`に
```
languageCode = "ja"
defaultContentLanguage = 'ja'
```
を追加(または`en`からの変更)。
`themes/tailwind/i18n/jp.toml`をコピーし`ja.toml`にする(元ファイルは消さない)。
あとは`language`とかでファイル内容検索かけて片っ端から`ja`に置換していく。

### index.mdの件と画像サイズの件