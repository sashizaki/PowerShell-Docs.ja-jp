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
# <span data-ttu-id="11e68-103">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="11e68-103">New-PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="11e68-104">概要</span><span class="sxs-lookup"><span data-stu-id="11e68-104">SYNOPSIS</span></span>

<span data-ttu-id="11e68-105">ワークフロー セッションのセッション構成オプションを格納したオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="11e68-105">Creates an object that contains session configuration options for workflow sessions.</span></span>

## <span data-ttu-id="11e68-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11e68-106">SYNTAX</span></span>

```
New-PSWorkflowExecutionOption [-PersistencePath <String>] [-MaxPersistenceStoreSizeGB <Int64>]
 [-PersistWithEncryption] [-MaxRunningWorkflows <Int32>] [-AllowedActivity <String[]>]
 [-OutOfProcessActivity <String[]>] [-EnableValidation] [-MaxDisconnectedSessions <Int32>]
 [-MaxConnectedSessions <Int32>] [-MaxSessionsPerWorkflow <Int32>] [-MaxSessionsPerRemoteNode <Int32>]
 [-MaxActivityProcesses <Int32>] [-ActivityProcessIdleTimeoutSec <Int32>]
 [-RemoteNodeSessionIdleTimeoutSec <Int32>] [-SessionThrottleLimit <Int32>]
 [-WorkflowShutdownTimeoutMSec <Int32>] [<CommonParameters>]
```

## <span data-ttu-id="11e68-107">Description</span><span class="sxs-lookup"><span data-stu-id="11e68-107">DESCRIPTION</span></span>

<span data-ttu-id="11e68-108">この `New-PSWorkflowExecutionOption` コマンドレットは、ワークフローセッション構成の詳細オプションを含むオブジェクトを作成します。これは、Windows PowerShell ワークフローワークフローを実行するように設計されたセッション構成です。</span><span class="sxs-lookup"><span data-stu-id="11e68-108">The `New-PSWorkflowExecutionOption` cmdlet creates an object that contains advanced options for workflow session configurations, that is session configurations designed to run Windows PowerShell Workflow workflows.</span></span>

<span data-ttu-id="11e68-109">**PSWorkflowExecutionOption** `New-PSWorkflowExecutionOption` およびコマンドレットなど、セッション構成を作成または変更するコマンドレットの **sessiontypeoption** パラメーターの値として生成される psworkflowexecutionoption オブジェクトを使用でき `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="11e68-109">You can use the **PSWorkflowExecutionOption** object that `New-PSWorkflowExecutionOption` generates as the value of the **SessionTypeOption** parameter of cmdlets that create or change a session configuration, such as the `Register-PSSessionConfiguration` and `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="11e68-110">コマンドレットの各パラメーターは、この `New-PSWorkflowExecutionOption` コマンドレットが返すワークフローセッション構成オプションオブジェクトのプロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="11e68-110">Each parameter of the `New-PSWorkflowExecutionOption` cmdlet represents a property of the workflow session configuration option object that the cmdlet returns.</span></span> <span data-ttu-id="11e68-111">パラメーターを省略した場合、このコマンドレットはプロパティの既定値でオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="11e68-111">If you omit a parameter, the cmdlet creates the object with a default value for the property.</span></span>

<span data-ttu-id="11e68-112">`New-PSWorkflowExecutionOption`コマンドレットは、Windows PowerShell ワークフロー機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="11e68-112">The `New-PSWorkflowExecutionOption` cmdlet is part of the Windows PowerShell Workflow feature.</span></span>

<span data-ttu-id="11e68-113">このコマンドにワークフロー共通パラメーターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="11e68-113">You can also add workflow common parameters to this command.</span></span> <span data-ttu-id="11e68-114">ワークフロー共通パラメーターの詳細については、「 [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11e68-114">For more information about workflow common parameters, see [about_WorkflowCommonParameters](About/about_WorkflowCommonParameters.md).</span></span>

<span data-ttu-id="11e68-115">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="11e68-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="11e68-116">例</span><span class="sxs-lookup"><span data-stu-id="11e68-116">EXAMPLES</span></span>

### <span data-ttu-id="11e68-117">例 1: ワークフローオプションオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="11e68-117">Example 1: Create a Workflow Options Object</span></span>

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

<span data-ttu-id="11e68-118">このコマンドは、コマンドレットを使用して `New-PSWorkflowExecutionOption` **Maxsessionsperworkflow** の値を10に増やし、 **maxsessionsperworkflow** の値を200に減らします。</span><span class="sxs-lookup"><span data-stu-id="11e68-118">This command uses the `New-PSWorkflowExecutionOption` cmdlet to increase the **MaxSessionsPerWorkflow** value to 10 and decrease the **MaxDisconnectedSessions** value to 200.</span></span>

<span data-ttu-id="11e68-119">出力には、このコマンドレットから返されたオブジェクトが示されています。</span><span class="sxs-lookup"><span data-stu-id="11e68-119">The output shows the object that the cmdlet returns.</span></span>

### <span data-ttu-id="11e68-120">例 2: ワークフローオプションオブジェクトの使用</span><span class="sxs-lookup"><span data-stu-id="11e68-120">Example 2: Using a Workflow Options Object</span></span>

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

<span data-ttu-id="11e68-121">最初の2つのコマンドは、新しいセッション構成オブジェクトを作成し、それを登録します。</span><span class="sxs-lookup"><span data-stu-id="11e68-121">The first two commands create a new session configuration object and registers it.</span></span>

<span data-ttu-id="11e68-122">3番目のコマンドは、コマンドレットを使用して ITWorkflows セッション構成を取得し、を使用して `Get-PSSessionConfiguration` `Format-List` セッション構成のすべてのプロパティを一覧に表示します。出力には、セッション構成のワークフローオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11e68-122">The third command uses the `Get-PSSessionConfiguration` cmdlet to the get the ITWorkflows session configuration and the `Format-List` to display all properties of the session configuration in a list.The output shows that the workflow options in the session configuration.</span></span> <span data-ttu-id="11e68-123">具体的には、セッション構成の **MaxSessionsPerWorkflow** プロパティの値が 10 に、 **MaxDisconnectedSessions** プロパティの値が 200 になっています。</span><span class="sxs-lookup"><span data-stu-id="11e68-123">Specifically, the session configuration has a **MaxSessionsPerWorkflow** property with a value of 10 and a **MaxDisconnectedSessions** property with a value of 200.</span></span>

## <span data-ttu-id="11e68-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11e68-124">PARAMETERS</span></span>

### <span data-ttu-id="11e68-125">-ActivityProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="11e68-125">-ActivityProcessIdleTimeoutSec</span></span>

<span data-ttu-id="11e68-126">各アクティビティのホスト プロセスがアイドル状態になった後にプロセスを維持する期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-126">Determines how long each activity host process is maintained after the process becomes idle.</span></span> <span data-ttu-id="11e68-127">この期間を過ぎると、プロセスは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="11e68-127">When the interval expires, the process closes.</span></span>

<span data-ttu-id="11e68-128">値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="11e68-128">Enter a value in seconds.</span></span> <span data-ttu-id="11e68-129">既定値は 60 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-129">The default value is 60.</span></span>

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

### <span data-ttu-id="11e68-130">-AllowedActivity</span><span class="sxs-lookup"><span data-stu-id="11e68-130">-AllowedActivity</span></span>

<span data-ttu-id="11e68-131">セッションで実行を許可するアクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-131">Specifies the activities that are permitted to run in the session.</span></span>

<span data-ttu-id="11e68-132">名前空間で修飾されたアクティビティ名を入力します (例:) `Microsoft.Powershell.HyperV.Activities.*` 。</span><span class="sxs-lookup"><span data-stu-id="11e68-132">Enter namespace-qualified activity names, such as `Microsoft.Powershell.HyperV.Activities.*`.</span></span>
<span data-ttu-id="11e68-133">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11e68-133">Wildcard characters are supported.</span></span> <span data-ttu-id="11e68-134">既定値の **PSDefaultActivities** には、組み込みの Windows Workflow Foundation アクティビティと、Windows PowerShell コア コマンドレットを表すアクティビティが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11e68-134">The default value, **PSDefaultActivities** , includes the built-in Windows Workflow Foundation activities and the activities that represent the Windows PowerShell Core cmdlets.</span></span>

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

### <span data-ttu-id="11e68-135">-EnableValidation</span><span class="sxs-lookup"><span data-stu-id="11e68-135">-EnableValidation</span></span>

<span data-ttu-id="11e68-136">許可するアクティビティの一覧にセッション内のすべてのワークフロー アクティビティが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11e68-136">Verifies that all workflow activities in the session are included in the allowed activities list.</span></span>

<span data-ttu-id="11e68-137">既定値は True です。</span><span class="sxs-lookup"><span data-stu-id="11e68-137">The default value is True.</span></span> <span data-ttu-id="11e68-138">検証を無効にするには、次のコマンド形式を使用し `-EnableValidation:$false` ます。</span><span class="sxs-lookup"><span data-stu-id="11e68-138">To disable validation, use the following command format: `-EnableValidation:$false`.</span></span>

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

### <span data-ttu-id="11e68-139">-MaxActivityProcesses</span><span class="sxs-lookup"><span data-stu-id="11e68-139">-MaxActivityProcesses</span></span>

<span data-ttu-id="11e68-140">ワークフロー アクティビティをサポートするためにセッションで作成できるプロセスの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-140">Specifies the maximum number of processes that can be created in the session to support workflow activities.</span></span> <span data-ttu-id="11e68-141">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-141">The default value is 5.</span></span>

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

### <span data-ttu-id="11e68-142">-MaxConnectedSessions</span><span class="sxs-lookup"><span data-stu-id="11e68-142">-MaxConnectedSessions</span></span>

<span data-ttu-id="11e68-143">操作状態にあるリモート セッションの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-143">Specifies the maximum number of remote sessions that are in an operational state.</span></span> <span data-ttu-id="11e68-144">このクォータは、すべてのリモート ノード (ターゲット コンピューター) に接続されているセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="11e68-144">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="11e68-145">既定値は 100 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-145">The default value is 100.</span></span>

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

### <span data-ttu-id="11e68-146">-MaxDisconnectedSessions</span><span class="sxs-lookup"><span data-stu-id="11e68-146">-MaxDisconnectedSessions</span></span>

<span data-ttu-id="11e68-147">切断状態にあるリモート セッションの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-147">Specifies the maximum number of remote sessions that are in a disconnected state.</span></span> <span data-ttu-id="11e68-148">このクォータは、すべてのリモート ノード (ターゲット コンピューター) に接続されているセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="11e68-148">This quota is applied to sessions connected to all remote nodes (target computers).</span></span> <span data-ttu-id="11e68-149">既定値は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-149">The default value is 1000.</span></span>

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

### <span data-ttu-id="11e68-150">-MaxPersistenceStoreSizeGB</span><span class="sxs-lookup"><span data-stu-id="11e68-150">-MaxPersistenceStoreSizeGB</span></span>

<span data-ttu-id="11e68-151">セッションで実行するワークフローに割り当てる永続化ストアの最大サイズをギガバイト単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-151">Specifies the maximum size, in gigabytes, of the persistence store allocated to workflows that run in the session.</span></span> <span data-ttu-id="11e68-152">このサイズを超えた場合、永続化されたデータをすべて保存するために永続化ストアが拡張されます。ただし、警告が表示され、ワークフローのイベント ログにメッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="11e68-152">When the size is exceeded, the persistence store is expanded to save all persisted data, but a warning is displayed and a message is written to the workflow event log.</span></span> <span data-ttu-id="11e68-153">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-153">The default value is 10.</span></span>

<span data-ttu-id="11e68-154">永続化ストアには、すべてのワークフロー ジョブのデータが格納されています。</span><span class="sxs-lookup"><span data-stu-id="11e68-154">The persistence store contains data for all workflow jobs.</span></span> <span data-ttu-id="11e68-155">データの格納機能により、状態を失うことなくジョブを再開できます。</span><span class="sxs-lookup"><span data-stu-id="11e68-155">The ability to store data allows the jobs to resume without losing state.</span></span>

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

### <span data-ttu-id="11e68-156">-MaxRunningWorkflows</span><span class="sxs-lookup"><span data-stu-id="11e68-156">-MaxRunningWorkflows</span></span>

<span data-ttu-id="11e68-157">セッションで同時に実行できるワークフローの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-157">Specifies that maximum number of workflows that can run in the session concurrently.</span></span>
<span data-ttu-id="11e68-158">既定値は 30 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-158">The default value is 30.</span></span>

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

### <span data-ttu-id="11e68-159">-Maxsessionsperremoを</span><span class="sxs-lookup"><span data-stu-id="11e68-159">-MaxSessionsPerRemoteNode</span></span>

<span data-ttu-id="11e68-160">各リモート ノード (ターゲット コンピューター) に接続できるセッションの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-160">Specifies the maximum number of sessions that can be connected to each remote node (target computer).</span></span> <span data-ttu-id="11e68-161">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-161">The default value is 5.</span></span>

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

### <span data-ttu-id="11e68-162">-MaxSessionsPerWorkflow</span><span class="sxs-lookup"><span data-stu-id="11e68-162">-MaxSessionsPerWorkflow</span></span>

<span data-ttu-id="11e68-163">各ワークフローをサポートするために作成できるセッションの最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-163">Specifies the maximum number of session that can be created to support each workflow.</span></span> <span data-ttu-id="11e68-164">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-164">The default value is 5.</span></span>

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

### <span data-ttu-id="11e68-165">-OutOfProcessActivity</span><span class="sxs-lookup"><span data-stu-id="11e68-165">-OutOfProcessActivity</span></span>

<span data-ttu-id="11e68-166">アウト プロセスで実行する ( **AllowedActivities** パラメーターで指定された) 許可されたアクティビティを指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-166">Determines which allowed activities (specified by the **AllowedActivities** parameter) run out-of-process.</span></span> <span data-ttu-id="11e68-167">既定値は **InlineScript** です。</span><span class="sxs-lookup"><span data-stu-id="11e68-167">The default value is **InlineScript**.</span></span>

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

### <span data-ttu-id="11e68-168">-PersistencePath</span><span class="sxs-lookup"><span data-stu-id="11e68-168">-PersistencePath</span></span>

<span data-ttu-id="11e68-169">ワークフローの状態とデータを格納するディスク上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-169">Specifies the location on disk where workflow state and data are stored.</span></span> <span data-ttu-id="11e68-170">ワークフローの状態とデータを格納することで、ワークフローを中断した後で再開することや、割り込みやネットワークの障害から復旧することができます。</span><span class="sxs-lookup"><span data-stu-id="11e68-170">Storing the workflow state and data allows workflows to be suspended and resumed, and to recover from interruptions and network failures.</span></span>

<span data-ttu-id="11e68-171">既定値は `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS` です。</span><span class="sxs-lookup"><span data-stu-id="11e68-171">The default value is `$env:LocalAppData\Microsoft\Windows\PowerShell\WF\PS`.</span></span>

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

### <span data-ttu-id="11e68-172">-PersistWithEncryption</span><span class="sxs-lookup"><span data-stu-id="11e68-172">-PersistWithEncryption</span></span>

<span data-ttu-id="11e68-173">ワークフローが永続化ストア内のデータを暗号化することを示します。</span><span class="sxs-lookup"><span data-stu-id="11e68-173">Indicates that the workflow encrypts the data in the persistence store.</span></span> <span data-ttu-id="11e68-174">ネットワーク共有に永続データを格納する場合は、この機能の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="11e68-174">Consider using this feature when storing persistence data in a network share.</span></span>

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

### <span data-ttu-id="11e68-175">-RemoteNodeSessionIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="11e68-175">-RemoteNodeSessionIdleTimeoutSec</span></span>

<span data-ttu-id="11e68-176">リモート ノード (ターゲット コンピューター) に接続しているアイドル状態のセッションを維持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-176">Specifies how long a session that is connected to a remote node (target computer) is maintained if it is idle.</span></span>

<span data-ttu-id="11e68-177">値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="11e68-177">Enter a value in seconds.</span></span> <span data-ttu-id="11e68-178">既定値は 60 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-178">The default value is 60.</span></span>

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

### <span data-ttu-id="11e68-179">-SessionThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="11e68-179">-SessionThrottleLimit</span></span>

<span data-ttu-id="11e68-180">セッションで開始されたすべてのワークフローをサポートするために作成する操作の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-180">Specifies how many operations are created to support all workflows started in the session.</span></span> <span data-ttu-id="11e68-181">既定値は 100 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-181">The default value is 100.</span></span>

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

### <span data-ttu-id="11e68-182">-WorkflowShutdownTimeoutMSec 秒</span><span class="sxs-lookup"><span data-stu-id="11e68-182">-WorkflowShutdownTimeoutMSec</span></span>

<span data-ttu-id="11e68-183">セッション内のすべてのワークフローが強制的に中断された後にセッションを維持する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="11e68-183">Specifies how long the session is maintained after all workflows in the session are forcibly suspended.</span></span> <span data-ttu-id="11e68-184">このタイムアウトを過ぎると、すべてのワークフローがまだ中断されていなくでも、セッションが閉じられます。</span><span class="sxs-lookup"><span data-stu-id="11e68-184">When the timeout expires, Windows PowerShell closes the session, even if all workflows are not yet suspended.</span></span>

<span data-ttu-id="11e68-185">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="11e68-185">Enter a value in milliseconds.</span></span>
<span data-ttu-id="11e68-186">既定値は 500 です。</span><span class="sxs-lookup"><span data-stu-id="11e68-186">The default value is 500.</span></span>

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

### <span data-ttu-id="11e68-187">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11e68-187">CommonParameters</span></span>

<span data-ttu-id="11e68-188">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11e68-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11e68-189">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11e68-189">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="11e68-190">入力</span><span class="sxs-lookup"><span data-stu-id="11e68-190">INPUTS</span></span>

### <span data-ttu-id="11e68-191">なし</span><span class="sxs-lookup"><span data-stu-id="11e68-191">None</span></span>

<span data-ttu-id="11e68-192">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="11e68-192">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="11e68-193">出力</span><span class="sxs-lookup"><span data-stu-id="11e68-193">OUTPUTS</span></span>

### <span data-ttu-id="11e68-194">Microsoft. PowerShell. PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="11e68-194">Microsoft.PowerShell.Commands.PSWorkflowExecutionOption</span></span>

## <span data-ttu-id="11e68-195">注</span><span class="sxs-lookup"><span data-stu-id="11e68-195">NOTES</span></span>

<span data-ttu-id="11e68-196">オプションによって設定された最大値を超えると、パラメーターの説明に記載されている場合を除き、セッションに別のインスタンスを作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="11e68-196">When the maximum value set by an option is exceeded, the command to create another instance in the session fails, unless noted in the parameter description.</span></span> <span data-ttu-id="11e68-197">たとえば、 **MaxConnectedSessions** の値が 100 の場合、</span><span class="sxs-lookup"><span data-stu-id="11e68-197">For example, if the value of **MaxConnectedSessions** is 100.</span></span> <span data-ttu-id="11e68-198">リモート ノード (ターゲット コンピューター) に 101 個目のセッションを作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="11e68-198">The command to create the 101st session to a remote node (target computer) fails.</span></span>

<span data-ttu-id="11e68-199">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="11e68-199">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="11e68-200">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="11e68-200">Also, session configurations that use a session configuration file have additional properties.</span></span>

<span data-ttu-id="11e68-201">特に、 **PSWorkflowExecutionOptions** オブジェクトが含まれるセッション構成のプロパティは、ワークフロー オプションの値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="11e68-201">In particular, the properties of session configurations that include a **PSWorkflowExecutionOptions** object vary based on the workflow option values.</span></span> <span data-ttu-id="11e68-202">たとえば、 **SessionThrottleLimit** プロパティに既定以外の値を設定する **PSWorkflowExecutionOptions** オブジェクトがセッション構成に含まれる場合、そのセッション構成には **SessionThrottleLimit** プロパティが存在します。</span><span class="sxs-lookup"><span data-stu-id="11e68-202">For example, if the session configuration includes a **PSWorkflowExecutionOptions** object that sets a non-default value for the **SessionThrottleLimit** property, the session configuration has a **SessionThrottleLimit** property.</span></span> <span data-ttu-id="11e68-203">それ以外の場合、存在しません。</span><span class="sxs-lookup"><span data-stu-id="11e68-203">Otherwise, it does not.</span></span>

## <span data-ttu-id="11e68-204">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11e68-204">RELATED LINKS</span></span>

[<span data-ttu-id="11e68-205">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="11e68-205">New-PSWorkflowSession</span></span>](New-PSWorkflowSession.md)

[<span data-ttu-id="11e68-206">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="11e68-206">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="11e68-207">about_WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="11e68-207">about_WorkflowCommonParameters</span></span>](About/about_WorkflowCommonParameters.md)
