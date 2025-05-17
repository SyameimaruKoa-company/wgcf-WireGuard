# WGCF(WARP) WireGuardプロファイル生成

※万が一僕以外が使いたい場合はフォークして使ってください。(多分それで使えるはず)

[![WGCF Create](https://github.com/SyameimaruKoa-company/wgcf-WireGuard/actions/workflows/blank.yml/badge.svg?event=workflow_run)](https://github.com/SyameimaruKoa-company/wgcf-WireGuard/actions/workflows/blank.yml)

このリポジトリは、GitHub Actions ワークフローによって自動生成された [wgcf](https://github.com/ViRb3/wgcf) プロファイルを生成するリポジトリです。
ワークフローを実行した際に入力した識別名 (`${{ github.event.inputs.terminal_name }}`) に基づいて、以下の2種類の WireGuard プロファイルが生成され、リリースにドラフトとして添付されます。

## 生成ファイルリスト

* `WARP-CloudFlare-[端末名].conf`
    *   `1.1.1.1` `1.0.0.1` `2606:4700:4700::1111` `2606:4700:4700::1001`
    * これは Cloudflare の DNS サーバー を使用する WireGuard プロファイルじゃ。
    * `wgcf generate` コマンドによって生成されたそのままのファイルです。

* `WARP-Google-[端末名].conf`
    * `8.8.8.8` `8.8.4.4` `2001:4860:4860::8888` `2001:4860:4860::8844` `2001:4860:4860::6464` `2001:4860:4860::64`  
    * これは Google の DNS サーバー を使用するように編集された WireGuard プロファイルです。
    * 使用されるかはしりませんが、DNS64も入れています。

* `WARP-AdGuard-[端末名].conf`
    * `94.140.14.14` `94.140.15.15` `2a10:50c0::ad1:ff` `2a10:50c0::ad2:ff`  
    * これは AdGuard の DNS サーバー を使用するように編集された WireGuard プロファイルです。

※ AdGuard と GoogleDNS は Cloudflare DNS プロファイルを基に、DNS 設定部分のみを置換しています。

任意の `.conf` ファイルをダウンロードして、任意の WireGuard クライアントにインポートすればWARPが使えます。
