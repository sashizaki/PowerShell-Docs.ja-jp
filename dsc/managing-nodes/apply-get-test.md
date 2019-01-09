---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノード上で構成を適用、取得、およびテストする
ms.openlocfilehash: 41f8d2d75d3dd9621de615e7999c2690cb8ce44a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402949"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a>ノード上で構成を適用、取得、およびテストする

このガイドでは、ターゲット ノードで構成を使用する方法を説明します。 このガイドは、次の手順に分割されます。

## <a name="apply-a-configuration"></a>構成を適用します。

適用しの構成を管理するためには、".mof"ファイルを生成する必要があります。 次のコードでは、このガイド全体で使用される単純な構成を表します。

```powershell
Configuration Sample
{
    # This will generate two .mof files, a localhost.mof, and a server02.mof
    Node localhost, server02
    {
        File SampleFile
        {
            DestinationPath = 'C:\Temp\temp.txt'
            Contents = 'This is a simple resource to show Configuration functionality on a Node.'
        }
    }
}

# The -OutputPath parameter is built into every Configuration automatically.
# The value of -OutputPath determines where the .mof file should be stored, once compiled.
Sample -OutputPath "C:\Temp\"
```

この構成をコンパイルすると、2 つの".mof"ファイルが生成されます。

```output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

構成を適用するには、使用、 [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)コマンドレット。 `-Path`パラメーターは、".mof"ファイルが存在するディレクトリを指定します。 ない場合は`-Computername`が指定されている`Start-DSCConfiguration`'.mof' ファイルの名前で指定したコンピューター名に各構成に適用されます (\<computername\>.mof)。 指定`-Verbose`に`Start-DSCConfiguration`をより詳細な出力を参照してください。

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

場合`-Wait`が指定されていない、1 つのジョブを作成するを参照してください。 作成されたジョブは 1 つが**ChildJob**によって処理される各".mof"ファイルの`Start-DSCConfiguration`します。

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

構成には、長い時間がかかると保護を停止する場合は、使用することができる場合[Stop-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)ローカル ノードでアプリケーションを停止します。

```powershell
Stop-DSCConfiguration -Force
```

によって返されるジョブ オブジェクトを介したジョブの状態を表示するには完了すると、 [Get-job](/powershell/module/microsoft.powershell.core/get-job)します。

```powershell
$job = Get-Job
$job.ChildJobs
```

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

参照してください、 **Verbose**出力を表示する、次のコマンドを使用して、 **Verbose**各ストリーム**ChildJob**します。 PowerShell ジョブの詳細についてを参照してください。 [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)します。

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-124525095-708259637-1543119021-1282804.
[SERVER01]: LCM:  [ Start  Set      ]
[SERVER01]: LCM:  [ Start  Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ Start  Test     ]  [[File]SampleFile]
[SERVER01]:                            [[File]SampleFile] The destination object was found and no action is required.
[SERVER01]: LCM:  [ End    Test     ]  [[File]SampleFile]  in 0.0370 seconds.
[SERVER01]: LCM:  [ Skip   Set      ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Set      ]
[SERVER01]: LCM:  [ End    Set      ]    in  0.2400 seconds.
Operation 'Invoke CimMethod' complete.
```

PowerShell 5.0 以降、`-UseExisting`にパラメーターが追加された`Start-DSCConfiguration`します。 指定して`-UseExisting`で指定されたいずれかの代わりに適用された既存の構成を使用するコマンドレットに指示する、`-Path`パラメーター。

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a>構成をテストします。

使用して現在適用されている構成をテストする[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)します。 `Test-DSCConfiguration` 戻ります`True`ノードが、準拠している場合と`False`でない場合。

```powershell
Test-DSCConfiguration
```

PowerShell 5.0 以降、`-Detailed`のコレクションを含むオブジェクトを返すパラメーターが追加された**ResourcesInDesiredState**と**ResourcesNotInDesiredState**

```powershell
Test-DSCConfiguration -Detailed
```

PowerShell 5.0 以降を適用することがなく、構成をテストできます。 `-ReferenceConfiguration`パラメーターは、テスト対象のノードに".mof"ファイルのパスを入力します。 いいえ**設定**ノードに対してアクションが実行されます。 PowerShell 4.0 では、それを適用せず、構成をテストする回避策がありますが、ここでは説明しません。

## <a name="get-configuration-values"></a>構成値を取得します。

[Get-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)コマンドレットは、現在適用されている構成で構成されているリソースの現在の値を返します。

```powershell
Get-DSCConfiguration
```

正常に適用されている場合、サンプルの構成からの出力は次のようになります。

```output
ConfigurationName    : Sample
DependsOn            :
ModuleName           : PSDesiredStateConfiguration
ModuleVersion        :
PsDscRunAsCredential :
ResourceId           : [File]SampleFile
SourceInfo           :
Attributes           : {archive}
Checksum             :
Contents             :
CreatedDate          : 11/27/2018 7:16:06 AM
Credential           :
DestinationPath      : C:\Temp\temp.txt
Ensure               : present
Force                :
MatchSource          :
ModifiedDate         : 11/27/2018 7:16:06 AM
Recurse              :
Size                 : 75
SourcePath           :
SubItems             :
Type                 : file
PSComputerName       :
CimClassName         : MSFT_FileDirectoryConfiguration
```

## <a name="get-configuration-status"></a>構成を状態します。

PowerShell 5.0 以降、 [Get-dscconfigurationstatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)コマンドレットを使用すると、ノードに適用される構成の履歴を参照してください。 PowerShell DSC の追跡に適用される最後の {{N}} 構成**プッシュ**または**プル**モード。 これが含まれる*整合性*チェック、LCM によって実行します。 既定では、`Get-DSCConfigurationStatus`最後の履歴エントリのみを示します。

```powershell
Get-DSCConfigurationStatus
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

使用して、`-All`パラメーターをすべての構成の状態の履歴を参照してください。

> [!NOTE]
> 簡潔にするための出力が切り捨てられます。

```powershell
Get-DSCConfigurationStatus -All
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
Success    11/27/2018 7:16:06 AM     Initial         PUSH  False                1
Success    11/27/2018 7:04:53 AM     Initial         PUSH  False                1
Success    11/27/2018 7:03:45 AM     Consistency     PUSH  False                2
Success    11/27/2018 7:03:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:48:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:44 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:18:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:03:44 AM     Consistency     PUSH  False                2
```

## <a name="manage-configuration-documents"></a>構成ドキュメントを管理します。

LCM と協力して、ノードの構成を管理**構成ドキュメント**します。 これらの".mof"ファイルは、"C:\Windows\System32\Configuration"ディレクトリに存在します。

PowerShell 5.0 以降、 [Remove-dscconfigurationdocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)将来の整合性チェックを停止するか、適用されるときにエラーがある構成を削除するには、".mof"ファイルを削除することができます。 `-Stage`パラメーターを削除する".mof"ファイルを指定できます。

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> PowerShell 4.0 を使用して直接これらの".mof"ファイルを削除することができますも[Remove-item](/powershell/module/microsoft.powershell.management/remove-item)します。

## <a name="publish-configurations"></a>発行の構成

PowerShell 5.0 以降、 [Publish-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)コマンドレットが追加されました。 このコマンドレットを使用すると、リモート コンピューターに適用することがなく".mof"ファイルを発行できます。

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a>関連項目

- [取得、テスト、および設定](../resources/get-test-set.md)
