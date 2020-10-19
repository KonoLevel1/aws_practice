# simple_notification_service
アプリケーションからのリアルタイムの通知メッセージを複数の通信チャネル経由でサブスクライバーに簡単にプッシュできる。
* サブスクライバーとは？
    * メール等で定期的な案内の送信を承諾しているユーザーのこと。
## 覚えておくべき用語
* Amazon Resource Name (ARN)
    * AWSにおけるリソースID
    * ARNを利用して、配信先の呼び出しを実施する。
* End Point
    * 配信対象端末を識別するためのデータ。
* Topic
    * 配信対象をグループ化し、一斉に通知を配信する機能。
* SubScription
    * 作成したトピックと配信対象のエンドポイントを紐付けるデータ。
* Publish
    * 通知を配信すること。
## 基本機能の一部の実行方法
### トピックの作成
トピックは、メッセージの送信先システムを定義する通信チャネルの論理的なグループ。<br>
AmazonSNSにメッセージを送信すると、トピックで定義されているチャネルに配信される。
## SNSを使用したリポジトリ
* [Grails_AWS_SNS](https://github.com/KonoLevel1/Grails_AWS_SNS)
* [Grails_AWS_SNS2](https://github.com/KonoLevel1/Grails_AWS_SNS2)
* [Grails_AWS_SNS3](https://github.com/KonoLevel1/Grails_AWS_SNS3)
* [Grails_AWS_SNS4](https://github.com/KonoLevel1/Grails_AWS_SNS4)