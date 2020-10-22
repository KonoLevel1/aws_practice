### SNSエラー対応まとめ

* AWS側で障害が発生している可能性がある
```
software.amazon.awssdk.services.sns.model.InternalErrorException: Request could not be completed (Service: Sns, Status Code: 500, Request ID: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)
```
### エラー内容
リクエストを完了できませんでした。
### 対応
AWS側で障害が発生している可能性があるので、https://status.aws.amazon.com/ やTwitterなどで状況を確認すると良き。