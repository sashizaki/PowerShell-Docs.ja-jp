---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/suspend-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Suspend-Job
ms.openlocfilehash: 6ab50342e963832d89b3dfc4128a22fc16405926
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212723"
---
# Suspend-Job

## 概要
ワークフロー ジョブを一時的に停止します。

## SYNTAX

### SessionIdParameterSet (既定値)

```
Suspend-Job [-Force] [-Wait] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobParameterSet

```
Suspend-Job [-Job] <Job[]> [-Force] [-Wait] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NameParameterSet

```
Suspend-Job [-Force] [-Wait] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Suspend-Job [-Force] [-Wait] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FilterParameterSet

```
Suspend-Job [-Force] [-Wait] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StateParameterSet

```
Suspend-Job [-Force] [-Wait] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description
**Suspend ジョブ** コマンドレットは、ワークフロージョブを中断します。
中断とは、一時的にワークフロージョブを中断または一時停止することを意味します。
ワークフローを実行しているユーザーは、このコマンドレットを使用してワークフローを中断できます。
ワークフローを中断するワークフロー内のコマンドである、中断ワークフローアクティビティを補完し https://go.microsoft.com/fwlink/?LinkId=267141 ます。

**Suspend-Job** コマンドレットは、ワークフロー ジョブでのみ機能します。
これは、Start-Job コマンドレットを使用して開始されたものなど、標準のバックグラウンドジョブでは機能しません。

ワークフロー ジョブを識別するには、ジョブの PSJobTypeName プロパティで **PSWorkflowJob** の値を検索します。
特定のカスタム ジョブの種類で **Suspend-Job** コマンドレットがサポートされているかどうかを確認する方法については、カスタムのジョブの種類のヘルプ トピックを参照してください。

ワークフロー ジョブを中断すると、ワークフロー ジョブは次のチェックポイントまで実行された後で中断されます。その後、ワークフロー ジョブ オブジェクトが直ちに返されます。
ジョブを取得する前に中断が完了するまで待機するには、 **Suspend ジョブ** または Wait-Job コマンドレットの *wait* パラメーターを使用します。
ワークフロージョブが中断されている場合、ジョブの **State** プロパティの値は中断されます。

正しく中断できるかどうかはチェックポイントに依存します。
現在のジョブの状態、メタデータ、および出力がチェックポイントに保存されるため、状態やデータを失うことなくワークフロージョブを再開できます。
ワークフロージョブにチェックポイントがない場合、正常に中断することはできません。
実行中のワークフローにチェックポイントを追加するには、 *PSPersist* ワークフロー共通パラメーターを使用します。
*Force* パラメーターを使用すると、ワークフロージョブを即座に中断し、チェックポイントのないワークフロージョブを中断できますが、操作によって状態とデータが失われる可能性があります。

ワークフロージョブ ( **Psworkflowjob** ) などのカスタムジョブの種類で job コマンドレットを使用する前に、カスタムジョブの種類をサポートするモジュールをインポートします。そのためには、Import-Module コマンドレットを使用するか、またはモジュールのコマンドレットを使用します。

このコマンドレットは、Windows PowerShell 3.0 で導入されました。

## 例

### 例 1: 名前を指定してワークフロージョブを中断する

```
The first command creates the Get-SystemLog workflow. The workflow uses the CheckPoint-Workflow activity to define a checkpoint in the workflow.
#Sample WorkflowWorkflow Get-SystemLog
{
    $Events = Get-WinEvent -LogName System
    CheckPoint-Workflow
    InlineScript {\\Server01\Scripts\Analyze-SystemEvents.ps1 -Events $Events}
}

The second command uses the *AsJob* parameter that is common to all workflows to run the Get-SystemLog workflow as a background job. The command uses the *JobName* workflow common parameter to specify a friendly name for the workflow job.
PS C:\> Get-SystemLog -AsJob -JobName "Get-SystemLogJob"

The third command uses the **Get-Job** cmdlet to get the Get-SystemLogJob workflow job. The output shows that the value of the **PSJobTypeName** property is PSWorkflowJob.
PS C:\> Get-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Running     True            localhost   Get-SystemLog

The fourth command uses the **Suspend-Job** cmdlet to suspend the Get-SystemLogJob job. The job runs to the checkpoint and then suspends.
PS C:\> Suspend-Job -Name Get-SystemLogJob
Id     Name              PSJobTypeName   State       HasMoreData     Location   Command
--     ----              -------------   -----       -----------     --------   -------
4      Get-SystemLogJob  PSWorkflowJob   Suspended   True            localhost   Get-SystemLog
```

この例では、ワークフロー ジョブを中断する方法を示します。

### 例 2: ワークフロージョブを中断および再開する

```
The first command suspends the LogWorkflowJob job.The command returns immediately. The output shows that the workflow job is still running, even though it is being suspended.
PS C:\> Suspend-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow

The second command uses the **Get-Job** cmdlet to get the LogWorkflowJob job. The output shows that the workflow job suspended successfully.
PS C:\> Get-Job -Name LogWorkflowJob
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Suspended     True            localhost            LogWorkflow

The third command uses the **Get-Job** cmdlet to get the LogWorkflowJob job and the Resume-Job cmdlet to resume it. The output shows that the workflow job resumed successfully and is now running.
PS C:\> Get-Job -Name LogWorkflowJob | Resume-Job
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
67     LogflowJob    PSWorkflowJob      Running       True            localhost            LogWorkflow
```

この例では、ワークフロー ジョブを中断し、再開する方法を示します。

### 例 3: リモートコンピューター上のワークフロージョブを中断する

```
PS C:\> Invoke-Command -ComputerName Srv01 -Scriptblock {Suspend-Job -Filter @{CustomID="031589"}
```

このコマンドは、Invoke-Command コマンドレットを使用して、Srv01 リモートコンピューター上のワークフロージョブを中断します。
*Filter* パラメーターの値は、customid 値を指定するハッシュテーブルです。
この **CustomID** は、ジョブのメタデータ ( **PSPrivateMetadata** ) です。

### 例 4: ワークフロージョブが中断されるまで待機する

```
PS C:\> Suspend-Job VersionCheck -Wait
Id     Name          PSJobTypeName      State         HasMoreData     Location             Command
--     ----          -------------      -----         -----------     --------             -------
 5     VersionCheck  PSWorkflowJob      Suspended     True            localhost            LogWorkflow
```

このコマンドは、VersionCheck ワークフロー ジョブを中断します。
このコマンドでは、 *Wait* パラメーターを使用して、ワークフロー ジョブが中断されるのを待機しています。
ワークフロージョブが次のチェックポイントまで実行され、中断されると、コマンドが完了し、ジョブオブジェクトが返されます。

### 例 5: ワークフロージョブを強制的に中断する

```
PS C:\> Suspend-Job Maintenance -Force
```

このコマンドは、強制的に Maintenance ワークフロー ジョブを中断します。
メンテナンスジョブにチェックポイントがありません。
正しく中断することができず、正常に再開されない可能性があります。

## PARAMETERS

### -Filter
条件のハッシュテーブルを指定します。
このコマンドレットは、すべての条件に適合するジョブを中断します。
ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
ワークフロー ジョブを即座に中断します。
この操作により、状態とデータが失われる可能性があります。

既定では、 **Suspend-Job** は、ワークフロー ジョブを次のチェックポイントまで実行した後で中断します。
このパラメーターを使用すると、チェックポイントがないワークフロー ジョブも中断できます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: F

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
このコマンドレットが中断するジョブの Id を指定します。

ID は、現在のセッションでジョブを一意に識別する整数です。
インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。
1つ以上の Id をコンマで区切って入力できます。
ジョブの ID を検索するには、Get-Job コマンドレットを使用します。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InstanceId
このコマンドレットが中断するジョブのインスタンス Id を指定します。
既定値はすべてのジョブです。

インスタンス ID は、コンピューター上のジョブを一意に識別する GUID です。
ジョブのインスタンス ID を調べるには、 **Get-Job** を使用します。

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ジョブ
このコマンドレットが停止するワークフロージョブを指定します。
ワークフロー ジョブが格納されている変数、またはワークフロー ジョブを取得するコマンドを入力します。
パイプを使用してワークフロー ジョブを **Suspend-Job** コマンドレットに渡すこともできます。

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Name
このコマンドレットが中断するジョブのフレンドリ名を指定します。
1 つまたは複数のワークフロー ジョブ名を入力します。
ワイルドカード文字がサポートされています。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -状態
ジョブの状態を指定します。
このコマンドレットは、指定された状態のジョブのみを停止します。
このパラメーターの有効値は、次のとおりです。

- NotStarted
- 実行中
- 完了
- 失敗
- 停止済み
- Blocked
- Suspended
- [Disconnected]\(切断済み\)
- 中断中
- 停止中

**Suspend-ジョブ** は、 **実行** 状態のワークフロージョブのみを中断します。

ジョブの状態の詳細については、MSDN ライブラリの「 [Jobstate 列挙型](https://msdn.microsoft.com/library/system.management.automation.jobstate) 」を参照してください。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Wait
ワークフロージョブが中断状態になるまで、このコマンドレットによってコマンドプロンプトが抑制されることを示します。
既定では、 **中断ジョブ** は、ワークフロージョブがまだ中断状態になっていない場合でも、直ちに返されます。

*Wait* パラメーターは、 **Suspend ジョブ** を実行する **コマンドレットに** 渡します。

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

### -Confirm
コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
コマンドレットの実行時に発生する内容を示します。
このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター
このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### システム管理. ジョブ
このコマンドレットには、すべての種類のジョブをパイプすることができます。
ただし、 **中断ジョブ** がサポートされていない種類のジョブを取得すると、終了エラーが返されます。

## 出力

### システム管理. ジョブ
このコマンドレットは、中断されたジョブを返します。

## 注

* 中断されているジョブを保存するメカニズムと保存先の場所は、ジョブの種類によって異なる可能性があります。 たとえば、中断されているワークフロー ジョブは、既定でフラット ファイル ストアに保存されますが、データベースに保存することもできます。
* Running 状態にないワークフロー ジョブを送信すると、 **Suspend-Job** は警告メッセージを表示します。 警告を抑制するには、値が SilentlyContinue の *Warnings action* 共通パラメーターを使用します。

  ジョブが中断をサポートする種類ではない場合、 **中断ジョブ** は終了エラーを返します。

* 中断されているワークフロージョブ (このコマンドレットによって中断されたジョブを含む) を検索するには、 **get-help** コマンドレットの *state* パラメーターを使用して、中断状態のワークフロージョブを取得します。
* 一部のジョブの種類には、Windows PowerShell によるジョブの中断が許可されないオプションまたはプロパティを持つもあります。 ジョブを中断する試みが失敗した場合は、ジョブのオプションとプロパティで中断が許可されていることを確認します。

## 関連リンク

[Get-Job](Get-Job.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)
