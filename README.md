# WGCF プロファイル生成リリースなのじゃ

[![WGCF Create](https://github.com/SyameimaruKoa-company/wgcf-WireGuard/actions/workflows/blank.yml/badge.svg?event=workflow_run)](https://github.com/SyameimaruKoa-company/wgcf-WireGuard/actions/workflows/blank.yml)

このリポジトリは、GitHub Actions ワークフローによって自動生成された [wgcf](https://github.com/ViRb3/wgcf) プロファイルを生成するリポジトリじゃ。
おぬしがワークフローを実行した際に入力した端末名 (`${{ github.event.inputs.terminal_name }}`) に基づいて、以下の2種類の WireGuard プロファイルが生成され、リリースにアセットとして添付されておるのじゃ。

## ファイルリストなのじゃ

* `WARP-CloudFlare-[端末名].conf`
    *   `1.1.1.1` `1.0.0.1` `2606:4700:4700::1111` `2606:4700:4700::1001`
    * これは Cloudflare の DNS サーバー を使用する WireGuard プロファイルじゃ。
    * `wgcf generate` コマンドによって生成されたそのままのファイルなのじゃ。

* `WARP-AdGuard-[端末名].conf`
    * `94.140.14.14` `94.140.15.15` `2a10:50c0::ad1:ff` `2a10:50c0::ad2:ff`  
    * これは AdGuard の DNS サーバー を使用するように編集された WireGuard プロファイルじゃ。
    * 上記の Cloudflare DNS プロファイルを基に、DNS 設定部分のみを AdGuard のものに置換しておるのじゃ。

これらの `.conf` ファイルをダウンロードして、おぬしの WireGuard クライアントにインポートすれば使えるはずじゃ。
