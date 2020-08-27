# cloud_watch
ログを確認するサービス

特定の条件のログを抽出するには、インサイトを利用する
* タイムスタンプ降順に20件のタイムスタンプとメッセージを表示
```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```
