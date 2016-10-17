# Set-PSRepository

Set-PSRepository は登録されたリポジトリの値を設定します。

## 説明

Set-PSRepository コマンドレットは登録されたモジュール リポジトリの値を設定します。

## コマンドレット構文

```powershell
Get-Command -Name Set-PSRepository -Module PowerShellGet -Syntax
```
## コマンドレット オンライン ヘルプ リファレンス

[Set-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517128)

## コマンド例

```powershell
PS C:\> Register-PSRepository -Name myRepository -SourceLocation "https://www.myget.org/F/powershellgetdemo/api/v2" -InstallationPolicy Trusted
PS C:\> Get-PSRepository
Name                      InstallationPolicy   SourceLocation
----                      ------------------   --------------
myRepository              Trusted              https://www.myget.org/F/powershellgetdemo/api/v2

# Set installation Policy for a repository
PS C:\> Set-PSRepository -Name myRepository -InstallationPolicy Untrusted
PS C:\> Get-PSRepository

Name                      InstallationPolicy   SourceLocation
----                      ------------------   --------------
myRepository              Untrusted            https://www.myget.org/F/powershellgetdemo/api/v2
```


### スクリプト共有がサポートされている Set-PSRepository コマンドレット

**ScriptSourceLocation** および **ScriptPublishLocation** を PSRepository に追加するには、Set-PSRepository コマンドレットを使用します。
```powershell
# Add script sharing locations to an existing PSRepository using Set-PSRepository object.
Set-PSRepository -Name MyGallery `
                 -ScriptSourceLocation https://MyGallery.com/api/v2/items/psscript/ `
                 -ScriptPublishLocation https://MyGallery.com/api/v2/package/

Get-PSRepository -Name GalleryINT | Format-List * -Force

Name : GalleryINT
SourceLocation : https://MyGallery.com/api/v2/
Trusted : True
Registered : True
InstallationPolicy : Trusted
PackageManagementProvider : NuGet
PublishLocation : https://MyGallery.com/api/v2/package/
ScriptSourceLocation : https://MyGallery.com/api/v2/items/psscript/
ScriptPublishLocation : https://MyGallery.com/api/v2/package/
ProviderOptions : {}

```


<!--HONumber=Aug16_HO3-->


