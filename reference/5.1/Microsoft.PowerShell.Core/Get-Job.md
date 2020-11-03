---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 0b9c76ca1e26adaa244473366c2eabdaaa28452c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212032"
---
# Get-Job

## 概要
現在のセッションで実行されている PowerShell バックグラウンドジョブを取得します。

## SYNTAX

### SessionIdParameterSet (既定値)

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [[-Id] <Int32[]>] [<CommonParameters>]
```

### CommandParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### InstanceIdParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-InstanceId] <Guid[]> [<CommonParameters>]
```

### NameParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Name] <String[]> [<CommonParameters>]
```

### StateParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-State] <JobState> [<CommonParameters>]
```

### FilterParameterSet

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## Description

**Get-Job** コマンドレットは、現在のセッションで開始されたバックグラウンド ジョブを表すオブジェクトを取得します。
Start-Job コマンドレットを使用するか、任意のコマンドレットの *AsJob* パラメーターを使用して、開始されたジョブを **取得すること** ができます。

パラメーターを指定しない場合、 **Get Job** コマンドは、現在のセッション内のすべてのジョブを取得します。
**Get-Job** のパラメーターを使用すると、特定のジョブを取得できます。

**Get-Job** から返されるジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。
結果を取得するには、Receive-Job コマンドレットを使用します。

Windows PowerShell のバックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。
通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。
Windows PowerShell のバックグラウンド ジョブの詳細については、「about_Jobs」を参照してください。

Windows PowerShell 3.0 以降では、 **Get-Job** コマンドレットを使用して、ワークフロー ジョブ、スケジュールされたジョブのインスタンスなどのカスタムのジョブの種類を取得できます。
ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。

カスタムジョブの種類を **取得できるようにするに** は、カスタムジョブの種類をサポートするモジュールをセッションにインポートしてから、 **Import-Module コマンドレット** を使用するか、またはモジュールのコマンドレットを使用または取得します。
特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。

## 例

### 例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する

```
PS C:\> Get-Job
```

このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。
ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。

### 例 2: インスタンス ID を使用してジョブを停止する

```
The first command uses the **Get-Job** cmdlet to get a job. It uses the *Name* parameter to identify the job. The command stores the job object that **Get-Job** returns in the $j variable. In this example, there is only one job with the specified name.
PS C:\> $j = Get-Job -Name Job1

The second command gets the **InstanceId** property of the object in the $j variable and stores it in the $ID variable.
PS C:\> $ID = $j.InstanceID

The third command displays the value of the $ID variable.
PS C:\> $ID

Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55

The fourth command uses Stop-Job cmdlet to stop the job. It uses the *InstanceId* parameter to identify the job and $ID variable to represent the instance ID of the job.
PS C:\> Stop-Job -InstanceId $ID
```

ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。
一意ではないジョブ名とは異なり、インスタンス ID は一意です。

### 例 3: 特定のコマンドを含むジョブを取得する

```
PS C:\> Get-Job -Command "*get-process*"
```

このコマンドは、Get-Process コマンドを含むシステム上のジョブを取得します。
このコマンドは、 *Get-Job* の **Command** パラメーターを使用して取得するジョブを制限します。
コマンドは、ワイルドカード文字 (*) を使用して、コマンド文字列内の任意の場所にある **Get Process** コマンドを含むジョブを取得します。

### 例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する

```
PS C:\> "*get-process*" | Get-Job
```

前の例のコマンドと同様に、このコマンドは、 **Get Process** コマンドを含むシステム上のジョブを取得します。
このコマンドは、パイプライン演算子 (|) を使用して、文字列を引用符で囲んだ **後、コマンドレットに** 送信します。
これは、前のコマンドと同等です。

### 例 5: 開始されていないジョブを取得する

```
PS C:\> Get-Job -State NotStarted
```

このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。
これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。

### 例 6: 名前が割り当てられていないジョブを取得する

```
PS C:\> Get-Job -Name Job*
```

このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。
Job \<number\> はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。

### 例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す

```
The first command uses the **Start-Job** cmdlet to start a background job that runs a **Get-Process** command on the local computer. The command uses the *Name* parameter of **Start-Job** to assign a friendly name to the job.
PS C:\> Start-Job -ScriptBlock {Get-Process} -Name MyJob

The second command uses Get-Job to get the job. It uses the *Name* parameter of **Get-Job** to identify the job. The command saves the resulting job object in the $j variable.
PS C:\> $j = Get-Job -Name MyJob

The third command displays the value of the job object in the $j variable. The value of the **State** property shows that the job is completed. The value of the **HasMoreData** property shows that there are results available from the job that have not yet been retrieved.
PS C:\> $j
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process

The fourth command uses the **Receive-Job** cmdlet to get the results of the job. It uses the job object in the $j variable to represent the job. You can also use a pipeline operator to send a job object to **Receive-Job**.
PS C:\> Receive-Job -Job $j
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

この例は、 **Get-Job** を使用してジョブ オブジェクトを取得した後、そのジョブ オブジェクトを使用してコマンド内のジョブを表す方法を示しています。

### 例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer.
PS C:\> Start-Job -ScriptBlock {Get-EventLog System}

The second command uses the *AsJob* parameter of the **Invoke-Command** cmdlet to start a job on the S1 computer. Even though the commands in the job run on the remote computer, the job object is created on the local computer, so you use local commands to manage the job.
PS C:\> Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob

The third command uses the **Invoke-Command** cmdlet to run a **Start-Job** command on the S2 computer. By using this method, the job object is created on the remote computer, so you use remote commands to manage the job.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}

The fourth command uses **Get-Job** to get the jobs stored on the local computer. The **PSJobTypeName** property of jobs, introduced in Windows PowerShell 3.0, shows that the local job started by using the **Start-Job** cmdlet is a background job and the job started in a remote session by using the **Invoke-Command** cmdlet is a remote job.
PS C:\> Get-Job
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System

The fifth command uses **Invoke-Command** to run a **Get-Job** command on the S2 computer.The sample output shows the results of the Get-Job command. On the S2 computer, the job appears to be a local job. The computer name is localhost and the job type is a background job.For more information about how to run background jobs on remote computers, see about_Remote_Jobs.
PS C:\> Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

この例では、別の方法を使用して開始された場合でも、 **Get Job** コマンドレットを使用して、現在のセッションで開始されたすべてのジョブを取得できることを示します。

### 例 9: 失敗したジョブを調査する

```
The first command uses the **Start-Job** cmdlet to start a job on the local computer. The job object that **Start-Job** returns shows that the job failed. The value of the **State** property is Failed.
PS C:\> Start-Job -ScriptBlock {Get-Process}
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process

The second command uses the **Get-Job** cmdlet to get the job. The command uses the dot method to get the value of the **JobStateInfo** property of the object. It uses a pipeline operator to send the object in the **JobStateInfo** property to the Format-List cmdlet, which formats all of the properties of the object (*) in a list.The result of the **Format-List** command shows that the value of the **Reason** property of the job is blank.
PS C:\> (Get-Job).JobStateInfo | Format-List -Property *
State  : Failed
Reason :

The third command investigates more. It uses a **Get-Job** command to get the job and then uses a pipeline operator to send the whole job object to the **Format-List** cmdlet, which displays all of the properties of the job in a list.The display of all properties in the job object shows that the job contains a child job named Job2.
PS C:\> Get-Job | Format-List -Property *
HasMoreData   : False
StatusMessage :
Location      : localhost
Command       : get-process
JobStateInfo  : Failed
Finished      : System.Threading.ManualReset
EventInstanceId    : fb792295-1318-4f5d-8ac8-8a89c5261507
Id            : 1
Name          : Job1
ChildJobs     : {Job2}
Output        : {}
Error         : {}
Progress      : {}
Verbose       : {}
Debug         : {}
Warning       : {}
StateChanged  :

The fourth command uses **Get-Job** to get the job object that represents the Job2 child job. This is the job in which the command actually ran. It uses the dot method to get the **Reason** property of the **JobStateInfo** property.The result shows that the job failed because of an Access Denied error. In this case, the user forgot to use the Run as administrator option when starting Windows PowerShell.Because background jobs use the remoting features of Windows PowerShell, the computer must be configured for remoting to run a job, even when the job runs on the local computer.For information about requirements for remoting in Windows PowerShell, see about_Remote_Requirements. For troubleshooting tips, see about_Remote_Troubleshooting.
PS C:\> (Get-Job -Name job2).JobStateInfo.Reason
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.
```

このコマンドは、job が返すジョブオブジェクトを使用 **して、** ジョブが失敗した原因を調査する方法を示します。
また、各ジョブの子ジョブを取得する方法も示します。

### 例 10: フィルター処理された結果を取得する

```
The first command uses the **Workflow** keyword to create the WFProcess workflow.
PS C:\> Workflow WFProcess {Get-Process}

The second command uses the *AsJob* parameter of the WFProcess workflow to run the workflow as a background job. It uses the *JobName* parameter of the workflow to specify a name for the job, and the *PSPrivateMetadata* parameter of the workflow to specify a custom ID.
PS C:\> WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}

The third command uses the *Filter* parameter of **Get-Job** to get the job by custom ID that was specified in the *PSPrivateMetadata* parameter.
PS C:\> Get-Job -Filter @{MyCustomId = 92107}
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

この例では、 *Filter* パラメーターを使用してワークフロー ジョブを取得する方法を示します。
Windows PowerShell 3.0 で導入された *Filter* パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。

### 例 11: 子ジョブに関する情報を取得する

```
The first command gets the jobs in the current session. The output includes a background job, a remote job and several instances of a scheduled job. The remote job, Job4, appears to have failed.
PS C:\> Get-Job
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The second command uses the *IncludeChildJob* parameter of **Get-Job**. The output adds the child jobs of all jobs that have child jobs.In this case, the revised output shows that only the Job5 child job of Job4 failed.
PS C:\> Get-Job -IncludeChildJob
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
3      Job3                            Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
6      Job6                            Completed     True            Server02            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The third command uses the *ChildJobState* parameter with a value of Failed.The output includes all parent jobs and only the child jobs that failed.
PS C:\> Get-Job -Name Job4 -ChildJobState Failed
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help

The fifth command uses the **JobStateInfo** property of jobs and its **Reason** property to discover why Job5 failed.
PS C:\> (Get-Job -Name Job5).JobStateInfo.Reason
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

この例は、 *Get-Job* コマンドレットの *IncludeChildJob* パラメーターと **ChildJobState** パラメーターを使用した場合の効果を示しています。

## PARAMETERS

### -After

指定された日時以降に終了した完了済みのジョブを取得します。
**Datetime** オブジェクトを入力します。たとえば、Get-Date コマンドレットによって返されるオブジェクトや、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。
これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。
このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Before

指定された日時以前に終了した完了済みのジョブを取得します。
**DateTime** オブジェクトを入力します。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。
これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。
このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ChildJobState

指定された状態を持つ子ジョブのみを取得します。
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

既定では、 **Get-Job** は子ジョブを取得しません。
*IncludeChildJob* パラメーターを使用すると **、すべて** の子ジョブが取得されます。
*ChildJobState* パラメーターを使用した場合、 *IncludeChildJob* パラメーターは効果を持ちません。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Command

コマンドの配列を文字列として指定します。
このコマンドレットは、指定されたコマンドを含むジョブを取得します。
既定値はすべてのジョブです。
ワイルドカード文字を使用すると、コマンドパターンを指定できます。

```yaml
Type: System.String[]
Parameter Sets: CommandParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -Filter

条件のハッシュテーブルを指定します。
このコマンドレットは、すべての条件に適合するジョブを取得します。
ジョブのプロパティをキー、ジョブのプロパティ値を値とするハッシュ テーブルを入力します。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類に対してのみ機能します。
これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。
このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

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

### -Hasdata

このコマンドレットが、指定された **hasを持つデータ** プロパティ値を持つジョブのみを取得するかどうかを示します。
**HasMoreData** プロパティは、すべてのジョブの結果が現在のセッションで受け取られたかどうかを示します。
より多くの結果を持つジョブを取得するには、$True の値を指定します。
より多くの結果が得られないジョブを取得するには、$False の値を指定します。

ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。

**Receive-Job** コマンドレットを使用すると、メモリ内のセッション固有のストレージから、返された結果が削除されます。
現在のセッションでジョブのすべての結果が返された場合は、ジョブの **Hasmore data** プロパティの値を $False) に設定して、現在のセッションにジョブの結果がなくなったことを示します。
*Receive-Job* が結果を削除して **HasMoreData** プロパティの値を変更しないようにするには、 **Receive-Job** の **Keep** パラメーターを使用します。
詳細を表示するには「`Get-Help Receive-Job`」を入力します。

**HasMoreData** プロパティは、現在のセッションに固有です。
ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 **Hasdata** の値が $False 場合でも、別のセッションで **Receive-job** コマンドレットを使用して、ジョブの結果を再度取得できます。
詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id

このコマンドレットが取得するジョブの Id の配列を指定します。

ID は、現在のセッションでジョブを一意に識別する整数です。
インスタンス ID よりも覚えやすく、入力する方が簡単ですが、現在のセッションでのみ一意です。
1つ以上の Id をコンマで区切って入力できます。
ジョブの ID を検索するには、パラメーターを指定せずに「」と入力 `Get-Job` します。

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IncludeChildJob

このコマンドレットが親ジョブに加えて子ジョブも返すことを示します。

このパラメーターは、エラーの原因が子ジョブのプロパティに保存されているので、ワークフロージョブを調査する場合に特に便利です。この場合、ジョブの親ジョブとジョブの失敗 **が返され** ます。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceId

このコマンドレットが取得するジョブのインスタンス Id の配列を指定します。
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

### -Name

このコマンドレットが取得するジョブのインスタンスフレンドリ名の配列を指定します。
ジョブの名前を入力するか、またはワイルドカード文字を使用してジョブ名のパターンを入力します。
既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -最新

取得するジョブの数を指定します。
このコマンドレットは、最後に終了したジョブを取得します。

*Newest* パラメーターは、並べ替えを行わずに、終了時刻の順で最も新しいジョブを返します。
出力を並べ替えるには、Sort-Object コマンドレットを使用します。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Int32
Parameter Sets: SessionIdParameterSet, CommandParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -状態

ジョブの状態を指定します。
このコマンドレットは、指定された状態のジョブのみを取得します。
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

既定では、 **Get-Job** は、現在のセッション内のすべてのジョブを取得します。

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

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットに入力を渡すことはできません。

## 出力

### System. Automation. RemotingJob

このコマンドレットは、セッション内のジョブを表すオブジェクトを返します。

## 注

* ジョブの **PSJobTypeName** プロパティは、ジョブの種類を示します。 プロパティ値は、ジョブの種類の作成者によって決定されます。 次の一覧に、一般的なジョブの種類を示します。

  - **Backgroundjob** 。
ローカルジョブは **、開始ジョブ** を使用して開始されました。

  - **Remotejob** 。
Invoke-Command コマンドレットの *AsJob* パラメーターを使用して、 **PSSession** でジョブが開始されました。

  - **Psworkflowjob** 。
ワークフローの *AsJob* 共通パラメーターを使用して開始されたジョブ。

## 関連リンク

[Invoke-Command](Invoke-Command.md)

[Receive-Job](Receive-Job.md)

[Remove-Job](Remove-Job.md)

[Resume-Job](Resume-Job.md)

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Suspend-Job](Suspend-Job.md)

[Wait-Job](Wait-Job.md)

[about_Jobs](About/about_Jobs.md)

[about_Job_Details](About/about_Job_Details.md)

[about_Remote_Jobs](About/about_Remote_Jobs.md)

[about_Scheduled_Jobs](../PSScheduledJob/About/about_Scheduled_Jobs.md)
