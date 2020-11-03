---
external help file: Get-DSCLocalConfigurationManager.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 12/12/2019
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscLocalConfigurationManager
ms.openlocfilehash: 162770d8eb3a8953dcfaeb31f30742a46353b33b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215315"
---
# Get-DscLocalConfigurationManager

## 概要

ノードのローカル Configuration Manager (LCM) 設定と状態を取得します。

## SYNTAX

```
Get-DscLocalConfigurationManager [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## Description

この `Get-DscLocalConfigurationManager` コマンドレットは、lcm 設定、またはメタ構成、およびノードの lcm の状態を取得します。 Common Information Model (CIM) セッションを使用してコンピューターを指定します。 ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターから構成設定を取得します。

## 例

### 例 1: ローカルコンピューターの LCM 設定を取得する

```powershell
Get-DscLocalConfigurationManager
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 47edd8c9-2798-4827-839a-b35cc87e69fb
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName
```

このコマンドは、ローカルコンピューターの LCM 設定を取得します。

出力の個々の属性の詳細については、 [ローカル Configuration Manager の構成](../../docs-conceptual/dsc/managing-nodes/metaconfig.md#basic-settings) に関するドキュメントを参照してください。

### 例 2: 指定したコンピューターの LCM 設定を取得する

```powershell
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Get-DscLocalConfigurationManager -CimSession $Session
```

```Output
ActionAfterReboot              : ContinueConfiguration
AgentId                        : 169dfa57-a7f9-43be-a7a5-9dd06587e052
AllowModuleOverWrite           : False
CertificateID                  :
ConfigurationDownloadManagers  : {}
ConfigurationID                :
ConfigurationMode              : ApplyAndMonitor
ConfigurationModeFrequencyMins : 15
Credential                     :
DebugMode                      : {NONE}
DownloadManagerCustomData      :
DownloadManagerName            :
LCMCompatibleVersions          : {1.0, 2.0}
LCMState                       : Idle
LCMStateDetail                 :
LCMVersion                     : 2.0
StatusRetentionTimeInDays      : 10
SignatureValidationPolicy      : NONE
SignatureValidations           : {}
MaximumDownloadSizeMB          : 500
PartialConfigurations          :
RebootNodeIfNeeded             : False
RefreshFrequencyMins           : 30
RefreshMode                    : PUSH
ReportManagers                 : {}
ResourceModuleManagers         : {}
PSComputerName                 : Server01
PSComputerName                 : Server01
```

この例では、CIM セッションによって指定されたコンピューターの LCM 設定を取得します。
例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。
または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。

最初のコマンドは、コマンドレットを使用して CIM セッションを作成し、 `New-CimSession` その **CimSession** オブジェクトを $Session 変数に格納します。 コマンドはパスワードの入力をユーザーに求めます。 詳細を表示するには「`Get-Help New-CimSession`」を入力します。

2番目のコマンドは、$Session 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターのローカル Configuration Manager 設定を取得します。 この場合、Server01 という名前のコンピューターです。

## PARAMETERS

### -AsJob

このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

リモート セッションまたはリモート コンピューターでコマンドレットを実行します。 またはコマンドレットの出力など、コンピューター名またはセッションオブジェクトを入力し `New-CimSession` `Get-CimSession` ます。

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit

コマンドレットを実行するために確立できる最大並行処理数を指定します。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

## 出力

## 注

## 関連リンク

[Windows PowerShell Desired State Configuration の概要](/powershell/scripting/dsc/overview/dscforengineers)

[Set-DscLocalConfigurationManager](Set-DscLocalConfigurationManager.md)
