# nitech-status

名古屋工業大学（NITech）の外部公開サービスの稼働状況を監視する非公式ステータスサイトです。
[Gatus](https://github.com/TwiN/gatus) を使用しています。

学外ネットワークからアクセスできない学内限定サービスは対象外とし、外部からアクセス可能なサービスのみを監視します。

## 監視対象

nitech.ac.jp ドメイン配下で外部からアクセス可能なサービスを監視しています。
大学公式サイト・図書館・情報基盤・教育システムといった全学的なサービスを中心に、
一部の学科・団体サイトも対象に含めています。

一覧は [config/config.yaml](config/config.yaml) を参照してください（コメントアウトされている項目は現在対象外です）。
設定項目の詳細は [Gatus のドキュメント](https://github.com/TwiN/gatus#configuration) を参照してください。

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
