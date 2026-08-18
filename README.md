# nitech-status

名古屋工業大学（NITech）の外部公開サービスの稼働状況を監視する非公式ステータスサイトです。
[Gatus](https://github.com/TwiN/gatus) を使用しています。

学外ネットワークからアクセスできない学内限定サービスは対象外とし、外部からアクセス可能なサービスのみを監視します。

## 監視対象

| サービス | グループ | URL |
|---|---|---|
| 大学公式サイト | 全学 | https://www.nitech.ac.jp/ |
| 附属図書館 | 全学 | https://www.lib.nitech.ac.jp/ |
| 図書館蔵書検索（OPAC） | 全学 | https://opac.lib.nitech.ac.jp/opc/ |
| 情報基盤センター | 情報基盤 | https://www.cc.nitech.ac.jp/ |
| 権威DNSサーバー ns1 | 情報基盤 | ns1.nitech.ac.jp（DNSクエリ） |
| 権威DNSサーバー ns2 | 情報基盤 | ns2.nitech.ac.jp（DNSクエリ） |
| Moodle（オンライン教材） | 教育システム | https://cms7.ict.nitech.ac.jp/moodle40a/ |
| シラバス公開システム | 教育システム | https://syllabus.ict.nitech.ac.jp/ |
| 履修登録システム | 教育システム | https://course.web.nitech.ac.jp/ |
| コンピュータ倶楽部 NITMic | 課外活動団体 | https://nitmic.club.nitech.ac.jp/ |

対象を追加・変更する場合は [config/config.yaml](config/config.yaml) を編集してください。
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
