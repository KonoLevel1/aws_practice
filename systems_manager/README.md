# systems_manager

## パラメーターストア
### AWS CLIを使った操作
* 平文で保存
```
$ aws ssm put-parameter --name 'hoge' --value 'hogehoge' --type String
```
* 値の参照
```
aws ssm get-parameter --output text --name 'hoge' --query Parameter.Value
```

