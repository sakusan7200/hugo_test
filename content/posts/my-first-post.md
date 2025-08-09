+++
title = 'My First Post'
date = 2025-08-08T20:18:25+09:00
draft = false
+++

# 初めに
WSL上に[HUGO](https://gohugo.io)の環境を作ってみた。

# 前提
+ Ubuntu on WSL
+ ' cd '使えるくらいのlinuxの知識
+ やる気

# 環境構築
## HUGOのインストール
```bash
wget https://github.com/gohugoio/hugo/releases/download/v0.128.0/hugo_extended_0.128.0_linux-amd64.deb
sudo dpkg -i hugo_extended_0.128.0_linux-amd64.deb
```

<details><summary>失敗例</summary>
```bash
sudo apt install hugo
```
Cpoilot君によると後の手順で使うやつとバージョンの整合が取れないらしい。
</details>

```bash
hugo version
```
ってインストールできたか確認。

## サーバー起動
テーマをダウンロードして、サーバを起動。
```bash
hugo new site quickstart
cd quickstart
git init
git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke
echo "theme = 'ananke'" >> hugo.toml
hugo server
```
そのうち
```
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
```
のように表示されるので表示されたURLをブラウザで開く。

## ページを作る
HUGOのテンプレが当たったページを作成。
適当な内容を書いて保存。
```bash
hugo new content content/posts/my-first-post.md
nano content/posts/my-first-post.md
```
さっきのURLを開いたブラウザで見たら、新しいページが増えているはずである。
![大体できスト](img1.png)

手数とｓｓｓｓｓｓｓ