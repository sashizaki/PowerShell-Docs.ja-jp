# Find-Command

モジュール内の PowerShell コマンドを検索します。

## 説明
Find-Command コマンドレットは、コマンドレット、エイリアス、関数、ワークフローなどの PowerShell コマンドを検索します。 Find-Command は、登録されているリポジトリ内のモジュールを検索します。
このコマンドレットが検索するコマンドごとに、PSGetCommandInfo オブジェクトを返します。 PSGetCommandInfo オブジェクトを Install-Module コマンドレットに渡して、コマンドを含むモジュールをインストールできます。

- Find-Command は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、RequiredVersion、AllVersions。
  - これらのパラメーターは同時に指定できません。
  - これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。
  - RequiredVersion パラメーターが指定されていない場合、Find-Command は指定された最小バージョン以上の最新バージョンのモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。
  - RequiredVersion パラメーターが指定されている場合、Find-Command は指定したバージョンに完全に一致するバージョンのモジュールのみを返します。
- Find-Command では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます。
- Find-Command では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。
- Find-Command では、登録されているリポジトリのすべてまたは一部からモジュール上でフィルター処理できます。

## コマンドレット構文
```powershell
Get-Command -Name Find-Command -Module PowerShellGet -Syntax
```

## コマンドレット オンライン ヘルプ リファレンス

[Find-Command](http://go.microsoft.com/fwlink/?LinkId=733636)

## コマンド例
```powershell

# Find a specific command
Find-Command -Name Get-ScriptAnalyzerRule

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Get-ScriptAnalyzerRule              1.5.0      PSScriptAnalyzer                    PSGallery

# Find multiple commands
Find-Command -Name Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer

# Find all available commands from all registered repositories
Find-Command

# Find available commands from few registered repositories
Find-Command -Repository PSGallery,PrivatePSGallery

# Find all commands in a specified repository
Find-Command -Repository PSGallery

# Find a command defined in a specific module
Find-Command -Name Get-ScriptAnalyzerRule -Module PSScriptAnalyzer

# Find commands from all versions of a module
Find-Command -ModuleName PSReadline -AllVersions

# Find commands with module name and MinimumVersion.
Find-Command -ModuleName PSReadline -MinimumVersion 1.1

# Find commands with module name and exact version
Find-Command -ModuleName AzureRM -RequiredVersion 1.4.0

# Find commands defined modules with -Filter based search. -Filter searches in description and module names
Find-Command -Filter Cookbook
Find-Command -Filter RBAC

# Find all commands with tags Azure or DSC in module metadata
Find-Command -Tag Azure, DSC

```

<!--HONumber=Aug16_HO3-->


