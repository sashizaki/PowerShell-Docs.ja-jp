---
external help file: Microsoft.PowerShell.Workflow.ServiceCore.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSWorkflowUtility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflowutility/invoke-asworkflow?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-AsWorkflow
ms.openlocfilehash: b96bce9fe4d574fe2b7e9c7c0f1e05ee0508adce
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213355"
---
# <span data-ttu-id="c5dae-103">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="c5dae-103">Invoke-AsWorkflow</span></span>

## <span data-ttu-id="c5dae-104">概要</span><span class="sxs-lookup"><span data-stu-id="c5dae-104">SYNOPSIS</span></span>
<span data-ttu-id="c5dae-105">コマンドまたは式を Windows PowerShell ワークフローとして実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-105">Runs a command or expression as a Windows PowerShell Workflow.</span></span>

## <span data-ttu-id="c5dae-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c5dae-106">SYNTAX</span></span>

### <span data-ttu-id="c5dae-107">Command (既定値)</span><span class="sxs-lookup"><span data-stu-id="c5dae-107">Command (Default)</span></span>

```
Invoke-AsWorkflow [-CommandName <String>] [-Parameter <Hashtable>] [-InputObject <Object>] [<CommonParameters>]
```

### <span data-ttu-id="c5dae-108">Expression</span><span class="sxs-lookup"><span data-stu-id="c5dae-108">Expression</span></span>

```
Invoke-AsWorkflow [-Expression <String>] [-InputObject <Object>] [<CommonParameters>]
```

## <span data-ttu-id="c5dae-109">Description</span><span class="sxs-lookup"><span data-stu-id="c5dae-109">DESCRIPTION</span></span>

<span data-ttu-id="c5dae-110">ワークフローは、 `Invoke-AsWorkflow` ワークフロー内のインラインスクリプトとして任意のコマンドまたは式を実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-110">The `Invoke-AsWorkflow` workflow runs any command or expression as an inline script in a workflow.</span></span>
<span data-ttu-id="c5dae-111">これらのワークフローは、標準のワークフロー セマンティクスを使用し、すべてのワークフロー共通パラメーターを持ち、ワークフローのすべての利点 (停止、再開、復旧する機能など) を備えています。</span><span class="sxs-lookup"><span data-stu-id="c5dae-111">These workflows use the standard workflow semantics, have all workflow common parameters, and have all benefits of workflows, including the ability to stop, resume, and recover.</span></span>

<span data-ttu-id="c5dae-112">ワークフローは、重要なデータを収集する実行時間の長いコマンドを対象にしていますが、任意のコマンドの実行に使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-112">Workflows are designed for long-running commands that collect critical data, but can be used to run any command.</span></span>
<span data-ttu-id="c5dae-113">詳細については、「 [about_Workflows](../PSWorkflow/About/about_Workflows.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dae-113">For more information, see [about_Workflows](../PSWorkflow/About/about_Workflows.md).</span></span>

<span data-ttu-id="c5dae-114">このコマンドにワークフロー共通パラメーターを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-114">You can also add workflow common parameters to this command.</span></span>
<span data-ttu-id="c5dae-115">ワークフロー共通パラメーターの詳細については、「」を参照してください [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="c5dae-115">For more information about workflow common parameters, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)</span></span>

<span data-ttu-id="c5dae-116">このワークフローは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c5dae-116">This workflow is introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c5dae-117">例</span><span class="sxs-lookup"><span data-stu-id="c5dae-117">EXAMPLES</span></span>

### <span data-ttu-id="c5dae-118">例 1: コマンドレットをワークフローとして実行する</span><span class="sxs-lookup"><span data-stu-id="c5dae-118">Example 1: Run a cmdlet as a workflow</span></span>

```powershell
Invoke-AsWorkflow -PSComputerName (Get-Content Servers.txt) -CommandName Get-ExecutionPolicy
```

```output
PSComputerName                     PSSourceJobInstanceId                   Value
--------------                     ---------------------                   -----
Server01                           77b1cdf8-8226-4662-9067-cd2fa5c3b711    AllSigned
Server02                           a33542d7-3cdd-4339-ab99-0e7cd8e59462    Unrestricted
Server03                           279bac28-066a-4646-9497-8fcdcfe9757e    AllSigned
localhost                          0d858009-2cc4-47a4-a2e0-da17dc2883d0    RemoteSigned
```

<span data-ttu-id="c5dae-119">このコマンドは、数 `Get-ExecutionPolicy` 百のコンピューターでワークフローとしてコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-119">This command runs the `Get-ExecutionPolicy` cmdlet as a workflow on hundreds of computers.</span></span>

<span data-ttu-id="c5dae-120">このコマンドでは、 **CommandName** パラメーターを使用して、ワークフローで実行するコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-120">The command uses the **CommandName** parameter to specify the cmdlet that runs in the workflow.</span></span>
<span data-ttu-id="c5dae-121">**PSComputerName** ワークフロー共通パラメーターを使用して、コマンドを実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-121">It uses the **PSComputerName** workflow common parameter to specify the computers on which the command runs.</span></span>
<span data-ttu-id="c5dae-122">**PSComputerName** パラメーターの値は、 `Get-Content` Servers.txt ファイルからコンピューター名の一覧を取得するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="c5dae-122">The value of the **PSComputerName** parameter is a `Get-Content` command that gets a list of computer names from the Servers.txt file.</span></span>
<span data-ttu-id="c5dae-123">パラメーター値は、値を使用する前にコマンドを実行するように Windows PowerShell に指示するために、かっこで囲まれてい `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-123">The parameter value is enclosed in parentheses to direct Windows PowerShell to run the `Get-Command` command before using the value.</span></span>

<span data-ttu-id="c5dae-124">すべてのリモート コマンドと同様に、コマンドをローカル コンピューターで実行する場合 (PSComputerName パラメーターの値にローカル コンピューターが含まれている場合)、[管理者として実行] オプションで Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c5dae-124">As with all remote commands, if the command runs on the local computer, (if the value of the PSComputerName parameter includes the local computer), you must start Windows PowerShell with the "Run as administrator" option.</span></span>

### <span data-ttu-id="c5dae-125">例 2: パラメーターを使用してコマンドレットを実行する</span><span class="sxs-lookup"><span data-stu-id="c5dae-125">Example 2: Run a cmdlet with parameters</span></span>

```powershell
$s = Import-Csv .\Servers.csv -Header ServerName, ServerID
Invoke-AsWorkflow -CommandName Get-ExecutionPolicy -Parameter @{Scope="Process"} -PSComputerName {$s.ServerName} -PSConnectionRetryCount 5
```

<span data-ttu-id="c5dae-126">最初のコマンドは、 `Import-Csv` コマンドレットを使用して、Servers.csv ファイルのコンテンツからオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-126">The first command uses the `Import-Csv` cmdlet to create an object from the content in the Servers.csv file.</span></span> <span data-ttu-id="c5dae-127">このコマンドは、パラメーターを使用して、 `Header` `ServerName` "リモートノード" とも呼ばれる、ターゲットコンピューターの名前を含む列のプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-127">The command uses the `Header` parameter to create a `ServerName` property for the column that contains the names of the target computers, also known as "remote nodes."</span></span> <span data-ttu-id="c5dae-128">このコマンドは、変数に結果を保存し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-128">The command saves the result in the `$s` variable.</span></span>

<span data-ttu-id="c5dae-129">2番目のコマンドは、ワークフローを使用して、 `Invoke-AsWorkflow` `Get-ExecutionPolicy` Servers.csv ファイル内のコンピューターでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-129">The second command uses the `Invoke-AsWorkflow` workflow to run a `Get-ExecutionPolicy` command on the computers in the Servers.csv file.</span></span> <span data-ttu-id="c5dae-130">このコマンドは、の **CommandName** パラメーターを使用して、 `Invoke-AsWorkflow`  ワークフローで実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-130">The command uses the **CommandName** parameter of `Invoke-AsWorkflow`  to specify the command to run in the workflow.</span></span> <span data-ttu-id="c5dae-131">この例では、のパラメーターを使用して、 `Parameter` `Invoke-AsWorkflow` Process という値を指定して `Scope` コマンドレットのパラメーターを指定して `Get-ExecutionPolicy` います。 **Process** また、このコマンドは、workflow common パラメーターを使用して、 `PSConnectionRetryCount` 各コンピューターでのコマンドの試行回数を5回に制限します。また、ワークフロー共通パラメーターを使用して、 `PSComputerName` リモートノード (ターゲットコンピューター) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-131">It uses the `Parameter` parameter of `Invoke-AsWorkflow` to specify the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** .The command also uses the `PSConnectionRetryCount` workflow common parameter to limit the command to five attempts on each computer and the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span> <span data-ttu-id="c5dae-132">パラメーターの値 `PSComputerName` は、 `ServerName` 変数内のすべてのオブジェクトのプロパティを取得する式です `$s` 。</span><span class="sxs-lookup"><span data-stu-id="c5dae-132">The value of the `PSComputerName` parameter is an expression that gets the `ServerName` property of every object in the `$s` variable.</span></span>

<span data-ttu-id="c5dae-133">これらのコマンドは、数 `Get-ExecutionPolicy` 百のコンピューターでワークフローとしてコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-133">These commands run a `Get-ExecutionPolicy` command as a workflow on hundreds of computers.</span></span>
<span data-ttu-id="c5dae-134">このコマンドは、コマンド `Scope` レットのパラメーターを `Get-ExecutionPolicy` **Process** の値と共に使用して、現在のセッションの実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-134">The command uses the `Scope` parameter of the `Get-ExecutionPolicy` cmdlet with a value of **Process** to get the execution policy in the current session.</span></span>

### <span data-ttu-id="c5dae-135">例 3: 式をワークフローとして実行する</span><span class="sxs-lookup"><span data-stu-id="c5dae-135">Example 3: Run an expression as a workflow</span></span>

```powershell
Invoke-AsWorkflow -Expression "ipconfig /all" -PSComputerName (Get-Content DomainControllers.txt) -AsJob -JobName IPConfig
```

```output
Id     Name          PSJobTypeName   State         HasMoreData   Location                Command
--     ----          -------------   -----         -----------   --------                -------
2      IpConfig      PSWorkflowJob   Completed     True          Server01, Server01...   Invoke-AsWorkflow
```

<span data-ttu-id="c5dae-136">このコマンドは、ワークフローを使用し `Invoke-AsWorkflow` て、DomainControllers.txt ファイルに一覧表示されているコンピューター上のワークフロージョブとして Ipconfig コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-136">This command uses the `Invoke-AsWorkflow` workflow to run an Ipconfig command as a workflow job on the computers listed in the DomainControllers.txt file.</span></span>

<span data-ttu-id="c5dae-137">このコマンドは、パラメーターを使用して `Expression` 、実行する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-137">The command uses the `Expression` parameter to specify the expression to run.</span></span>
<span data-ttu-id="c5dae-138">ワークフロー共通パラメーターを使用して、 `PSComputerName` リモートノード (ターゲットコンピューター) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-138">It uses the `PSComputerName` workflow common parameter to specify the names of the remote nodes (target computers).</span></span>

<span data-ttu-id="c5dae-139">また、このコマンドは、ワークフロー共通パラメーターを使用して、 `AsJob` `JobName` 各コンピューターで "Ipconfig" ジョブ名を使用してワークフローをバックグラウンドジョブとして実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-139">The command also uses the `AsJob` and `JobName` workflow common parameters to run the workflow as a background job on each computer with the "Ipconfig" job name.</span></span>

<span data-ttu-id="c5dae-140">このコマンドは、 `ContainerParentJob` `System.Management.Automation.ContainerParentJob` 各コンピューター上のワークフロージョブを格納するオブジェクト () を返します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-140">The command returns a `ContainerParentJob` object (`System.Management.Automation.ContainerParentJob`) that contains the workflow jobs on each computer.</span></span>

## <span data-ttu-id="c5dae-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c5dae-141">PARAMETERS</span></span>

### <span data-ttu-id="c5dae-142">-CommandName</span><span class="sxs-lookup"><span data-stu-id="c5dae-142">-CommandName</span></span>

<span data-ttu-id="c5dae-143">指定されたコマンドレットまたは高度な関数をワークフローとして実行します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-143">Runs the specified cmdlet or advanced function as a workflow.</span></span>
<span data-ttu-id="c5dae-144">コマンドレットまたは関数の名前 (、、など) を入力し `Update-Help` `Set-ExecutionPolicy` `Set-NetFirewallRule` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-144">Enter the cmdlet or function name, such as `Update-Help`, `Set-ExecutionPolicy`, or `Set-NetFirewallRule`.</span></span>

```yaml
Type: System.String
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5dae-145">-式</span><span class="sxs-lookup"><span data-stu-id="c5dae-145">-Expression</span></span>

<span data-ttu-id="c5dae-146">このコマンドレットがワークフローとして実行する式を指定します。</span><span class="sxs-lookup"><span data-stu-id="c5dae-146">Specifies the  expression that this cmdlet runs as a workflow.</span></span>
<span data-ttu-id="c5dae-147">式を文字列として入力します。たとえば、のように `"ipconfig /all"` なります。</span><span class="sxs-lookup"><span data-stu-id="c5dae-147">Enter the expression as a string, such as `"ipconfig /all"`.</span></span>
<span data-ttu-id="c5dae-148">式にスペースや特殊文字が含まれている場合は、式を二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-148">If the expression includes spaces or special characters, enclose the expression in quotation marks.</span></span>

```yaml
Type: System.String
Parameter Sets: Expression
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5dae-149">-Parameter</span><span class="sxs-lookup"><span data-stu-id="c5dae-149">-Parameter</span></span>

<span data-ttu-id="c5dae-150">パラメーターで指定したコマンドのパラメーターとパラメーター値を指定し `CommandName` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-150">Specifies the parameters and parameter values of the command that is specified in the `CommandName` parameter.</span></span>
<span data-ttu-id="c5dae-151">各キーがパラメーター名で、その値がパラメーター値 (など) であるハッシュテーブルを入力し `@{ExecutionPolicy="AllSigned"}` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-151">Enter a hash table in which each key is a parameter name and its value is the parameter value, such as `@{ExecutionPolicy="AllSigned"}`.</span></span>

<span data-ttu-id="c5dae-152">ハッシュテーブルの詳細については、「 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dae-152">For information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: Command
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c5dae-153">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c5dae-153">-InputObject</span></span>

<span data-ttu-id="c5dae-154">パイプラインの入力を許可するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-154">Used to allows pipeline input.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c5dae-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5dae-155">CommonParameters</span></span>

<span data-ttu-id="c5dae-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c5dae-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c5dae-157">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dae-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

### <span data-ttu-id="c5dae-158">WorkflowCommonParameters</span><span class="sxs-lookup"><span data-stu-id="c5dae-158">WorkflowCommonParameters</span></span>

<span data-ttu-id="c5dae-159">このコマンドレットは、ワークフロー固有の共通パラメーターもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c5dae-159">This cmdlet also supports workflow specific common parameters.</span></span>
<span data-ttu-id="c5dae-160">詳細については、「 [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5dae-160">For information, see [about_WorkflowCommonParameters](../PSWorkflow/About/about_WorkflowCommonParameters.md).</span></span>

## <span data-ttu-id="c5dae-161">入力</span><span class="sxs-lookup"><span data-stu-id="c5dae-161">INPUTS</span></span>

### <span data-ttu-id="c5dae-162">System.Object</span><span class="sxs-lookup"><span data-stu-id="c5dae-162">System.Object</span></span>

<span data-ttu-id="c5dae-163">パイプを使用して任意のオブジェクトをパラメーターに渡し `InputObject` ます。</span><span class="sxs-lookup"><span data-stu-id="c5dae-163">You can pipe any object to the `InputObject` parameter.</span></span>

## <span data-ttu-id="c5dae-164">出力</span><span class="sxs-lookup"><span data-stu-id="c5dae-164">OUTPUTS</span></span>

### <span data-ttu-id="c5dae-165">なし</span><span class="sxs-lookup"><span data-stu-id="c5dae-165">None</span></span>

<span data-ttu-id="c5dae-166">このコマンドは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c5dae-166">This command does not generate any output.</span></span>
<span data-ttu-id="c5dae-167">ただし、実行するワークフローによって出力が生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="c5dae-167">However, it runs the workflow, which might generate output.</span></span>

## <span data-ttu-id="c5dae-168">注</span><span class="sxs-lookup"><span data-stu-id="c5dae-168">NOTES</span></span>

## <span data-ttu-id="c5dae-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c5dae-169">RELATED LINKS</span></span>

[<span data-ttu-id="c5dae-170">New-PSWorkflowExecutionOption</span><span class="sxs-lookup"><span data-stu-id="c5dae-170">New-PSWorkflowExecutionOption</span></span>](../PSWorkflow/New-PSWorkflowExecutionOption.md)

[<span data-ttu-id="c5dae-171">New-PSWorkflowSession</span><span class="sxs-lookup"><span data-stu-id="c5dae-171">New-PSWorkflowSession</span></span>](../PSWorkflow/New-PSWorkflowSession.md)

[<span data-ttu-id="c5dae-172">about_Workflows</span><span class="sxs-lookup"><span data-stu-id="c5dae-172">about_Workflows</span></span>](../PSWorkflow/About/about_Workflows.md)

[<span data-ttu-id="c5dae-173">about_Workflow_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="c5dae-173">about_Workflow_Common_Parameters</span></span>](../PSWorkflow/About/about_WorkflowCommonParameters.md)
