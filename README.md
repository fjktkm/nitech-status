# nitech-status

名古屋工業大学（NITech）の外部公開サービスの稼働状況を監視する非公式ステータスサイトです。
[Gatus](https://github.com/TwiN/gatus) を使用しています。

学外ネットワークからアクセスできない学内限定サービスは対象外とし、外部からアクセス可能なサービスのみを監視します。

## 監視対象

nitech.ac.jp ドメイン配下で外部からアクセス可能なサービスを、合計143件監視しています。
大学公式サイト・図書館・情報基盤・教育システムといった全学的なサービスから、
各学科の研究室、課外活動団体のサイトまで対象に含めています。

サーバーの応答自体はあるものの、内容が放棄されたプレースホルダーページ（Webサーバーの
初期状態のまま等）だったサイトは対象から除外しています。

一覧は [config/config.yaml](config/config.yaml) を参照してください。
設定項目の詳細は [Gatus のドキュメント](https://github.com/TwiN/gatus#configuration) を参照してください。

一部の研究室・団体サイトは、TLS証明書が自己署名または期限切れのままになっているため、
`client.insecure: true` で証明書検証をスキップしています。実際にリダイレクトなしで
http のみで配信されているサイトは、そのまま http で監視しています。

## ローカルでの動作確認

Docker と Docker Compose が必要です。

```sh
# フォアグラウンドで起動（http://localhost:8080 で確認）
docker compose up

# バックグラウンド起動 / 停止
docker compose up -d
docker compose down
```

Gatus の永続化データ（SQLite）は named volume（`gatus-data`）に保存されます。

## 免責事項

本サイトは、個人が運営している非公式サイトです。名古屋工業大学とは一切関係ありません。
