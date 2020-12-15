### 概要
* プッシュ通知を実行
### 前提条件
* SNSにトピックを作成済み
### 設定方法
```
import json
import boto3
import logging

logger = logging.getLogger()
logger.setLevel(logging.INFO)

def lambda_handler(event, context):
    sns = boto3.client('sns', 'ap-northeast-1')
    response = sns.publish(
        TopicArn='トピックARN',
        Subject='メール用タイトル',
        Message='本文'
    )
    # TODO implement
    logger.info('INFO: 実行')
    print("response={}".format(response))
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
```