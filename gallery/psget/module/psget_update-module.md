# Update-Module

指定したモジュールの最新バージョンをオンライン ギャラリーからダウンロードし、ローカル コンピューターにインストールします。

## 説明

Update-Module コマンドレットは、Install-Module を実行してオンライン ギャラリーからインストールした Windows PowerShell モジュールの最新バージョンをローカル コンピューターにインストールします。

既定では、必要なバージョンを指定しない限り、オンライン ギャラリーで入手可能な指定のモジュールの最新バージョンがインストールされます。 モジュール名を指定して、既存のインストール済みのモジュールを更新できます。更新が必要なモジュールについては、Update-Module が $env:PSModulePath を検索します。

Name パラメーターを指定せずに Update-Module を実行すると、ローカル コンピューターで更新が可能なすべてのモジュールが更新されます。

### メモ

- このコマンドレットは、Windows 7 または Windows 2008 R2 および今後のリリースの Windows での、Windows PowerShell 3.0 または今後のリリースの Windows PowerShell で機能します。
- Name パラメーターで指定したモジュールが、Install-Module によってインストールされていない場合はエラーが発生します。 Update-Module は、Install-Module を使用してオンライン ギャラリーからインストールしたモジュールについてのみ実行できます。
- Update-Module が使用中のバイナリを更新しようとすると、問題が発生したプロセスを特定し、プロセスを停止してから Update-Module を再試行するように求めるエラーが返されます。
- PowerShell 5.0 以降のバージョンでは、Update-Module がモジュールを更新するときに、モジュールの最新 (または指定した) バージョンが追加されるため、古いバージョンと新しいバージョンが同じディレクトリに並んで存在することになります。 これについては、理解しやすいようコマンドの出力例を示します。


## コマンドレット構文
```powershell
Get-Command -Name Update-Module -Module PowerShellGet -Syntax
```

## コマンドレット オンライン ヘルプ リファレンス

[Update-Module](http://go.microsoft.com/fwlink/?LinkID=398576)


## コマンド例

```powershell
PS C:\\windows\\system32> Update-Module -Name ContosoServer -RequiredVersion 1.5
PS C:\\windows\\system32> Get-Module -ListAvailable -Name ContosoServer | Format-List Name,Version,ModuleBase
Name : ContosoServer
Version : 2.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.0
Name : ContosoServer
Version : 1.5
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.5
Name : ContosoServer
Version : 1.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.0
PS C:\\windows\\system32> Get-InstalledModule
Version Name Repository Description
------- ---- ---------- -----------
1.0 ContosoServer MSPSGallery ContosoServer module
1.5 ContosoServer MSPSGallery ContosoServer module
2.0 ContosoServer MSPSGallery ContosoServer module
PS C:\\windows\\system32> Update-Module -Name ContosoServer
PS C:\\windows\\system32> Get-Module -ListAvailable -Name ContosoServer | Format-List Name,Version,ModuleBase
Name : ContosoServer
Version : 2.8.1
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.8.1
Name : ContosoServer
Version : 2.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\2.0
Name : ContosoServer
Version : 1.5
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.5
Name : ContosoServer
Version : 1.0
ModuleBase : C:\\Program Files\\WindowsPowerShell\\Modules\\ContosoServer\\1.0
PS C:\\windows\\system32> Get-InstalledModule
Version Name Repository Description
------- ---- ---------- -----------
1.0 ContosoServer MSPSGallery ContosoServer module
1.5 ContosoServer MSPSGallery ContosoServer module
2.0 ContosoServer MSPSGallery ContosoServer module
2.8.1 ContosoServer MSPSGallery ContosoServer module
```


###  依存関係を持つ TestDepWithNestedRequiredModules1 モジュールを更新します。
```powershell
Find-Module -Name TestDepWithNestedRequiredModules1 -Repository LocalRepo -AllVersions

Version    Name                                Repository  Description
-------    ----                                ----------  -----------
1.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
2.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module

Update-Module -Name TestDepWithNestedRequiredModules1 -RequiredVersion 2.0
Get-InstalledModule

Version    Name                                Repository  Description
-------    ----                                ----------  -----------
1.0        NestedRequiredModule1               LocalRepo   NestedRequiredModule1 module
2.5        NestedRequiredModule2               LocalRepo   NestedRequiredModule2 module
2.0        NestedRequiredModule3               LocalRepo   NestedRequiredModule3 module
2.5        NestedRequiredModule3               LocalRepo   NestedRequiredModule3 module
1.0        RequiredModule1                     LocalRepo   RequiredModule1 module
2.5        RequiredModule2                     LocalRepo   RequiredModule2 module
2.0        RequiredModule3                     LocalRepo   RequiredModule3 module
2.5        RequiredModule3                     LocalRepo   RequiredModule3 module
1.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
2.0        TestDepWithNestedRequiredModules1   LocalRepo   TestDepWithNestedRequiredModules1 module
```

<!--HONumber=Aug16_HO3-->


