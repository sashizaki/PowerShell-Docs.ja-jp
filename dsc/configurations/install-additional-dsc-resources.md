---
ms.date: 12/12/2018
keywords: dsc、powershell、resource、ギャラリーのセットアップ
title: 追加の DSC リソースをインストールする
ms.openlocfilehash: ecaf176230ccd934b57b1c27d72ff83e6ba906e9
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402909"
---
# <a name="install-additional-dsc-resources"></a>追加の DSC リソースをインストールする

PowerShell には、Desired State Configuration (DSC) のいくつかのボックスのリソースが含まれています。 **PSDesiredStateConfiguration**モジュールには、すべての PowerShell の特定インスタンスで使用可能な OOB DSC リソースが含まれます。

これは、PowerShell 4.0 およびリソースの機能の説明に含まれる OOB リソースの一覧です。

> [!NOTE]
> これは、PowerShell の各バージョンと共に OOB リソースの数が大きく、不完全なリストです。

|リソース  |説明  |
|---------|---------|
|**File**|ファイルとディレクトリの状態を制御します。 ファイルをコピー、**ソース**を**先**し、更新時に、**ソース**日付、チェックサム、およびハッシュを比較することによって変更。|
|**Archive**|アーカイブと指定した場所をアンパックします。 指定したアーカイブを検証します**チェックサム**します。|
|**Environment**|環境変数を管理します。|
|**グループ**|ローカル グループを管理し、グループ メンバーシップを制御します。|
|**Log**|メッセージを書き込みます、`Microsoft-Windows-Desired State Configuration/Analytic`イベント ログ。|
|**Package**|インストールまたはを使用してパッケージをアンインストールします**引数**、 **LogPath**、 **ReturnCode**、その他の設定。|
|**Registry**|レジストリ キーと値を管理します。|
|**Script**|デザインできる独自[取得-テスト-設定](../resources/get-test-set.md)スクリプト ブロック。|
|**Service**|Windows サービスを構成します。|
|**User** |ローカル ユーザーと属性を管理します。|
|**WindowsFeature**|役割と機能を管理します。|
|**WindowsProcess**|Windows プロセスを構成します。|

OOB のリソースでは、一般的な操作に適した開始点を許可します。 OOB のリソースは、ニーズを満たしていない場合書き込める独自[カスタム リソース](../resources/authoringResource.md)します。 問題を解決するために、カスタム リソースを記述する前に、Microsoft と PowerShell コミュニティの両方で既に作成されている DSC リソースの膨大な数を探す必要があります。

両方の DSC リソースを見つけることができます、 [PowerShell ギャラリー](https://www.powershellgallery.com/)と[GitHub](https://github.com/)します。 DSC リソースを使用して PowerShell コンソールから直接インストールすることもできます。 [PowerShellGet](/powershell/module/powershellget/)します。

## <a name="installing-powershellget"></a>PowerShellGet のインストール

既にあるかどうかを判断する**PowerShell**取得、またはのインストールに関するヘルプを取得するには、次のガイドを参照してください。[PowerShellGet のインストール](/powershell/gallery/installing-psget)

## <a name="finding-dsc-resources-using-powershellget"></a>PowerShellGet を使用して DSC リソースの検索

1 回**PowerShellGet**がインストールされている、システムの検索し、インストールでホストされる DSC リソース、 [PowerShell ギャラリー](https://www.powershellgallery.com/)します。

まず、使用して、 [Find-dscresource](/powershell/module/powershellget/find-dscresource)コマンドレット DSC リソースを検索します。 実行するときに`Find-DSCResource`最初の「NuGet プロバイダー」をインストールする次のプロンプトが表示されます。

```
PS> Find-DSCResource

NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with NuGet-based repositories. The
NuGet provider must be available in 'C:\Program Files\PackageManagement\ProviderAssemblies' or
'C:\Users\xAdministrator\AppData\Local\PackageManagement\ProviderAssemblies'. You can also install the NuGet provider
 by running 'Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to
install and import the NuGet provider now?
[Y] Yes  [N] No  [?] Help (default is "Y"):
```

キーを押して 'y' の後に"NuGet"プロバイダーがインストールされている、PowerShell ギャラリーからインストールできる DSC リソースの一覧を参照してください。

> [!NOTE]
> これが非常に大きいために、一覧は表示されません。

指定することも、 `-Name` 、ワイルドカードを使用するパラメーターまたは`-Filter`検索を絞り込むためにワイルドカードを含まないパラメーター。 この例では、ワイルドカードを使用して「タイム ゾーン」DSC リソースの検索を試みます。

> [!IMPORTANT]
> 現在のバグがある、`Find-DSCResource`両方のワイルドカードを使用できないようにするコマンドレット、`-Name`と`-Filter`パラメーター。 回避策を使用して、次の 2 つ目の例を示しています`Where-Object`します。

```
PS> Find-DSCResource -Name *Time*

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Carbon_EnvironmentVariable          2.6.0      Carbon                              PSGallery
Carbon_FirewallRule                 2.6.0      Carbon                              PSGallery
Carbon_Group                        2.6.0      Carbon                              PSGallery
Carbon_IniFile                      2.6.0      Carbon                              PSGallery
Carbon_Permission                   2.6.0      Carbon                              PSGallery
Carbon_Privilege                    2.6.0      Carbon                              PSGallery
Carbon_ScheduledTask                2.6.0      Carbon                              PSGallery
Carbon_Service                      2.6.0      Carbon                              PSGallery
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
xTimeZone                           1.8.0.0    xTimeZone                           PSGallery
xSqlServerDefaultDir                1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerMoveDatabaseFiles         1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerSQLDataRoot               1.0.0      mlSqlServerDSC                      PSGallery
xSqlServerStartupParam              1.0.0      mlSqlServerDSC                      PSGallery
```

使用することも`Where-Object`より詳細なフィルターを使用した DSC リソースを検索します。 このアプローチは、組み込みのパラメーターをフィルター処理を使用するよりも低速になります。

```
PS> Find-DSCResource | Where-Object {$_.Name -like "Time*"}

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
TimeZone                            6.0.0.0    ComputerManagementDsc               PSGallery
```

フィルターの詳細については、次を参照してください。 [Where-object](/powershell/module/microsoft.powershell.core/where-object)します。

## <a name="installing-dsc-resources-using-powershellget"></a>PowerShellGet を使用して DSC リソースをインストールします。

DSC リソースをインストールするには、使用、 [Install-module](/powershell/module/PowershellGet/Install-Module)コマンドレットは、下に表示するモジュールの名前を指定する**モジュール**検索結果内の名前。

「タイム ゾーン」リソースができるので、モジュールは次の例をインストール、"ComputerManagementDSC"モジュールに存在します。

> [!NOTE]
> PowerShell ギャラリーを信頼していない場合は、確認を求めず、以下の警告を表示し、インストールの後続のプロンプトを回避する方法を指示するようにします。

```
PS> Install-Module -Name ComputerManagementDSC

Untrusted repository
You are installing the modules from an untrusted repository. If you trust this repository, change its
InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from
'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

モジュールのインストールを続行するには、' y' キーを押します。 インストールした後を使用して、新しいリソースをインストールすることを確認できる[Get-dscresource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)します。

```
PS> Get-DSCResource -Name TimeZone -Syntax

TimeZone [String] #ResourceName
{
    IsSingleInstance = [string]{ Yes }
    TimeZone = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

指定することで、新しくインストールされたモジュールで他のリソースを表示することも、`-ModuleName`パラメーター。

```
PS> Get-DSCResource -Module ComputerManagementDSC

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      Computer                  ComputerManagementDsc          6.0.0.0    {Name, Credential, DependsOn, ...
PowerShell      OfflineDomainJoin         ComputerManagementDsc          6.0.0.0    {IsSingleInstance, RequestFile...
PowerShell      PowerPlan                 ComputerManagementDsc          6.0.0.0    {IsSingleInstance, Name, Depen...
PowerShell      PowerShellExecutionPolicy ComputerManagementDsc          6.0.0.0    {ExecutionPolicy, ExecutionPol...
PowerShell      ScheduledTask             ComputerManagementDsc          6.0.0.0    {TaskName, ActionArguments, Ac...
PowerShell      TimeZone                  ComputerManagementDsc          6.0.0.0    {IsSingleInstance, TimeZone, D...
PowerShell      VirtualMemory             ComputerManagementDsc          6.0.0.0    {Drive, Type, DependsOn, Initi...
```

## <a name="see-also"></a>関連項目

- [リソースとは](../resources/resources.md)
