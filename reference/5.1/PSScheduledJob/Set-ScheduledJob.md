---
external help file: Microsoft.PowerShell.ScheduledJob.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSScheduledJob
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psscheduledjob/set-scheduledjob?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ScheduledJob
ms.openlocfilehash: 99dbdc84430c0a8b5cf505a22b139cd07236e160
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213368"
---
# <span data-ttu-id="fe766-103">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-103">Set-ScheduledJob</span></span>

## <span data-ttu-id="fe766-104">概要</span><span class="sxs-lookup"><span data-stu-id="fe766-104">SYNOPSIS</span></span>
<span data-ttu-id="fe766-105">スケジュールされたジョブを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe766-105">Changes scheduled jobs.</span></span>

## <span data-ttu-id="fe766-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe766-106">SYNTAX</span></span>

### <span data-ttu-id="fe766-107">ScriptBlock (既定値)</span><span class="sxs-lookup"><span data-stu-id="fe766-107">ScriptBlock (Default)</span></span>

```
Set-ScheduledJob [-Name <String>] [-ScriptBlock <ScriptBlock>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="fe766-108">FilePath</span><span class="sxs-lookup"><span data-stu-id="fe766-108">FilePath</span></span>

```
Set-ScheduledJob [-Name <String>] [-FilePath <String>] [-Trigger <ScheduledJobTrigger[]>]
 [-InitializationScript <ScriptBlock>] [-RunAs32] [-Credential <PSCredential>]
 [-Authentication <AuthenticationMechanism>] [-ScheduledJobOption <ScheduledJobOptions>]
 [-InputObject] <ScheduledJobDefinition> [-MaxResultCount <Int32>] [-PassThru] [-ArgumentList <Object[]>]
 [-RunNow] [-RunEvery <TimeSpan>] [<CommonParameters>]
```

### <span data-ttu-id="fe766-109">実行</span><span class="sxs-lookup"><span data-stu-id="fe766-109">Execution</span></span>

```
Set-ScheduledJob [-InputObject] <ScheduledJobDefinition> [-ClearExecutionHistory] [-PassThru]
 [<CommonParameters>]
```

## <span data-ttu-id="fe766-110">Description</span><span class="sxs-lookup"><span data-stu-id="fe766-110">DESCRIPTION</span></span>
<span data-ttu-id="fe766-111">**Set-ScheduledJob** コマンドレットは、ジョブで実行するコマンドや、ジョブを実行するために必要な資格情報など、スケジュールされたジョブのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe766-111">The **Set-ScheduledJob** cmdlet changes the properties of scheduled jobs, such as the commands that the jobs run or the credentials required to run the job.</span></span>
<span data-ttu-id="fe766-112">このコマンドレットを使用して、スケジュールされたジョブの実行履歴をクリアすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fe766-112">You can also use it to clear the execution history of the scheduled job.</span></span>

<span data-ttu-id="fe766-113">このコマンドレットを使用するには、まず Get-ScheduledJob コマンドレットを使用して、スケジュールされたジョブを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe766-113">To use this cmdlet, begin by using the Get-ScheduledJob cmdlet to get the scheduled job.</span></span>
<span data-ttu-id="fe766-114">次に、スケジュールされたジョブを **Set ScheduledJob** にパイプするか、変数にジョブを保存し、 *InputObject* パラメーターを使用してジョブを識別します。</span><span class="sxs-lookup"><span data-stu-id="fe766-114">Then, pipe the scheduled job to **Set-ScheduledJob** or save the job in a variable and use the *InputObject* parameter to identify the job.</span></span>
<span data-ttu-id="fe766-115">**Set-ScheduledJob** の他のパラメーターを使用して、ジョブのプロパティを変更したり、実行履歴をクリアしたりします。</span><span class="sxs-lookup"><span data-stu-id="fe766-115">Use the remaining parameters of **Set-ScheduledJob** to change the job properties or clear the execution history.</span></span>

<span data-ttu-id="fe766-116">**Set ScheduledJob** を使用して、スケジュールされたジョブのトリガーとオプションを変更できますが、Jobtrigger、Set jobtrigger、および Set-ScheduledJobOption コマンドレットを使用すると、これらのタスクをより簡単に実行できます。</span><span class="sxs-lookup"><span data-stu-id="fe766-116">Although you can use **Set-ScheduledJob** to change the triggers and options of a scheduled job, the Add-JobTrigger, Set-JobTrigger, and Set-ScheduledJobOption cmdlets provide much easier ways to accomplish those tasks.</span></span>
<span data-ttu-id="fe766-117">スケジュールされた新しいジョブを作成するには、Register-ScheduledJob コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-117">To create a new scheduled job, use the Register-ScheduledJob cmdlet.</span></span>

<span data-ttu-id="fe766-118">**Set ScheduledJob** の *Trigger* パラメーターは、ジョブを開始する1つまたは複数のジョブトリガーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fe766-118">The *Trigger* parameter of **Set-ScheduledJob** adds one or more job triggers that start the job.</span></span>
<span data-ttu-id="fe766-119">*Trigger* パラメーターは省略可能であるため、スケジュールされたジョブを作成するときにトリガーを追加し、後でジョブトリガーを追加します。次に、 *runnow* パラメーターを追加してすぐにジョブを開始し、Start-Job コマンドレットを使用して、スケジュールされていないジョブを他のジョブのテンプレートとして保存します。</span><span class="sxs-lookup"><span data-stu-id="fe766-119">The *Trigger* parameter is optional, so you can add triggers when you create the scheduled job, add job triggers later, add the *RunNow* parameter to start the job immediately, use the Start-Job cmdlet to start the job immediately at any time, or save the untriggered scheduled job as a template for other jobs.</span></span>

<span data-ttu-id="fe766-120">**設定-scheduledjob** は、Windows PowerShell に含まれている psscheduledjob モジュールのジョブスケジュールコマンドレットのコレクションの1つです。</span><span class="sxs-lookup"><span data-stu-id="fe766-120">**Set-ScheduledJob** is one of a collection of job scheduling cmdlets in the PSScheduledJob module that is included in Windows PowerShell.</span></span>

<span data-ttu-id="fe766-121">スケジュールされたジョブの詳細については、PSScheduledJob モジュールの概要トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-121">For more information about Scheduled Jobs, see the About topics in the PSScheduledJob module.</span></span>
<span data-ttu-id="fe766-122">PSScheduledJob モジュールをインポートし、次のように入力し `Get-Help about_Scheduled*` ます。または about_Scheduled_Jobs を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-122">Import the PSScheduledJob module and then type: `Get-Help about_Scheduled*` or see about_Scheduled_Jobs.</span></span>

<span data-ttu-id="fe766-123">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="fe766-123">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="fe766-124">例</span><span class="sxs-lookup"><span data-stu-id="fe766-124">EXAMPLES</span></span>

### <span data-ttu-id="fe766-125">例 1: ジョブを実行するスクリプトを変更する</span><span class="sxs-lookup"><span data-stu-id="fe766-125">Example 1: Change the script that a job runs</span></span>

```
PS C:\> Get-ScheduledJob -Name "Inventory"
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-Inventory.ps1             True

The second command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job. A pipeline operator (|) sends the scheduled job to the **Set-ScheduledJob** cmdlet. The **Set-ScheduledJob** cmdlet uses the *Script* parameter to specify a new script, Get-FullInventory.ps1. The command uses the *Passthru* parameter to return the scheduled job after the change.
PS C:\> Get-ScheduledJob -Name "Inventory" | Set-ScheduledJob -FilePath "C:\Scripts\Get-FullInventory.ps1" -Passthru
Id         Name            Triggers        Command                                  Enabled
--         ----            --------        -------                                  -------
1          Inventory       {1}             C:\Scripts\Get-FullInventory.ps1         True
```

<span data-ttu-id="fe766-126">この例では、スケジュールされたジョブで実行するスクリプトを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fe766-126">This example shows how to change the script that is run in a scheduled job.</span></span>

<span data-ttu-id="fe766-127">最初のコマンドは、Get-ScheduledJob コマンドレットを使用して、スケジュールされたジョブのインベントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe766-127">The first command uses the Get-ScheduledJob cmdlet to get the Inventory scheduled job.</span></span>
<span data-ttu-id="fe766-128">出力には、ジョブで Get-Inventory.ps1 スクリプトが実行されることが示されています。</span><span class="sxs-lookup"><span data-stu-id="fe766-128">The output shows that the job runs the Get-Inventory.ps1 script.</span></span>

<span data-ttu-id="fe766-129">このコマンドは必須ではありません。スクリプトの変更の結果を表示するためにのみ含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe766-129">This command is not required; it is included only to show the effect of the script change.</span></span>

### <span data-ttu-id="fe766-130">例 2: スケジュールされたジョブの実行履歴を削除する</span><span class="sxs-lookup"><span data-stu-id="fe766-130">Example 2: Delete the execution history of a scheduled job</span></span>

```
PS C:\> Get-ScheduledJob BackupArchive | Set-ScheduledJob -ClearExecutionHistory
```

<span data-ttu-id="fe766-131">このコマンドは、スケジュールされたジョブ BackupArchive の現在の実行履歴と保存されているジョブの結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe766-131">This command deletes the current execution history and saved job results for the BackupArchive scheduled job.</span></span>

<span data-ttu-id="fe766-132">このコマンドは、Get-ScheduledJob コマンドレットを使用して、スケジュールされたジョブスケジュール backuparchive を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe766-132">The command uses the Get-ScheduledJob cmdlet to get the BackupArchive scheduled job.</span></span>
<span data-ttu-id="fe766-133">パイプライン演算子 (|) により、ジョブを **Set-ScheduledJob** コマンドレットに渡して、ジョブを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe766-133">A pipeline operator (|) sends the job to the **Set-ScheduledJob** cmdlet to change it.</span></span>
<span data-ttu-id="fe766-134">**Set ScheduledJob** コマンドレットは、 *ClearExecutionHistory* パラメーターを使用して、実行履歴と保存された結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe766-134">The **Set-ScheduledJob** cmdlet uses the *ClearExecutionHistory* parameter to delete the execution history and saved results.</span></span>

<span data-ttu-id="fe766-135">スケジュールされたジョブの実行履歴と保存されているジョブの結果の詳細については、「about_Scheduled_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-135">For more information about the execution history and saved job results of scheduled jobs, see about_Scheduled_Jobs.</span></span>

### <span data-ttu-id="fe766-136">例 3: リモートコンピューター上のスケジュールされたジョブを変更する</span><span class="sxs-lookup"><span data-stu-id="fe766-136">Example 3: Change scheduled jobs on a remote computer</span></span>

```
PS C:\> Invoke-Command -Computer "Server01, Server02" -ScriptBlock {Get-ScheduledJob | Set-ScheduledJob -InitializationScript \\SrvA\Scripts\SetForRun.ps1}
```

<span data-ttu-id="fe766-137">このコマンドは、Server01 コンピューターと Server02 コンピューター上のスケジュールされたすべてのジョブの初期化スクリプトを変更します。</span><span class="sxs-lookup"><span data-stu-id="fe766-137">This command changes the initialization script in all scheduled jobs on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="fe766-138">このコマンドは、Invoke-Command コマンドレットを使用して、Server01 コンピューターと Server02 コンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe766-138">The command uses the Invoke-Command cmdlet to run a command on the Server01 and Server02 computers.</span></span>

<span data-ttu-id="fe766-139">リモートコマンドは、コンピューター上のスケジュールされたすべてのジョブを取得する Get-ScheduledJob コマンドで開始します。</span><span class="sxs-lookup"><span data-stu-id="fe766-139">The remote command begins with a Get-ScheduledJob command that gets all scheduled jobs on the computer.</span></span>
<span data-ttu-id="fe766-140">スケジュールされたジョブは、 **Set scheduledjob** コマンドレットにパイプされます。このコマンドレットは、初期化スクリプトを SetForRun.ps1 に変更します。</span><span class="sxs-lookup"><span data-stu-id="fe766-140">The scheduled jobs are piped to the **Set-ScheduledJob** cmdlet, which changes the initialization script to SetForRun.ps1.</span></span>

## <span data-ttu-id="fe766-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe766-141">PARAMETERS</span></span>

### <span data-ttu-id="fe766-142">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="fe766-142">-ArgumentList</span></span>
<span data-ttu-id="fe766-143">*FilePath* パラメーターで指定されたスクリプトのパラメーター、または *ScriptBlock* パラメーターで指定されたコマンドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-143">Specifies values for the parameters of the script that is specified by the *FilePath* parameter or for the command that is specified by the *ScriptBlock* parameter.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-144">-認証</span><span class="sxs-lookup"><span data-stu-id="fe766-144">-Authentication</span></span>
<span data-ttu-id="fe766-145">ユーザーの資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-145">Specifies the mechanism that is used to authenticate the user's credentials.</span></span>
<span data-ttu-id="fe766-146">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fe766-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="fe766-147">Default</span><span class="sxs-lookup"><span data-stu-id="fe766-147">Default</span></span>
- <span data-ttu-id="fe766-148">Basic</span><span class="sxs-lookup"><span data-stu-id="fe766-148">Basic</span></span>
- <span data-ttu-id="fe766-149">Credssp</span><span class="sxs-lookup"><span data-stu-id="fe766-149">Credssp</span></span>
- <span data-ttu-id="fe766-150">ダイジェスト</span><span class="sxs-lookup"><span data-stu-id="fe766-150">Digest</span></span>
- <span data-ttu-id="fe766-151">Kerberos</span><span class="sxs-lookup"><span data-stu-id="fe766-151">Kerberos</span></span>
- <span data-ttu-id="fe766-152">ネゴシエート</span><span class="sxs-lookup"><span data-stu-id="fe766-152">Negotiate</span></span>
- <span data-ttu-id="fe766-153">NegotiateWithImplicitCredential</span><span class="sxs-lookup"><span data-stu-id="fe766-153">NegotiateWithImplicitCredential</span></span>

<span data-ttu-id="fe766-154">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="fe766-154">The default value is Default.</span></span>
<span data-ttu-id="fe766-155">このパラメーターの値の詳細については、MSDN ライブラリの「 [Authenticationmechanism 列挙型](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-155">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](https://msdn.microsoft.com/library/system.management.automation.runspaces.authenticationmechanism) in the MSDN library.</span></span>

<span data-ttu-id="fe766-156">注意: ユーザーの資格情報が認証対象のリモートコンピューターに渡される Credential Security Support Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="fe766-156">Caution: Credential Security Support Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
<span data-ttu-id="fe766-157">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="fe766-157">This mechanism increases the security risk of the remote operation.</span></span>
<span data-ttu-id="fe766-158">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe766-158">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: ScriptBlock, FilePath
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-159">-ClearExecutionHistory</span><span class="sxs-lookup"><span data-stu-id="fe766-159">-ClearExecutionHistory</span></span>
<span data-ttu-id="fe766-160">スケジュールされたジョブの現在の実行履歴と保存されている結果を削除します。</span><span class="sxs-lookup"><span data-stu-id="fe766-160">Deletes the current execution history and the saved results of the scheduled job.</span></span>

<span data-ttu-id="fe766-161">ジョブの実行履歴とジョブの結果は、スケジュールされたジョブと共に、ジョブが作成されたコンピューターの $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs ディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="fe766-161">The job execution history and job results are saved with the scheduled job in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs directory on the computer on which the job is created.</span></span>
<span data-ttu-id="fe766-162">実行履歴を表示するには、Get-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-162">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="fe766-163">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-163">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="fe766-164">このパラメーターによって、タスク スケジューラから Windows イベント ログに書き込まれたイベントが影響を受けることはありません。また、Windows PowerShell がジョブの結果の保存を停止することもありません。</span><span class="sxs-lookup"><span data-stu-id="fe766-164">This parameter does not affect the events that Task Scheduler writes to the Windows event logs and it does not stop Windows PowerShell from saving job results.</span></span>
<span data-ttu-id="fe766-165">保存されるジョブの結果の数を管理するには、 *MaxResultCount* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-165">To manage the number of job results that are saved, use the *MaxResultCount* parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Execution
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-166">-Credential</span><span class="sxs-lookup"><span data-stu-id="fe766-166">-Credential</span></span>
<span data-ttu-id="fe766-167">スケジュールされたジョブを実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-167">Specifies a user account that has permission to run the scheduled job.</span></span>
<span data-ttu-id="fe766-168">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="fe766-168">The default is the current user.</span></span>

<span data-ttu-id="fe766-169">User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットのような **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe766-169">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one from the Get-Credential cmdlet.</span></span>
<span data-ttu-id="fe766-170">ユーザー名のみを入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe766-170">If you enter only a user name, you will be prompted for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-171">-FilePath</span><span class="sxs-lookup"><span data-stu-id="fe766-171">-FilePath</span></span>
<span data-ttu-id="fe766-172">スケジュールされたジョブで実行するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-172">Specifies a script that the scheduled job runs.</span></span>
<span data-ttu-id="fe766-173">ローカル コンピューター上の .ps1 ファイルのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe766-173">Enter the path to a .ps1 file on the local computer.</span></span>
<span data-ttu-id="fe766-174">スクリプト パラメーターの既定値を指定するには、 *ArgumentList* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-174">To specify default values for the script parameters, use the *ArgumentList* parameter.</span></span>
<span data-ttu-id="fe766-175">スケジュールされたすべてのジョブには、 *ScriptBlock* 値または *FilePath* 値が必ず設定されています。</span><span class="sxs-lookup"><span data-stu-id="fe766-175">Every scheduled job must have either a *ScriptBlock* or *FilePath* value.</span></span>

```yaml
Type: System.String
Parameter Sets: FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-176">-InitializationScript</span><span class="sxs-lookup"><span data-stu-id="fe766-176">-InitializationScript</span></span>
<span data-ttu-id="fe766-177">Windows PowerShell スクリプト (.ps1) の完全修飾パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-177">Specifies the fully qualified path to a Windows PowerShell script (.ps1).</span></span>
<span data-ttu-id="fe766-178">初期化スクリプトは、 *ScriptBlock* パラメーターで指定されたコマンドまたは *FilePath* パラメーターで指定されスクリプトの前に、バックグラウンド ジョブ用に作成されたセッションで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fe766-178">The initialization script runs in the session that is created for the background job before the commands that are specified by the *ScriptBlock* parameter or the script that is specified by the *FilePath* parameter.</span></span>
<span data-ttu-id="fe766-179">初期化スクリプトを使用すると、ファイル、関数、またはエイリアスの追加、ディレクトリの作成、前提条件の確認など、セッションを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="fe766-179">You can use the initialization script to configure the session, such as adding files, functions, or aliases, creating directories, or checking for prerequisites.</span></span>

<span data-ttu-id="fe766-180">プライマリ ジョブ コマンドを実行するスクリプトを指定するには、 *FilePath* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-180">To specify a script that runs the primary job commands, use the *FilePath* parameter.</span></span>

<span data-ttu-id="fe766-181">終了しないエラーなど、初期化スクリプトがエラーを生成した場合、スケジュールされたジョブの現在のインスタンスは実行されず、状態は Failed になります。</span><span class="sxs-lookup"><span data-stu-id="fe766-181">If the initialization script generates an error, including a non-terminating error, the current instance of the scheduled job does not run and its status is Failed.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-182">-InputObject</span><span class="sxs-lookup"><span data-stu-id="fe766-182">-InputObject</span></span>
<span data-ttu-id="fe766-183">変更するスケジュールされたジョブを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-183">Specifies the scheduled job to be changed.</span></span>
<span data-ttu-id="fe766-184">**ScheduledJobDefinition** オブジェクトを含む変数を入力するか、Get-ScheduledJob コマンドなどの **ScheduledJobDefinition** オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe766-184">Enter a variable that contains **ScheduledJobDefinition** objects or type a command or expression that gets **ScheduledJobDefinition** objects, such as a Get-ScheduledJob command.</span></span>
<span data-ttu-id="fe766-185">パイプを使用して **ScheduledJobDefinition** オブジェクトを **設定** することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe766-185">You can also pipe a **ScheduledJobDefinition** object to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="fe766-186">複数のスケジュールされたジョブを指定すると、 **Set-ScheduledJob** はすべてのジョブに同じ変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="fe766-186">If you specify multiple scheduled jobs, **Set-ScheduledJob** makes the same changes to all jobs.</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-187">-MaxResultCount</span><span class="sxs-lookup"><span data-stu-id="fe766-187">-MaxResultCount</span></span>
<span data-ttu-id="fe766-188">スケジュールされたジョブに対して保持されるジョブの結果のエントリ数を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-188">Specifies how many job result entries are maintained for the scheduled job.</span></span>
<span data-ttu-id="fe766-189">既定値は 32 です。</span><span class="sxs-lookup"><span data-stu-id="fe766-189">The default value is 32.</span></span>

<span data-ttu-id="fe766-190">Windows PowerShell では、スケジュールされたジョブのトリガーされた各インスタンスの実行履歴と結果をディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="fe766-190">Windows PowerShell saves the execution history and results of each triggered instance of the scheduled job on disk.</span></span>
<span data-ttu-id="fe766-191">このパラメーターの値により、このスケジュールされたジョブに対して保存されるジョブ インスタンスの結果の数が決まります。</span><span class="sxs-lookup"><span data-stu-id="fe766-191">The value of this parameter determines the number of job instance results that are saved for this scheduled job.</span></span>
<span data-ttu-id="fe766-192">ジョブ インスタンスの結果の数がこの値を超えた場合は、最新のジョブ インスタンスの結果を保存するために、最も古いジョブ インスタンスの結果が削除されます。</span><span class="sxs-lookup"><span data-stu-id="fe766-192">When the number of job instance results exceeds this value, Windows PowerShell deletes the results of the oldest job instance to make room for the results of the newest job instance.</span></span>

<span data-ttu-id="fe766-193">ジョブの実行履歴とジョブの結果は、 \\ \<JobName\> \\ ジョブが作成されたコンピューターの $home \appdata\local\microsoft\windows\powershell\scheduledjobs \ 出力ディレクトリに保存され \<Timestamp\> ます。</span><span class="sxs-lookup"><span data-stu-id="fe766-193">The job execution history and job results are saved in the $home\AppData\Local\Microsoft\Windows\PowerShell\ScheduledJobs\\\<JobName\>\Output\\\<Timestamp\> directories on the computer on which the job is created.</span></span>
<span data-ttu-id="fe766-194">実行履歴を表示するには、Get-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-194">To see the execution history, use the Get-Job cmdlet.</span></span>
<span data-ttu-id="fe766-195">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-195">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="fe766-196">*MaxResultCount* パラメーターは、スケジュールされたジョブの ExecutionHistoryLength プロパティの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-196">The *MaxResultCount* parameter sets the value of the ExecutionHistoryLength property of the scheduled job.</span></span>

<span data-ttu-id="fe766-197">現在の実行履歴とジョブの結果を削除するには、 *ClearExecutionHistory* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-197">To delete the current execution history and job results, use the *ClearExecutionHistory* parameter.</span></span>

```yaml
Type: System.Int32
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-198">-Name</span><span class="sxs-lookup"><span data-stu-id="fe766-198">-Name</span></span>
<span data-ttu-id="fe766-199">スケジュールされたジョブの新しい名前とスケジュールされたジョブのインスタンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-199">Specifies a new name for the scheduled job and instances of the scheduled job.</span></span>
<span data-ttu-id="fe766-200">名前は、ローカル コンピューター上で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe766-200">The name must be unique on the local computer.</span></span>

<span data-ttu-id="fe766-201">変更するスケジュールされたジョブを特定するには、 *InputObject* パラメーターを使用するか、スケジュールされたジョブを Get-ScheduledJob からスケジュールされたジョブにパイプを使用して **設定** します。</span><span class="sxs-lookup"><span data-stu-id="fe766-201">To identify the scheduled job to be changed, use the *InputObject* parameter or pipe a scheduled job from Get-ScheduledJob to **Set-ScheduledJob** .</span></span>

<span data-ttu-id="fe766-202">このパラメーターによって、ディスク上のジョブ インスタンスの名前が変更されることはありません。</span><span class="sxs-lookup"><span data-stu-id="fe766-202">This parameter does not change the names of job instances on disk.</span></span>
<span data-ttu-id="fe766-203">このコマンドが完了した後に開始されるジョブ インスタンスのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="fe766-203">It affects only job instances that are started after this command completes.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-204">-PassThru</span><span class="sxs-lookup"><span data-stu-id="fe766-204">-PassThru</span></span>
<span data-ttu-id="fe766-205">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fe766-205">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="fe766-206">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fe766-206">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="fe766-207">-RunAs32</span><span class="sxs-lookup"><span data-stu-id="fe766-207">-RunAs32</span></span>
<span data-ttu-id="fe766-208">スケジュールされたジョブを 32 ビット プロセスで実行します。</span><span class="sxs-lookup"><span data-stu-id="fe766-208">Runs the scheduled job in a 32-bit process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-209">-RunEvery</span><span class="sxs-lookup"><span data-stu-id="fe766-209">-RunEvery</span></span>

<span data-ttu-id="fe766-210">ジョブを実行する頻度を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-210">Used to specify how often to run the job.</span></span> <span data-ttu-id="fe766-211">たとえば、15分ごとにジョブを実行するには、このオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-211">For example, use this option to run a job every 15 minutes.</span></span>

```yaml
Type: System.TimeSpan
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-212">-RunNow</span><span class="sxs-lookup"><span data-stu-id="fe766-212">-RunNow</span></span>
<span data-ttu-id="fe766-213">**Set scheduledjob** コマンドレットが実行されるとすぐに、ジョブを直ちに開始します。</span><span class="sxs-lookup"><span data-stu-id="fe766-213">Starts a job immediately, as soon as the **Set-ScheduledJob** cmdlet is run.</span></span>
<span data-ttu-id="fe766-214">このパラメーターを使用すると、登録後すぐにタスク スケジューラをトリガーして Windows PowerShell スクリプトを実行する必要がなくなります。また、ユーザーが開始日時を指定したトリガーを作成する必要もありません。</span><span class="sxs-lookup"><span data-stu-id="fe766-214">This parameter eliminates the need to trigger Task Scheduler to run a Windows PowerShell script immediately after registration, and does not require users to create a trigger that specifies a starting date and time.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-215">-Get-scheduledjoboption</span><span class="sxs-lookup"><span data-stu-id="fe766-215">-ScheduledJobOption</span></span>
<span data-ttu-id="fe766-216">スケジュールされたジョブのオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-216">Sets options for the scheduled job.</span></span>
<span data-ttu-id="fe766-217">New-ScheduledJobOption コマンドレットを使用して作成したオブジェクトやハッシュテーブルの値など、 **ScheduledJobOptions** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe766-217">Enter a **ScheduledJobOptions** object, such as one that you create by using the New-ScheduledJobOption cmdlet, or a hash table value.</span></span>

<span data-ttu-id="fe766-218">スケジュールされたジョブを登録するときにスケジュールされたジョブのオプションを設定することも、Set-ScheduledJobOption または **Set ScheduledJob** コマンドレットを使用してオプションを設定または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe766-218">You can set options for a scheduled job when you register the scheduled job or use the Set-ScheduledJobOption or **Set-ScheduledJob** cmdlets to set or change options.</span></span>

<span data-ttu-id="fe766-219">さまざまなオプションとその既定値により、スケジュールされたジョブが実行されるかどうかとそのタイミングが決まります。</span><span class="sxs-lookup"><span data-stu-id="fe766-219">Many of the options and their default values determine whether and when a scheduled job runs.</span></span>
<span data-ttu-id="fe766-220">ジョブをスケジュールする前に、必ずこれらのオプションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-220">Be sure to review these options before scheduling a job.</span></span>
<span data-ttu-id="fe766-221">スケジュールされたジョブオプションの説明 (既定値を含む) については、「Get-scheduledjoboption」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-221">For a description of the scheduled job options, including the default values, see New-ScheduledJobOption.</span></span>

<span data-ttu-id="fe766-222">ハッシュ テーブルを渡すには、次のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-222">To submit a hash table, use the following keys.</span></span>
<span data-ttu-id="fe766-223">次のハッシュ テーブルには、キーとその既定値が示されています。</span><span class="sxs-lookup"><span data-stu-id="fe766-223">In the following hash table, the keys are shown with their default values.</span></span>

`@{# Power SettingsStartIfOnBattery=$False;StopIfGoingOnBattery=$True; WakeToRun=$False; # Idle SettingsStartIfNotIdle=$False; IdleDuration="00:10:00"; IdleTimeout="01:00:00"; StopIfGoingOffIdle=$True; RestartOnIdleResume=$False;# Security settingsShowInTaskScheduler=$TrueRunElevated=$False;# MiscRunWithoutNetwork=$False;DoNotAllowDemandStart=$False;MultipleInstancePolicy=IgnoreNew# Can be IgnoreNew, Parallel, Queue, StopExisting}`

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobOptions
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-224">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="fe766-224">-ScriptBlock</span></span>
<span data-ttu-id="fe766-225">スケジュールされたジョブで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-225">Specifies the commands that the scheduled job runs.</span></span>
<span data-ttu-id="fe766-226">コマンドを中かっこ ({ }) で囲み、スクリプト ブロックを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe766-226">Enclose the commands in braces ( { } ) to create a script block.</span></span>
<span data-ttu-id="fe766-227">コマンド パラメーターの既定値を指定するには、 *ArgumentList* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-227">To specify default values for command parameters, use the *ArgumentList* parameter.</span></span>

<span data-ttu-id="fe766-228">すべての Register-ScheduledJob コマンドで、 *ScriptBlock* パラメーターと *FilePath* パラメーターのどちらかを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe766-228">Every Register-ScheduledJob command must use either the *ScriptBlock* or *FilePath* parameters.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-229">-トリガー</span><span class="sxs-lookup"><span data-stu-id="fe766-229">-Trigger</span></span>
<span data-ttu-id="fe766-230">スケジュールされたジョブのトリガーを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe766-230">Specifies the triggers for the scheduled job.</span></span>
<span data-ttu-id="fe766-231">New-JobTrigger コマンドレットが返すオブジェクトや、ジョブトリガーのキーと値のハッシュテーブルなど、1つまたは複数の **Scheduledjobtrigger** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="fe766-231">Enter one or more **ScheduledJobTrigger** objects, such as the objects that the New-JobTrigger cmdlet returns, or a hash table of job trigger keys and values.</span></span>

<span data-ttu-id="fe766-232">ジョブトリガーは、スケジュールされたジョブを1回だけ、または定期的に、またはイベントが発生したときに自動的に開始します。</span><span class="sxs-lookup"><span data-stu-id="fe766-232">A job trigger starts a scheduled job automatically on a one-time or recurring scheduled or when an event occurs.</span></span>

<span data-ttu-id="fe766-233">ジョブ トリガーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fe766-233">Job triggers are optional.</span></span>
<span data-ttu-id="fe766-234">スケジュールされたジョブを作成するときにトリガーを追加したり、Add-JobTrigger または **Set ScheduledJob** コマンドレットを使用してトリガーを後で追加したり、Start-Job コマンドレットを使用してスケジュールされたジョブをすぐに開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe766-234">You can add a trigger when you create the scheduled job, use the Add-JobTrigger or **Set-ScheduledJob** cmdlets to add triggers later, or use the Start-Job cmdlet to start the scheduled job immediately.</span></span>
<span data-ttu-id="fe766-235">また、ジョブ トリガーのないスケジュールされたジョブを作成し、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe766-235">You can also create and maintain a scheduled job that has no job triggers.</span></span>

<span data-ttu-id="fe766-236">ハッシュ テーブルを渡すには、次のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe766-236">To submit a hash table, use the following keys.</span></span>

<span data-ttu-id="fe766-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (または任意の有効な時刻文字列)。 `DaysOfWeek="Monday", "Wednesday"` (または曜日名の任意の組み合わせ)。 `Interval=2` (または任意の有効な頻度の間隔)。 `RandomDelay="30minutes"` (または任意の有効な timespan 文字列)。 `User="Domain1\User01"` (または任意の有効なユーザー。 AtLogon frequency 値と共にのみ使用されます)</span><span class="sxs-lookup"><span data-stu-id="fe766-237">`@{Frequency="Once" (or Daily, Weekly, AtStartup, AtLogon);At="3am"` (or any valid time string); `DaysOfWeek="Monday", "Wednesday"` (or any combination of day names); `Interval=2` (or any valid frequency interval); `RandomDelay="30minutes"` (or any valid timespan string); `User="Domain1\User01"` (or any valid user; used only with the AtLogon frequency value)</span></span>

<span data-ttu-id="fe766-238">}</span><span class="sxs-lookup"><span data-stu-id="fe766-238">}</span></span>

```yaml
Type: Microsoft.PowerShell.ScheduledJob.ScheduledJobTrigger[]
Parameter Sets: ScriptBlock, FilePath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="fe766-239">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe766-239">CommonParameters</span></span>
<span data-ttu-id="fe766-240">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fe766-240">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe766-241">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe766-241">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe766-242">入力</span><span class="sxs-lookup"><span data-stu-id="fe766-242">INPUTS</span></span>

### <span data-ttu-id="fe766-243">ScheduledJobDefinition (Microsoft PowerShell)</span><span class="sxs-lookup"><span data-stu-id="fe766-243">Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fe766-244">パイプを使用して、スケジュールされたジョブを **Set-ScheduledJob** に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="fe766-244">You can pipe scheduled jobs to **Set-ScheduledJob** .</span></span>

## <span data-ttu-id="fe766-245">出力</span><span class="sxs-lookup"><span data-stu-id="fe766-245">OUTPUTS</span></span>

### <span data-ttu-id="fe766-246">[なし] または [ScheduledJobDefinition]</span><span class="sxs-lookup"><span data-stu-id="fe766-246">None or Microsoft.PowerShell.ScheduledJob.ScheduledJobDefinition</span></span>
<span data-ttu-id="fe766-247">*Passthru* パラメーターを使用すると、 **Set-ScheduledJob** は変更されたスケジュールされたジョブを返します。</span><span class="sxs-lookup"><span data-stu-id="fe766-247">If you use the *Passthru* parameter, **Set-ScheduledJob** returns the scheduled job that was changed.</span></span>
<span data-ttu-id="fe766-248">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="fe766-248">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="fe766-249">注</span><span class="sxs-lookup"><span data-stu-id="fe766-249">NOTES</span></span>

## <span data-ttu-id="fe766-250">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fe766-250">RELATED LINKS</span></span>

[<span data-ttu-id="fe766-251">Add-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-251">Add-JobTrigger</span></span>](Add-JobTrigger.md)

[<span data-ttu-id="fe766-252">Disable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-252">Disable-JobTrigger</span></span>](Disable-JobTrigger.md)

[<span data-ttu-id="fe766-253">Disable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-253">Disable-ScheduledJob</span></span>](Disable-ScheduledJob.md)

[<span data-ttu-id="fe766-254">Enable-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-254">Enable-JobTrigger</span></span>](Enable-JobTrigger.md)

[<span data-ttu-id="fe766-255">Enable-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-255">Enable-ScheduledJob</span></span>](Enable-ScheduledJob.md)

[<span data-ttu-id="fe766-256">Get-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-256">Get-JobTrigger</span></span>](Get-JobTrigger.md)

[<span data-ttu-id="fe766-257">Get-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-257">Get-ScheduledJob</span></span>](Get-ScheduledJob.md)

[<span data-ttu-id="fe766-258">Get-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fe766-258">Get-ScheduledJobOption</span></span>](Get-ScheduledJobOption.md)

[<span data-ttu-id="fe766-259">New-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-259">New-JobTrigger</span></span>](New-JobTrigger.md)

[<span data-ttu-id="fe766-260">New-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fe766-260">New-ScheduledJobOption</span></span>](New-ScheduledJobOption.md)

[<span data-ttu-id="fe766-261">Register-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-261">Register-ScheduledJob</span></span>](Register-ScheduledJob.md)

[<span data-ttu-id="fe766-262">Remove-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-262">Remove-JobTrigger</span></span>](Remove-JobTrigger.md)

[<span data-ttu-id="fe766-263">Set-JobTrigger</span><span class="sxs-lookup"><span data-stu-id="fe766-263">Set-JobTrigger</span></span>](Set-JobTrigger.md)

[<span data-ttu-id="fe766-264">Set-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-264">Set-ScheduledJob</span></span>](Set-ScheduledJob.md)

[<span data-ttu-id="fe766-265">Set-ScheduledJobOption</span><span class="sxs-lookup"><span data-stu-id="fe766-265">Set-ScheduledJobOption</span></span>](Set-ScheduledJobOption.md)

[<span data-ttu-id="fe766-266">Unregister-ScheduledJob</span><span class="sxs-lookup"><span data-stu-id="fe766-266">Unregister-ScheduledJob</span></span>](Unregister-ScheduledJob.md)
