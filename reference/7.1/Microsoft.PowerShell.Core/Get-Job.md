---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-job?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Job
ms.openlocfilehash: 8a92e07746e86d4b0b84049f1f479a82c85e5e6f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217712"
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

### CommandParameterSet

```
Get-Job [-IncludeChildJob] [-ChildJobState <JobState>] [-HasMoreData <Boolean>] [-Before <DateTime>]
 [-After <DateTime>] [-Newest <Int32>] [-Command <String[]>] [<CommonParameters>]
```

### FilterParameterSet

```
Get-Job [-Filter] <Hashtable> [<CommonParameters>]
```

## Description

**Get-Job** コマンドレットは、現在のセッションで開始されたバックグラウンド ジョブを表すオブジェクトを取得します。 Start-Job コマンドレットを使用するか、任意のコマンドレットの *AsJob* パラメーターを使用して、開始されたジョブを **取得すること** ができます。

パラメーターを指定しない場合、 **Get Job** コマンドは、現在のセッション内のすべてのジョブを取得します。
**Get-Job** のパラメーターを使用すると、特定のジョブを取得できます。

**Get-Job** から返されるジョブ オブジェクトには、ジョブに関する有用な情報が含まれていますが、ジョブの結果は含まれません。 結果を取得するには、Receive-Job コマンドレットを使用します。

PowerShell バックグラウンドジョブは、現在のセッションと対話せずにバックグラウンドで実行されるコマンドです。 通常は、バックグラウンドジョブを使用して、完了までに時間がかかる複雑なコマンドを実行します。 PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」を参照してください。

Windows PowerShell 3.0 以降では、 **Get-Job** コマンドレットを使用して、ワークフロー ジョブ、スケジュールされたジョブのインスタンスなどのカスタムのジョブの種類を取得できます。 ジョブの種類を調べるには、ジョブの **PSJobTypeName** プロパティを使用します。

カスタムジョブの種類を **取得できるようにするに** は、カスタムジョブの種類をサポートするモジュールをセッションにインポートしてから、 **Import-Module コマンドレット** を使用するか、またはモジュールのコマンドレットを使用または取得します。 特定のカスタム ジョブの種類については、カスタムのジョブの種類機能のドキュメントを参照してください。

## 例

### 例 1: 現在のセッションで開始されているすべてのバックグラウンドジョブを取得する

```powershell
Get-Job
```

このコマンドは、現在のセッションで開始されたすべてのバックグラウンド ジョブを取得します。
ローカル コンピューター上でジョブが実行される場合でも、他のセッションで作成されたジョブは含まれません。

### 例 2: インスタンス ID を使用してジョブを停止する

ジョブのインスタンス ID を取得し、それを使用してジョブを停止する方法を次のコマンドに示します。
一意ではないジョブ名とは異なり、インスタンス ID は一意です。

```powershell
$j = Get-Job -Name Job1
$ID = $j.InstanceID
$ID
```

```Output
Guid
----
03c3232e-1d23-453b-a6f4-ed73c9e29d55
```

```powershell
Stop-Job -InstanceId $ID
```

最初のコマンドは、 **Get-Job** コマンドレットを使用して、ジョブを取得します。 この例では、 *Name* パラメーターを使用してジョブを識別します。 このコマンドは、 **Get-Job** から返されたジョブ オブジェクトを $j 変数に保存します。 この例では、指定された名前のジョブが 1 つだけあります。

2 番目のコマンドは、$j 変数内のオブジェクトの **InstanceId** プロパティを取得して、$ID 変数に保存します。

3 番目のコマンドは、$ID 変数の値を表示します。

4番目のコマンドは、Stop-Job コマンドレットを使用してジョブを停止します。 *InstanceId* パラメーターを使用してジョブを識別し、$ID 変数を使用してインスタンス ID を表しています。

### 例 3: 特定のコマンドを含むジョブを取得する

```powershell
Get-Job -Command "*get-process*"
```

このコマンドは、Get-Process コマンドを含むシステム上のジョブを取得します。 このコマンドは、 *Get-Job* の **Command** パラメーターを使用して取得するジョブを制限します。 コマンドは、ワイルドカード文字 (*) を使用して、コマンド文字列内の任意の場所にある **Get Process** コマンドを含むジョブを取得します。

### 例 4: パイプラインを使用して特定のコマンドを含むジョブを取得する

```powershell
"*get-process*" | Get-Job
```

前の例のコマンドと同様に、このコマンドは、 **Get Process** コマンドを含むシステム上のジョブを取得します。 このコマンドは、パイプライン演算子 (|) を使用して、文字列を引用符で囲んだ **後、コマンドレットに** 送信します。 これは、前のコマンドと同等です。

### 例 5: 開始されていないジョブを取得する

```powershell
Get-Job -State NotStarted
```

このコマンドは、作成されている一方でまだ開始されていないジョブのみを取得します。
これには、後で実行するようにスケジュール設定されているジョブとまだスケジュール設定されていないジョブが含まれます。

### 例 6: 名前が割り当てられていないジョブを取得する

```powershell
Get-Job -Name Job*
```

このコマンドは、job で始まるジョブ名を持つすべてのジョブを取得します。
Job \<number\> はジョブの既定の名前であるため、このコマンドは、明示的に名前が割り当てられていないすべてのジョブを取得します。

### 例 7: ジョブオブジェクトを使用してコマンド内のジョブを表す

この例は、 **Get-Job** を使用してジョブ オブジェクトを取得した後、そのジョブ オブジェクトを使用してコマンド内のジョブを表す方法を示しています。

```powershell
Start-Job -ScriptBlock {Get-Process} -Name MyJob
$j = Get-Job -Name MyJob
$j
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
6      MyJob           BackgroundJob   Completed     True            localhost            Get-Process
```

```powershell
Receive-Job -Job $j
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    124       4    13572      12080    59            1140 audiodg
    783      16    11428      13636   100             548 CcmExec
     96       4     4252       3764    59            3856 ccmsetup
...
```

最初のコマンドは、 **開始ジョブ** コマンドレットを使用して、ローカルコンピューターで **Get Process** コマンドを実行するバックグラウンドジョブを開始します。 このコマンドでは、 *Start-Job* の **Name** パラメーターを使用して、ジョブにフレンドリ名を割り当てています。

2 番目のコマンドは、Get-Job を使用してジョブを取得します。 ジョブを識別するために *Get-Job* の **Name** パラメーターが使用されています。 このコマンドは、結果のジョブ オブジェクトを $j 変数に保存します。

3 番目のコマンドは、$j 変数内のジョブ オブジェクトの値を表示します。 **State** プロパティの値は、ジョブが完了したことを示します。 **HasMoreData** プロパティの値は、このジョブに関してまだ取得されていない結果があることを示しています。

4番目のコマンドは **、job コマンドレットを** 使用して、ジョブの結果を取得します。 ジョブを表すために、$j 変数内のジョブ オブジェクトが使用されています。 パイプライン演算子を使用して、ジョブオブジェクトを **受信ジョブ** に送信することもできます。

### 例 8: 別の方法で開始されたジョブを含むすべてのジョブを取得する

この例では、別の方法を使用して開始された場合でも、 **Get Job** コマンドレットを使用して、現在のセッションで開始されたすべてのジョブを取得できることを示します。

```powershell
Start-Job -ScriptBlock {Get-EventLog System}
Invoke-Command -ComputerName S1 -ScriptBlock {Get-EventLog System} -AsJob
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Get-Job
```

```Output
Id     Name       PSJobTypeName   State         HasMoreData     Location        Command
--     ----       -------------   -----         -----------     --------        -------
1      Job1       BackgroundJob   Running       True            localhost       Get-EventLog System
2      Job2       RemoteJob       Running       True            S1              Get-EventLog System
```

```powershell
Invoke-Command -ComputerName S2 -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
```

```Output
Id    Name     PSJobTypeName  State      HasMoreData   Location   Command
--    ----     -------------  -----      -----------   -------    -------
4     Job4     BackgroundJob  Running    True          localhost  Get-Eventlog System
```

最初のコマンドは、 **Start ジョブ** コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。

2番目のコマンドは、 **コマンド** レットの *AsJob* パラメーターを使用して、S1 コンピューターでジョブを開始します。 ジョブに含まれるコマンドがリモート コンピューター上で実行される場合でもジョブ オブジェクトがローカル コンピューターに作成されるため、ローカル コマンドを使用してジョブを管理します。

3 番目のコマンドは、 **Invoke-Command** コマンドレットを使用して、S2 コンピューター上で **Start-Job** コマンドを実行します。 この方法を使用すると、ジョブオブジェクトがリモートコンピューター上に作成されるため、リモートコマンドを使用してジョブを管理します。

4 番目のコマンドは、 **Get-Job** を使用して、ローカル コンピューター上に格納されているジョブを取得します。 Windows PowerShell 3.0 で導入されたジョブの **PSJobTypeName** プロパティには、 **開始ジョブ** コマンドレットを使用して開始したローカルジョブがバックグラウンドジョブであり、 **Invoke コマンド** レットを使用してリモートセッションで開始されたジョブがリモートジョブであることが示されています。

5番目のコマンドは、 **コマンド** を使用して、S2 コンピューター上で **Get ジョブ** コマンドを実行します。サンプル出力には、Get-Job コマンドの結果が示されています。 S2 コンピューター上では、ジョブはローカル ジョブとして表示されます。 コンピューター名は localhost で、ジョブの種類はバックグラウンドジョブです。

リモートコンピューターでバックグラウンドジョブを実行する方法の詳細については、「about_Remote_Jobs」を参照してください。

### 例 9: 失敗したジョブを調査する

```powershell
Start-Job -ScriptBlock {Get-Process}
```

```Output
Id     Name       PSJobTypeName   State       HasMoreData     Location             Command
--     ----       -------------   -----       -----------     --------             -------
1      Job1       BackgroundJob   Failed      False           localhost            Get-Process
```

```powershell
(Get-Job).JobStateInfo | Format-List -Property *
```

```Output
State  : Failed
Reason :
```

```powershell
Get-Job | Format-List -Property *
```

```Output
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
```

```powershell
(Get-Job -Name job2).JobStateInfo.Reason
```

```Output
Connecting to remote server using WSManCreateShellEx api failed. The async callback gave the following error message: Access is denied.

For information about requirements for remoting in PowerShell, see about_Remote_Requirements. For
troubleshooting tips, see about_Remote_Troubleshooting.
```

このコマンドは、job が返すジョブオブジェクトを使用 **して、** ジョブが失敗した原因を調査する方法を示します。
また、各ジョブの子ジョブを取得する方法も示します。

最初のコマンドは、 **Start ジョブ** コマンドレットを使用して、ローカルコンピューター上でジョブを開始します。 **Start-Job** から返されるジョブ オブジェクトは、ジョブが失敗したことを示しています。 **State** プロパティの値が失敗しました。

2 番目のコマンドは、 **Get-Job** コマンドレットを使用して、ジョブを取得します。 ここでは、ドット表記を使用してオブジェクトの **JobStateInfo** プロパティの値を取得しています。 パイプライン演算子を使用して、 **Jobstateinfo** プロパティのオブジェクトを Format-List コマンドレットに送信します。これにより、オブジェクト (*) のすべてのプロパティが一覧表示されます。 **形式一覧** コマンドの結果は、ジョブの **Reason** プロパティの値が空白であることを示しています。

3番目のコマンドは、詳細を調査します。 このコマンドは、ジョブを取得するために、 **Get job** コマンドを使用します。次に、パイプライン演算子を使用して、ジョブオブジェクト全体を一覧表示します。このコマンドレットに **より** 、ジョブのすべてのプロパティがリストに表示されます。Job オブジェクトのすべてのプロパティの表示は、そのジョブに Job2 という名前の子ジョブが含まれていることを示しています。

4 番目のコマンドは、 **Get-Job** を使用して、Job2 子ジョブを表すジョブ オブジェクトを取得します。 これは、コマンドが実際に実行されたジョブです。 ここでは、ドットメソッドを使用して、 **Jobstateinfo** プロパティの **Reason** プロパティを取得します。結果には、アクセス拒否エラーによってジョブが失敗したことが示されます。 この場合、ユーザーは PowerShell の起動時に [管理者として実行] オプションを使用していません。バックグラウンドジョブは、PowerShell のリモート処理機能を使用するため、ローカルコンピューターでジョブが実行されている場合でも、ジョブを実行するリモート処理用にコンピューターを構成する必要があります。

### 例 10: フィルター処理された結果を取得する

この例では、 *Filter* パラメーターを使用してワークフロー ジョブを取得する方法を示します。
Windows PowerShell 3.0 で導入された *Filter* パラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、カスタムのジョブの種類でのみ有効です。

```powershell
Workflow WFProcess {Get-Process}
WFProcess -AsJob -JobName WFProcessJob -PSPrivateMetadata @{MyCustomId = 92107}
Get-Job -Filter @{MyCustomId = 92107}
```

```Output
Id     Name            State         HasMoreData     Location             Command
--     ----            -----         -----------     --------             -------
1      WFProcessJob    Completed     True            localhost            WFProcess
```

最初のコマンドは、 **workflow** キーワードを使用して、ワークフローのワークフローを作成します。

2番目のコマンドは、ワークフローをバックグラウンドジョブとして実行するために、処理されたプロセスワークフローの *AsJob* パラメーターを使用します。 ここでは、ワークフローの *JobName* パラメーターを使用してジョブの名前を指定し、ワークフローの *PSPrivateMetadata* パラメーターを使用してカスタム ID を指定しています。

3 番目のコマンドでは、 *Get-Job* の **Filter** パラメーターを使用して、 *PSPrivateMetadata* パラメーターで指定されたカスタム ID でジョブを取得しています。

### 例 11: 子ジョブに関する情報を取得する

この例は、 *Get-Job* コマンドレットの *IncludeChildJob* パラメーターと **ChildJobState** パラメーターを使用した場合の効果を示しています。

```powershell
Get-Job
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost            .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02   .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
Get-Job -IncludeChildJob
```

```Output
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
```

```powershell
Get-Job -Name Job4 -ChildJobState Failed
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
2      Job2            BackgroundJob   Completed     True            localhost           .\Get-Archive.ps1
4      Job4            RemoteJob       Failed        True            Server01, Server02  .\Get-Archive.ps1
5      Job5                            Failed        False           Server01            .\Get-Archive.ps1
7      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
8      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
9      UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
10     UpdateHelpJob   PSScheduledJob  Completed     True            localhost            Update-Help
```

```powershell
(Get-Job -Name Job5).JobStateInfo.Reason
```

```Output
Connecting to remote server Server01 failed with the following error message:
Access is denied.
For more information, see the about_Remote_Troubleshooting Help topic.
```

最初のコマンドは、現在のセッション内のジョブを取得します。 出力には、バックグラウンド ジョブ、リモート ジョブ、およびスケジュールされたジョブのいくつかのインスタンスが含まれます。 リモート ジョブ Job4 については、失敗したことが示されています。

2 番目のコマンドは、 *Get-Job* の **IncludeChildJob** パラメーターを使用します。 出力には、子ジョブを持つすべてのジョブの子ジョブが追加されます。この場合、変更後の出力には、Job4 の Job5 子ジョブのみが失敗したことが示されます。

3番目のコマンドは、 *Childjobstate* パラメーターを使用して、値が failed であることを示します。出力には、すべての親ジョブと、失敗した子ジョブのみが含まれます。

4番目のコマンドは、jobs の **Jobstateinfo** プロパティと **Reason** プロパティを使用して、Job5 が失敗した理由を検出します。

## PARAMETERS

### -After

指定された日時以降に終了した完了済みのジョブを取得します。 **Datetime** オブジェクトを入力します。たとえば、Get-Date コマンドレットによって返されるオブジェクトや、 **datetime** オブジェクトに変換できる文字列 (やなど) を入力し `Dec 1, 2012 2:00 AM` `11/06` ます。

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。 これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。 このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

このパラメーターは、ワークフロー ジョブ、スケジュールされたジョブなどの、 **EndTime** プロパティを持つカスタムのジョブの種類に対してのみ機能します。 これは、 **開始ジョブ** コマンドレットを使用して作成されたジョブなど、標準のバックグラウンドジョブでは機能しません。 このパラメーターのサポートについては、ジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.DateTime
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

**Receive-Job** コマンドレットを使用すると、メモリ内のセッション固有のストレージから、返された結果が削除されます。 現在のセッションでジョブのすべての結果が返された場合は、ジョブの **Hasmore data** プロパティの値を $False) に設定して、現在のセッションにジョブの結果がなくなったことを示します。 *Receive-Job* が結果を削除して **HasMoreData** プロパティの値を変更しないようにするには、 **Receive-Job** の **Keep** パラメーターを使用します。 詳細を表示するには「`Get-Help Receive-Job`」を入力します。

**HasMoreData** プロパティは、現在のセッションに固有です。 ジョブの結果をディスクに保存するスケジュールされたジョブの種類など、カスタムジョブの種類の結果がセッションの外部に保存される場合は、 **Hasdata** の値が $False 場合でも、別のセッションで **Receive-job** コマンドレットを使用して、ジョブの結果を再度取得できます。 詳細については、カスタムのジョブの種類のヘルプ トピックを参照してください。

このパラメーターは Windows PowerShell 3.0 で導入されました。

```yaml
Type: System.Boolean
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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
Parameter Sets: SessionIdParameterSet, InstanceIdParameterSet, NameParameterSet, StateParameterSet, CommandParameterSet
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

[Start-Job](Start-Job.md)

[Stop-Job](Stop-Job.md)

[Wait-Job](Wait-Job.md)

