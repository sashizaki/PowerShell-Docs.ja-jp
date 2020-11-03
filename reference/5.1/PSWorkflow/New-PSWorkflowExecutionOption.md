---
external help file: Microsoft.Powershell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSWorkflow
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/new-psworkflowexecutionoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSWorkflowExecutionOption
ms.openlocfilehash: db5d19396f555a41ad14552823c57f3b11c79321
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218288"
---
# New-PSWorkflowExecutionOption

## 概要

ワークフロー セッションのセッション構成オプションを格納したオブジェクトを作成します。

## SYNTAX

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## Description

この `New-PSWorkflowExecutionOption` コマンドレットは、ワークフローセッション構成の詳細オプションを含むオブジェクトを作成します。これは、Windows PowerShell ワークフローワークフローを実行するように設計されたセッション構成です。

**PSWorkflowExecutionOption** `New-PSWorkflowExecutionOption` およびコマンドレットなど、セッション構成を作成または変更するコマンドレットの **sessiontypeoption** パラメーターの値として生成される psworkflowexecutionoption オブジェクトを使用でき `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` ます。

コマンドレットの各パラメーターは、この `New-PSWorkflowExecutionOption` コマンドレットが返すワークフローセッション構成オプションオブジェクトのプロパティを表します。 パラメーターを省略した場合、このコマンドレットはプロパティの既定値でオブジェクトを作成します。

`New-PSWorkflowExecutionOption`コマンドレットは、Windows PowerShell ワークフロー機能の一部です。

このコマンドにワークフロー共通パラメーターを追加することもできます。 ワークフロー共通パラメーターの詳細については、「 [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)」を参照してください。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: ワークフローオプションオブジェクトを作成する

```powershell
New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
```

```Output
SessionThrottleLimit                       : 100
PersistencePath                            : C:\Users\User01\AppData\Local\Microsoft\Windows\PowerShell\WF\PS
MaxPersistenceStoreSizeGB                  : 10
PersistWithEncryption                      : False
MaxRunningWorkflows                        : 30
AllowedActivity                            : {PSDefaultActivities}
OutOfProcessActivity                       : {InlineScript}
EnableValidation                           : True
MaxDisconnectedSessions                    : 200
MaxConnectedSessions                       : 100
MaxSessionsPerWorkflow                     : 10
MaxSessionsPerRemoteNode                   : 5
MaxActivityProcesses                       : 5
ActivityProcessIdleTimeoutSec              : 60
RemoteNodeSessionIdleTimeoutSec            : 60
WorkflowShutdownTimeoutMSec                : 500
```

このコマンドは、コマンドレットを使用して `New-PSWorkflowExecutionOption` **Maxsessionsperworkflow** の値を10に増やし、 **maxsessionsperworkflow** の値を200に減らします。

出力には、このコマンドレットから返されたオブジェクトが示されています。

### 例 2: ワークフローオプションオブジェクトの使用

```powershell
# Create a Workflow Options object and save it in a variable
$wo = New-PSWorkflowExecutionOption -MaxSessionsPerWorkflow 10 -MaxDisconnectedSessions 200
# Create the ITWorkflow session configuration
Register-PSSessionConfiguration -Name ITWorkflows -SessionTypeOption $wo -Force
```

```Output
    WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type            Keys                                Name
----            ----                                ----
Container       {Name=ITWorkflows}                  ITWorkflows
```

```powershell
Get-PSSessionConfiguration ITWorkflows | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITWorkflows
MaxConcurrentCommandsPerShell : 1000
allowedactivity               : PSDefaultActivities
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
maxsessionsperworkflow        : 10
lang                          : en-US
sessionconfigurationdata      : <SessionConfigurationData>
                                    <Param Name='PrivateData'>
                                        <PrivateData>
                                            <ParamName='enablevalidation' Value='True'/>
                                            <Param Name='allowedactivity'Value='PSDefaultActivities' />
                                            <Param Name='outofprocessactivity' Value='InlineScript'/>
                                            <Param Name='maxdisconnectedsessions' Value='200' />
                                            <ParamName='maxsessionsperworkflow' Value='10'/>
                                        </PrivateData>
                                    </Param>
                                </SessionConfigurationData>
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 25
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
outofprocessactivity          : InlineScript
SDKVersion                    : 2
Name                          : ITWorkflows
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
enablevalidation              : True
Enabled                       : True
maxdisconnectedsessions       : 200
MaxShellsPerUser              : 25
Permission                    :
```

最初の2つのコマンドは、新しいセッション構成オブジェクトを作成し、それを登録します。

3番目のコマンドは、コマンドレットを使用して ITWorkflows セッション構成を取得し、を使用して `Get-PSSessionConfiguration` `Format-List` セッション構成のすべてのプロパティを一覧に表示します。出力には、セッション構成のワークフローオプションが表示されます。 具体的には、セッション構成の **MaxSessionsPerWorkflow** プロパティの値が 10 に、 **MaxDisconnectedSessions** プロパティの値が 200 になっています。

## PARAMETERS

### -ActivityProcessIdleTimeoutSec

各アクティビティのホスト プロセスがアイドル状態になった後にプロセスを維持する期間を決定します。 この期間を過ぎると、プロセスは閉じられます。

値を秒単位で入力します。 既定値は 60 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowedActivity

セッションで実行を許可するアクティビティを指定します。

名前空間で修飾されたアクティビティ名を入力します (例:) `Microsoft.Powershell.HyperV.Activities.*` 。
ワイルドカード文字がサポートされています。 既定値の **PSDefaultActivities** には、組み込みの Windows Workflow Foundation アクティビティと、Windows PowerShell コア コマンドレットを表すアクティビティが含まれます。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: PSDefaultActivities
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableValidation

許可するアクティビティの一覧にセッション内のすべてのワークフロー アクティビティが含まれていることを確認します。

既定値は True です。 検証を無効にするには、次のコマンド形式を使用し `-EnableValidation:$false` ます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxActivityProcesses

ワークフロー アクティビティをサポートするためにセッションで作成できるプロセスの最大数を指定します。 既定値は 5 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxConnectedSessions

操作状態にあるリモート セッションの最大数を指定します。 このクォータは、すべてのリモート ノード (ターゲット コンピューター) に接続されているセッションに適用されます。 既定値は 100 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxDisconnectedSessions

切断状態にあるリモート セッションの最大数を指定します。 このクォータは、すべてのリモート ノード (ターゲット コンピューター) に接続されているセッションに適用されます。 既定値は 1000 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 1000
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPersistenceStoreSizeGB

セッションで実行するワークフローに割り当てる永続化ストアの最大サイズをギガバイト単位で指定します。 このサイズを超えた場合、永続化されたデータをすべて保存するために永続化ストアが拡張されます。ただし、警告が表示され、ワークフローのイベント ログにメッセージが書き込まれます。 既定値は 10 です。

永続化ストアには、すべてのワークフロー ジョブのデータが格納されています。 データの格納機能により、状態を失うことなくジョブを再開できます。

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 10
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxRunningWorkflows

セッションで同時に実行できるワークフローの最大数を指定します。
既定値は 30 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 30
Accept pipeline input: False
Accept wildcard characters: False
```

### -Maxsessionsperremoを

各リモート ノード (ターゲット コンピューター) に接続できるセッションの最大数を指定します。 既定値は 5 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSessionsPerWorkflow

各ワークフローをサポートするために作成できるセッションの最大数を指定します。 既定値は 5 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutOfProcessActivity

アウト プロセスで実行する ( **AllowedActivities** パラメーターで指定された) 許可されたアクティビティを指定します。 既定値は **InlineScript** です。

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: InlineScript
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistencePath

ワークフローの状態とデータを格納するディスク上の場所を指定します。 ワークフローの状態とデータを格納することで、ワークフローを中断した後で再開することや、割り込みやネットワークの障害から復旧することができます。

既定値は `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS` です。

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PersistWithEncryption

ワークフローが永続化ストア内のデータを暗号化することを示します。 ネットワーク共有に永続データを格納する場合は、この機能の使用を検討してください。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: $env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteNodeSessionIdleTimeoutSec

リモート ノード (ターゲット コンピューター) に接続しているアイドル状態のセッションを維持する期間を指定します。

値を秒単位で入力します。 既定値は 60 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 60
Accept pipeline input: False
Accept wildcard characters: False
```

### -SessionThrottleLimit

セッションで開始されたすべてのワークフローをサポートするために作成する操作の数を指定します。 既定値は 100 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 100
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkflowShutdownTimeoutMSec 秒

セッション内のすべてのワークフローが強制的に中断された後にセッションを維持する期間を指定します。 このタイムアウトを過ぎると、すべてのワークフローがまだ中断されていなくでも、セッションが閉じられます。

値をミリ秒単位で入力します。
既定値は 500 です。

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 500
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### Microsoft. PowerShell. PSWorkflowExecutionOption

## 注

オプションによって設定された最大値を超えると、パラメーターの説明に記載されている場合を除き、セッションに別のインスタンスを作成するコマンドは失敗します。 たとえば、 **MaxConnectedSessions** の値が 100 の場合、 リモート ノード (ターゲット コンピューター) に 101 個目のセッションを作成するコマンドは失敗します。

セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。 また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。

特に、 **PSWorkflowExecutionOptions** オブジェクトが含まれるセッション構成のプロパティは、ワークフロー オプションの値によって異なります。 たとえば、 **SessionThrottleLimit** プロパティに既定以外の値を設定する **PSWorkflowExecutionOptions** オブジェクトがセッション構成に含まれる場合、そのセッション構成には **SessionThrottleLimit** プロパティが存在します。 それ以外の場合、存在しません。

## 関連リンク

[New-PSWorkflowSession](New-PSWorkflowSession.md)

[about_Workflows](../PSWorkflow/About/about_Workflows.md)

[about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)
