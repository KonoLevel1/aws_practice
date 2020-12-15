### 概要
* パラメーターストアから値を取得
### 前提条件
* AWSサービスに登録している
### 設定方法
* 権限問題をクリアするために、ロールを作成
1. IAMにアクセス
2. ロール
3. ロールの作成
4. Lambdaを選択
5. 次のステップ：アクセス権限
6. AWSLambdaVPCAccessExecutionRoleを検索しチェック
7. AmazonSSMReadOnlyAccessを検索しチェック
8. 次のステップ：タグ
9. 次のステップ：確認
10. ロール名と説明を設定
11. ロールの作成
* パラメーターストアに値を登録
1. System Managerにアクセス
2. パラメーターストア
3. パラメーターの作成
4. 名前と説明を設定
5. 利用枠は特にこだわりなければ標準
6. タイプとデータ型を設定
7. 値を設定
8. パラメータを作成
* Lambdaを作成
1. Lambdaにアクセス
2. 関数の作成
3. 一から作成
4. 関数名とランタイムを設定
5. デフォルトの実行ロールの変更より「既存のロールを使用する」
6. 先程作成したロールを選択
7. 関数の作成
8. コード作成
```
import json
import logging
import boto3

logger = logging.getLogger()
logger.setLevel(logging.INFO)

def lambda_handler(event, context):
    ssm = boto3.client('ssm')
    
    response = ssm.get_parameter(
        Name = 'パラメーターストアの名前',
        WithDecryption=True
        )
    # TODO implement
    text = response['Parameter']['Value']
    logger.info('INFO: {}'.format(text))
    return {
        'statusCode': 200,
        'body': json.dumps('Hello from Lambda!')
    }
```