# systems_manager

## パラメーターストア
### AWS CLIを使った操作
* 平文で保存
```
$ aws ssm put-parameter --name 'hoge' --value 'hogehoge' --type String
```
* 平文で保存（上書き）
```
$ aws ssm put-parameter --name 'hoge' --value 'hogehogehoge' --type String --overwrite
```
* 値の参照
```
aws ssm get-parameter --output text --name 'hoge' --query Parameter.Value
```
* 暗号化した値の保存
```
$ aws ssm put-parameter --name 'encryption_hoge' --value 'hogehoge' --type SecureString
```
* 暗号化した値の参照
```
$ aws ssm get-parameter --output text --query Parameter.Value --name 'encryption_hoge' --with-decryption 
```



