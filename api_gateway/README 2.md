# cognito
ウェブやモバイルアプリのユーザーのサインアップやサインイン、アクセスコントロールを行うサービス

# 使い道
* ユーザー認証などに利用
# メリット
* 
# 注意点
# 使い方
### **管理者ユーザーの作成**
* CLIより、管理者ユーザーを作成する

**前提条件**
* ユーザープールを作成済であること

構成
```
aws cognito-idp admin-create-user \
--profile プロファイル名 \
--user-pool-id ユーザープールID \
--username 任意の名前 \
--temporary-password パスワードポリシーに沿ったパスワード
```
例
```
aws cognito-idp admin-create-user \
--profile default \
--user-pool-id ap-northeast-1_xxxxxxxx \
--username konolevel1 \
--temporary-password 12345aB!
```

### **初期パスワードの変更**
* CLIより、初期パスワードを変更する

**前提条件**
* ユーザープールを作成済であること
* 管理者ユーザーを作成済であること

構成
```
aws cognito-idp admin-set-user-password \
  --profile default \
  --region ap-northeast-1 \
  --user-pool-id ap-northeast-1_xxxxx \
  --username konolevel1 \
  --password ポリシーに沿ったパスワード \
  --permanent
```
例
```
aws cognito-idp admin-set-user-password \
  --profile default \
  --region ap-northeast-1 \
  --user-pool-id ap-northeast-1_xxxxx \
  --username konolevel1 \
  --password 12345aB! \
  --permanent
```