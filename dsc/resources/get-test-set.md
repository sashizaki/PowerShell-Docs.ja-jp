---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 取得-テスト-設定
ms.openlocfilehash: e46710954679bf20f4536c6efbcbd4dafd9e629e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402574"
---
# <a name="get-test-set"></a>取得-テスト-設定

>適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

![取得、テスト、および設定](/media/get-test-set.png)

PowerShell Desired State Configuration は構築、**取得**、**テスト**、および**設定**プロセス。 DSC[リソース](resources.md)それぞれにこれらの各操作を完了する方法が含まれています。 [構成](../configurations/configurations.md)、リソースのためのパラメーターになるキーを入力するリソースのブロックを定義する**取得**、**テスト**、および**設定**メソッド。

構文は、**サービス**リソース ブロック。 **サービス**リソースは、Windows サービスを構成します。

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

**取得**、**テスト**、および**設定**のメソッド、**サービス**リソースでこれらの値をそのまま使用するパラメーターのブロックが必要があります。

```powershell
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [System.String]
        $Name,

        [System.String]
        [ValidateSet("Automatic", "Manual", "Disabled")]
        $StartupType,

        [System.String]
        [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
        $BuiltInAccount,

        [System.Management.Automation.PSCredential]
        [ValidateNotNull()]
        $Credential,

        [System.String]
        [ValidateSet("Running", "Stopped")]
        $State="Running",

        [System.String]
        [ValidateNotNullOrEmpty()]
        $DisplayName,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Description,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Path,

        [System.String[]]
        [ValidateNotNullOrEmpty()]
        $Dependencies,

        [System.String]
        [ValidateSet("Present", "Absent")]
        $Ensure="Present"
    )
```

> [!NOTE]
> 言語とリソースを定義するために使用する方法を決定する方法、**取得**、**テスト**、および**設定**メソッドが定義されます。

**サービス**リソースの 1 つの必須キーのみが (`Name`)、**サービス**ブロックのリソースのように単純な可能性があります。

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

上記の構成をコンパイルするときに、キーの指定した値が生成される".mof"ファイルに格納されます。 詳細については、次を参照してください。 [MOF](/windows/desktop/wmisdk/managed-object-format--mof-)します。

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

適用すると、[ローカル構成マネージャー](../managing-nodes/metaConfig.md)に渡すし、値"Spooler"、".mof"ファイルから読み取るは、`-Name`のパラメーター、**取得**、**テスト**、**設定**の"MyService"のインスタンスのメソッド、**サービス**リソース。

## <a name="get"></a>取得

**取得**リソースのメソッドは、ターゲット ノードで構成されているように、リソースの状態を取得します。 この状態として返されます、 [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables)します。 キー、 **hashtable**リソースは、構成可能な値、またはパラメーターになります。

**取得**メソッドは、マップに直接、 [Get-dscconfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration)コマンドレット。 呼び出すと`Get-DSCConfiguration`、LCM の実行、**取得**現在適用されている構成内の各リソースのメソッド。 LCM は、対応する各リソース インスタンスにパラメーターとして".mof"ファイルに格納されているキーの値を使用します。

これはサンプルの出力から、**サービス**"Spooler"サービスを構成するリソース。

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won’t be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

現在の値のプロパティを表示で構成可能な出力、**サービス**リソース。

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a>Server1

**テスト**リソースのメソッドは、ターゲット ノードが現在に準拠して、リソースのかどうかを判断*目的の状態を*します。 **テスト**メソッドを返します。`$True`または`$False`ノードが準拠しているかどうかを示すためにのみです。
呼び出すと[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)、LCM の呼び出し、**テスト**現在適用されている構成内の各リソースのメソッド。 LCM は、対応する各リソース インスタンスにパラメーターとして".mof"ファイルに格納されているキーの値を使用します。

場合、結果の個々 のリソースの**テスト**は`$False`、`Test-DSCConfiguration`返します`$False`ノードが準拠していないことを示します。 場合すべてのリソースの**テスト**メソッドが返す`$True`、`Test-DSCConfiguration`返します`$True`ノードが準拠していることを示します。

```powershell
Test-DSCConfiguration
```

```output
True
```

PowerShell 5.0 以降、`-Detailed`パラメーターが追加されました。 指定する`-Detailed`により`Test-DSCConfiguration`を準拠、および非準拠リソースの検索結果のコレクションを格納するオブジェクトを返します。

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

詳細については、次を参照してください[Test-dscconfiguration。](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)

## <a name="set"></a>設定

**設定**リソースのメソッドが、リソースの準拠するためのノードを強制しようとしています。*目的の状態を*します。 **設定**メソッドがするものでは**べき等である**、つまり**設定**を複数回実行して、エラーのない同じ結果を常に取得できます。  実行すると[Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration)、現在適用されている構成内の各リソースを LCM 切り替えます。 LCM が".mof"ファイルから現在のリソース インスタンスのキーの値を取得し、それらをパラメーターとして使用、**テスト**メソッド。 場合、**テスト**メソッドを返します。 `$True`、ノードが現在のリソースに準拠して、**設定**メソッドはスキップされます。 場合、**テスト**返します`$False`ノードが非対応です。  LCM は、リソース インスタンスのキー値としてパラメーターに渡す、リソースの**設定**ノード コンプライアンスを復元する方法。

指定することによって、`-Verbose`と`-Wait`パラメーターの進行状況を見ることができます、`Start-DSCConfiguration`コマンドレット。 この例では、ノードは準拠では既にです。 `Verbose`出力には、ことを示します、**設定**メソッドはスキップされました。

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a>関連項目

- [Azure Automation DSC の概要](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)
- [Setting up an SMB pull server (SMB プル サーバーのセットアップ)](../pull-server/pullServerSMB.md)
- [Configuring a pull client (プル クライアントの構成)](../pull-server/pullClientConfigID.md)
