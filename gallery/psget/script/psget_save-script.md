# Save-Script

Save-Script コマンドレットでは、指定した場所に保存することによって、スクリプト ファイルを確認できます。

## 説明

Save-Script コマンドレットは指定したスクリプトを保存します。

## コマンドレット構文

```powershell
Get-Command -Name Save-Script -Module PowerShellGet -Syntax
```
## コマンドレット オンライン ヘルプ リファレンス

[Save-Script](http://go.microsoft.com/fwlink/?LinkId=619786)

## コマンド例

### 例 1: リポジトリからスクリプトを保存する
このコマンドは、最新バージョンのスクリプト Fabrikam-ClientScript を GalleryINT リポジトリからローカル フォルダー C:\ScriptSharingDemo に保存します

```powershell
Save-Script -Name Fabrikam-ClientScript -Repository GalleryINT -Path C:\ScriptSharingDemo
```

### 例 2: Find-Script コマンドレットからパイプして、スクリプトのバージョンを保存する

最初のコマンドで、リポジトリ GalleryINT からバージョン 1.5 の Fabrikam-ClientScript を検索して、フォルダー C:\ScriptSharingDemo に保存します

2 番目のコマンドで、保存したスクリプト メタデータを検証します。

```powershell
Find-Script -Name Fabrikam-ClientScript -Repository GalleryINT -RequiredVersion 1.5 | Save-Script -Path C:\\ScriptSharingDemo
Test-ScriptFileInfo C:\\ScriptSharingDemo\\Fabrikam-ClientScript.ps1

Version Name Author Description
------- ---- ------ -----------
1.5 Fabrikam-ClientScript manikb Description for the Fabrikam-ClientScript script
```


<!--HONumber=Aug16_HO3-->


