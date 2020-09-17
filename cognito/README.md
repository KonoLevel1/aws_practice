# cognito
ウェブやモバイルアプリのユーザーのサインアップやサインイン、アクセスコントロールを行うサービス

# 使い道
* ログの監視
# メリット
* ログによって障害の原因調査などが行える
# 注意点
# 使い方
* Alarms
    * メトリクスをもとにアラームを発行する機能。メトリクスが特定の値を超えた場合に発動。
* Logs Insights
    * クエリ言語を使用してログデータの検索・分析ができる。
    * CloudWatch左メニュー > ログ > インサイト
    * クエリの例（ERRORを含むログを時系列降順に20件表示）
    ```
    fields @timestamp, @message
    | filter @message like "ERROR"
    | sort @timestamp desc
    | limit 20
    ```
    * クエリの例（ログレベルERRORのログを20件表示）
    ```
    fields @timestamp, @message
    | filter @message like /(?i)(error)/
    | sort @timestamp desc
    | limit 20
    ```
