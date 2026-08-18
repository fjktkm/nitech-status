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

対象を追加・変更する場合は [config/config.yaml](config/config.yaml) を編集してください。
設定項目の詳細は [Gatus のドキュメント](https://github.com/TwiN/gatus#configuration) を参照してください。

## ローカルでの動作確認

Gatus は事前ビルド済みの Docker イメージを設定ファイルで動かすだけなので、
Dev Container のようなツールチェーン分離は不要です。Docker が使える環境であれば
そのまま `docker compose` で起動できます。

```sh
# フォアグラウンドで起動（http://localhost:8080 で確認）
docker compose up

# バックグラウンド起動 / 停止
docker compose up -d
docker compose down
```

Gatus の永続化データ（SQLite）は named volume（`gatus-data`）に保存されます。
ローカルディレクトリにはバインドマウントしていないため、OneDrive 等の同期対象にはなりません。

## 免責事項

本サイトは有志が個人の立場で運営する非公式のものであり、名古屋工業大学とは一切関係がありません。本サイトは同大学による承認・後援を受けたものではなく、「名古屋工業大学」および「NITech」の名称は識別のためにのみ使用しており、同大学との提携関係を示すものではありません。
