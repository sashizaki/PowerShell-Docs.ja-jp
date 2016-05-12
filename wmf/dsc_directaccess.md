# DSC リソース メソッドへの直接アクセス


DSC リソースとそのメソッド (Get、Set、Test) に直接アクセスできるように、`Invoke-DscResource` コマンドレットが追加されました。 これは、DSC リソースを活用することを希望するサード パーティが使用できます。 通常このコマンドレットは、`refreshMode = ‘Disabled’` と組み合わせて使用されますが、どの refreshMode が設定されているかに関係なく使用できます。 次に新しいコマンドレットの使用方法の例を示します。

## ファイルが存在することを確認します

```powershell
$result = Invoke-DscResource -Name File -Method Set -Property @{
                            DestinationPath = "$env:SystemDrive\\DirectAccess.txt";
                            Contents = 'This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## ファイルが存在することをテストします

```powershell
$result = Invoke-DscResource -Name File -Method Test -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result | fl
```

## ファイルの内容を取得します

```powershell
$result = Invoke-DscResource -Name File -Method Get -Property @{
                            DestinationPath="$env:SystemDrive\\DirectAccess.txt";
                            Contents='This file is create by Invoke-DscResource'} -Verbose
$result.ItemValue | fl
```


<!--HONumber=Apr16_HO4-->


