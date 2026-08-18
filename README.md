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
| 基礎類 | 研究・教育組織 | https://kiso.web.nitech.ac.jp/ |
| 規則・ガイドライン管理システム | 研究・教育組織 | https://kisoku.web.nitech.ac.jp/ |
| 研究シーズ集 | 研究・教育組織 | https://seeds.web.nitech.ac.jp/ |
| ソフトウェア集 | 研究・教育組織 | https://software.web.nitech.ac.jp/ |
| 産学官金連携機構 | 研究・教育組織 | https://sanren.web.nitech.ac.jp/ |
| リサーチ・アドミニストレーション（URA）室 | 研究・教育組織 | https://rao.web.nitech.ac.jp/ |
| ダイバーシティ推進センター | 研究・教育組織 | https://diversity.web.nitech.ac.jp/ |
| 新領域学術院 | 研究・教育組織 | https://nfri.web.nitech.ac.jp/ |
| 分析装置・機器紹介 | 研究・教育組織 | https://kiki.web.nitech.ac.jp/ |
| マテリアル先端リサーチインフラ事業 | 研究・教育組織 | https://nano.web.nitech.ac.jp/ |
| 若手研究イノベータ養成センター | 研究・教育組織 | http://wakate.web.nitech.ac.jp/ |
| オープンサイエンスポータル | 研究・教育組織 | https://oa.web.nitech.ac.jp/ |
| オプトバイオテクノロジー研究センター | 研究・教育組織 | http://obtrc.web.nitech.ac.jp/ |
| NITech AI研究センター | 研究・教育組織 | https://airc.web.nitech.ac.jp/ |
| 留学生センター | 研究・教育組織 | https://isc.web.nitech.ac.jp/ |
| 卒業生連携室 | 研究・教育組織 | https://alum.nitech.ac.jp/ |
| 工学教育総合センター | 研究・教育組織 | http://educenter.web.nitech.ac.jp/ |
| コンピュータ倶楽部 NITMic | 課外活動団体 | https://nitmic.club.nitech.ac.jp/ |
| プログラミング部 C0de | 課外活動団体 | https://c0de-web.club.nitech.ac.jp/ |
| アカペラサークル Grazie!! | 課外活動団体 | https://grazie.club.nitech.ac.jp/ |
| 管弦楽団 | 課外活動団体 | https://nitorchestra.club.nitech.ac.jp/ |
| S-EV（ソーラーカー部） | 課外活動団体 | https://solar-car.club.nitech.ac.jp/ |
| 水泳部 | 課外活動団体 | https://nitswimmingteam.club.nitech.ac.jp/ |
| ボート部 | 課外活動団体 | https://rowing.club.nitech.ac.jp/ |
| ワンダーフォーゲル部 | 課外活動団体 | https://nitwv.club.nitech.ac.jp/ |
| 卓球部 | 課外活動団体 | https://ttc.club.nitech.ac.jp/ |
| 吹奏楽団 | 課外活動団体 | https://nwo.club.nitech.ac.jp/ |
| アイスホッケー部 | 課外活動団体 | https://nitech-icehockey.club.nitech.ac.jp/ |

一部のクラブサイト（ボート部、ワンダーフォーゲル部、卓球部、吹奏楽団、アイスホッケー部）はTLS証明書が自己署名または期限切れのため、証明書検証をスキップして監視しています。

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
