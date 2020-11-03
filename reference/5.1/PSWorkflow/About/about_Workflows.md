---
description: PowerShell ワークフロー機能の概要について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_workflows?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Workflows
ms.openlocfilehash: fbd8ee62b1e9c6969d489c5024c33f5cca883dc6
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221848"
---
# <a name="about-workflows"></a><span data-ttu-id="70d80-104">ワークフローについて</span><span class="sxs-lookup"><span data-stu-id="70d80-104">About Workflows</span></span>

## <a name="short-description"></a><span data-ttu-id="70d80-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="70d80-105">Short description</span></span>

<span data-ttu-id="70d80-106">PowerShell ワークフロー機能の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="70d80-106">Provides a brief introduction to the PowerShell Workflow feature.</span></span>

## <a name="long-description"></a><span data-ttu-id="70d80-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="70d80-107">Long description</span></span>

<span data-ttu-id="70d80-108">PowerShell ワークフローは、PowerShell に [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) の利点をもたらし、ワークフローの作成と実行を可能にします。</span><span class="sxs-lookup"><span data-stu-id="70d80-108">PowerShell Workflow brings the benefits of the [Windows Workflow Foundation](/dotnet/framework/windows-workflow-foundation) to PowerShell and enables you to write and run workflows.</span></span>

<span data-ttu-id="70d80-109">Powershell ワークフローは powershell 3.0 で導入され、PowerShell 5.1 で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="70d80-109">PowerShell Workflow was introduced in PowerShell 3.0 and the module is available up to PowerShell 5.1.</span></span> <span data-ttu-id="70d80-110">PowerShell ワークフローの詳細については、「 [ワークフローガイド](/previous-versions/powershell/scripting/components/workflows-guide) 」と「 [Windows Powershell ワークフローの作成](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-110">For more information about PowerShell Workflow, see the [Workflows Guide](/previous-versions/powershell/scripting/components/workflows-guide) and [Writing a Windows PowerShell Workflow](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow).</span></span>

## <a name="about-workflows"></a><span data-ttu-id="70d80-111">ワークフローについて</span><span class="sxs-lookup"><span data-stu-id="70d80-111">About workflows</span></span>

<span data-ttu-id="70d80-112">ワークフローは、一連の関連アクティビティで構成されるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="70d80-112">Workflows are commands that consist of an ordered sequence of related activities.</span></span> <span data-ttu-id="70d80-113">通常、これらは長時間にわたって実行され、多数のコンピューターに対してデータを収集し、変更を加えることがあります (多くの場合、異種環境で)。</span><span class="sxs-lookup"><span data-stu-id="70d80-113">Typically, they run for an extended period of time, gathering data from and making changes to hundreds of computers, often in heterogeneous environments.</span></span>

<span data-ttu-id="70d80-114">ワークフローは、XAML、Windows Workflow Foundation で使用される言語、または PowerShell 言語で記述できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-114">Workflows can be written in XAML, the language used in Windows Workflow Foundation, or in the PowerShell language.</span></span> <span data-ttu-id="70d80-115">ワークフローは通常、モジュールにパッケージ化され、ヘルプトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="70d80-115">Workflows are typically packaged in modules and include help topics.</span></span> <span data-ttu-id="70d80-116">詳細については、[XAML の概要 (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-116">For more information, see [XAML Overview (WPF)](/dotnet/framework/wpf/advanced/xaml-overview-wpf).</span></span>

<span data-ttu-id="70d80-117">ワークフローは、自動的に再起動され、一般的な障害から自動的に回復するため、IT 環境において重要です。</span><span class="sxs-lookup"><span data-stu-id="70d80-117">Workflows are critical in an IT environment because they can survive reboots and recover automatically from common failures.</span></span> <span data-ttu-id="70d80-118">ワークフローの処理を中断することなく、ワークフローを実行しているセッションとコンピューターから切断して再接続できます。また、データを失うことなく、ワークフローを透過的に中断および再開できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-118">You can disconnect and reconnect from sessions and computers running workflows without interrupting workflow processing, and suspend and resume workflows transparently without data loss.</span></span> <span data-ttu-id="70d80-119">ワークフロー内の各アクティビティは、参照用にログ記録および監査できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-119">Each activity in a workflow can be logged and audited for reference.</span></span>
<span data-ttu-id="70d80-120">ワークフローはジョブとして実行でき、PowerShell のスケジュールされたジョブ機能を使用してスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="70d80-120">Workflows can run as jobs and can be scheduled by using the Scheduled Jobs feature of PowerShell.</span></span>

<span data-ttu-id="70d80-121">ワークフローの状態とデータは、ワークフローの開始時と終了時、および指定したポイントで保存または永続化されます。</span><span class="sxs-lookup"><span data-stu-id="70d80-121">The state and data in a workflow is saved or persisted at the beginning and end of the workflow and at points that you specify.</span></span> <span data-ttu-id="70d80-122">ワークフローの永続化ポイントは、データベーススナップショットやプログラムチェックポイントと同様に動作し、中断や障害の影響からワークフローを保護します。</span><span class="sxs-lookup"><span data-stu-id="70d80-122">Workflow persistence points work like database snapshots or program checkpoints to protect the workflow from the effects of interruptions and failures.</span></span> <span data-ttu-id="70d80-123">ワークフローが障害から復旧できない場合は、永続化されたデータを使用し、最初から広範なワークフローを再実行するのではなく、最後の永続性ポイントから再開できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-123">If the workflow is unable to recover from a failure, you can use the persisted data and resume from the last persistence point, instead of rerunning an extensive workflow from the beginning.</span></span>

## <a name="workflow-requirements-and-configuration"></a><span data-ttu-id="70d80-124">ワークフローの要件と構成</span><span class="sxs-lookup"><span data-stu-id="70d80-124">Workflow requirements and configuration</span></span>

<span data-ttu-id="70d80-125">PowerShell ワークフローの構成は、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="70d80-125">A PowerShell Workflow configuration consists of the following elements:</span></span>

- <span data-ttu-id="70d80-126">ワークフローを実行するクライアントコンピューター。</span><span class="sxs-lookup"><span data-stu-id="70d80-126">A client computer, which runs the workflow.</span></span>
- <span data-ttu-id="70d80-127">クライアントコンピューター上またはリモートコンピューター上のワークフローセッション ( **PSSession** )。</span><span class="sxs-lookup"><span data-stu-id="70d80-127">A workflow session, **PSSession** , on the client computer or on a remote computer.</span></span>
- <span data-ttu-id="70d80-128">管理ノード。ワークフローアクティビティの影響を受ける対象コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="70d80-128">Managed nodes, the target computers that are affected by the workflow activities.</span></span>

<span data-ttu-id="70d80-129">ワークフローセッションは必須ではありませんが、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="70d80-129">The workflow session isn't required, but is recommended.</span></span> <span data-ttu-id="70d80-130">**Pssessions** は、PowerShell の堅牢な回復と切断されたセッションの機能を利用して、接続されていないワークフローセッションを復旧できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-130">**PSSessions** can take advantage of the robust recovery and Disconnected Sessions features of PowerShell to recover disconnected workflow sessions.</span></span> <span data-ttu-id="70d80-131">詳細については、「」を参照してください [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span><span class="sxs-lookup"><span data-stu-id="70d80-131">For more information, see [about_Remote_Disconnected_Sessions](../../Microsoft.PowerShell.Core/About/about_Remote_Disconnected_Sessions.md)</span></span>

<span data-ttu-id="70d80-132">ワークフローセッションが実行されているクライアントコンピューターとコンピューターを管理ノードにすることができるので、すべてのロールを満たす1台のコンピューターでワークフローを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-132">Because the client computer and the computer on which the workflow session runs can be managed nodes, you can run a workflow on a single computer that fulfills all roles.</span></span>

<span data-ttu-id="70d80-133">クライアントコンピューターと、ワークフローセッションが実行されているコンピューターは、PowerShell 3.0 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d80-133">The client computer and the computer on which the workflow session runs must be running PowerShell 3.0.</span></span> <span data-ttu-id="70d80-134">Windows Server オペレーティングシステムの Server Core インストールオプションを含む、対象となるすべてのシステムがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="70d80-134">All eligible systems are supported, including the Server Core installation options of Windows Server operating systems.</span></span>

<span data-ttu-id="70d80-135">コマンドレットを含むワークフローを実行するには、管理対象ノードに Windows PowerShell 2.0 以降がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d80-135">To run workflows that include cmdlets, the managed nodes must have Windows PowerShell 2.0 or later.</span></span> <span data-ttu-id="70d80-136">ワークフローにコマンドレットが含まれていない場合、管理対象ノードには PowerShell は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="70d80-136">Managed nodes don't require PowerShell unless the workflow includes cmdlets.</span></span> <span data-ttu-id="70d80-137">PowerShell がインストールされていないコンピューターでは、Windows Management Instrumentation (WMI) および Common Information Model (CIM) コマンドを含むワークフローを実行できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-137">You can run workflows that include Windows Management Instrumentation (WMI) and Common Information Model (CIM) commands on computers that don't have PowerShell.</span></span>

## <a name="how-to-get-workflows"></a><span data-ttu-id="70d80-138">ワークフローを取得する方法</span><span class="sxs-lookup"><span data-stu-id="70d80-138">How to get workflows</span></span>

<span data-ttu-id="70d80-139">ワークフローは通常、モジュールにパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="70d80-139">Workflows are typically packaged in modules.</span></span> <span data-ttu-id="70d80-140">ワークフローを含むモジュールをインポートするには、モジュール内の任意のコマンドを使用するか、またはコマンドレットを使用し `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="70d80-140">To import the module that includes a workflow, use any command in the module or use the `Import-Module` cmdlet.</span></span>
<span data-ttu-id="70d80-141">モジュールは、モジュール内のコマンドを初めて使用するときに自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="70d80-141">Modules are imported automatically on first use of any command in the module.</span></span>

<span data-ttu-id="70d80-142">コンピューターにインストールされているモジュール内のワークフローを検索するには、 `Get-Command` コマンドレットの **CommandType** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-142">To find the workflows in modules installed on your computer, use the `Get-Command` cmdlet's **CommandType** parameter.</span></span>

```powershell
Get-Command -CommandType Workflow
```

## <a name="how-to-run-workflows"></a><span data-ttu-id="70d80-143">ワークフローを実行する方法</span><span class="sxs-lookup"><span data-stu-id="70d80-143">How to run workflows</span></span>

<span data-ttu-id="70d80-144">ワークフローを実行するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-144">To run a workflow, use the following procedure.</span></span>

1. <span data-ttu-id="70d80-145">管理ノードがローカルコンピューターの場合、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="70d80-145">When the managed node is the local computer, this step isn't required.</span></span>
   <span data-ttu-id="70d80-146">それ以外の場合は、クライアントコンピューターで、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="70d80-146">Otherwise, on the client computer, start PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Start-Process PowerShell -Verb RunAs
   ```

1. <span data-ttu-id="70d80-147">ワークフローセッションを実行するコンピューターと、コマンドレットを含むワークフローの影響を受ける管理対象ノードで、PowerShell リモート処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="70d80-147">Enable PowerShell remoting on the computer that runs the workflow session and on managed nodes affected by workflows that include cmdlets.</span></span>

   <span data-ttu-id="70d80-148">この手順は、参加しているコンピューターごとに1回だけ行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="70d80-148">You only need to do this step once on each participating computer.</span></span>

   <span data-ttu-id="70d80-149">この手順は、コマンドレットを含むワークフローを実行する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="70d80-149">This step is required only when running workflows that include cmdlets.</span></span> <span data-ttu-id="70d80-150">ワークフローセッションがクライアントコンピューターで実行されている場合、または PowerShell 3.0 を実行している管理対象ノード上で実行されている場合を除き、クライアントコンピューターでリモート処理を有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="70d80-150">You don't need to enable remoting on the client computer, unless the workflows session runs on the client computer, or on any managed nodes that are running PowerShell 3.0.</span></span>

   <span data-ttu-id="70d80-151">リモート処理を有効にするには、コマンドレットを使用し `Enable-PSRemoting` ます。</span><span class="sxs-lookup"><span data-stu-id="70d80-151">To enable remoting, use the `Enable-PSRemoting` cmdlet.</span></span>

   ```powershell
   Enable-PSRemoting -Force
   ```

   <span data-ttu-id="70d80-152">リモート処理を有効にするには、 **[スクリプトの実行を有効に** する] グループポリシー設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-152">You can enable remoting by using the **Turn on Script Execution** Group Policy setting.</span></span> <span data-ttu-id="70d80-153">詳細については、「 [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) 」および「 [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-153">For more information, see [about_Group_Policy_Settings](../../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md) and [about_Execution_Policies](../../Microsoft.PowerShell.Core/About/about_Execution_Policies.md).</span></span>

1. <span data-ttu-id="70d80-154">またはコマンドレットを使用して、 `New-PSWorkflowSession` `New-PSSession` ワークフローセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="70d80-154">Use the `New-PSWorkflowSession` or `New-PSSession` cmdlets to create the workflow session.</span></span>

   <span data-ttu-id="70d80-155">コマンドレットでは、 `New-PSWorkflowSession` 対象のコンピューターで組み込みの **Microsoft. PowerShell ワークフロー** セッション構成を使用するセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="70d80-155">The `New-PSWorkflowSession` cmdlet starts a session that uses the built-in **Microsoft.PowerShell.Workflow** session configuration on the destination computer.</span></span> <span data-ttu-id="70d80-156">このセッション構成には、スクリプト、種類およびフォーマットファイル、およびワークフロー用に設計されたオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70d80-156">This session configuration includes scripts, type and formatting files, and options that are designed for workflows.</span></span>

   <span data-ttu-id="70d80-157">または、コマンドレットを使用し `New-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="70d80-157">Or, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="70d80-158">ConfigurationName **のセッション構成** を指定するには、 **ConfigurationName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-158">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span> <span data-ttu-id="70d80-159">このコマンドは、コマンドレットを使用した場合と同じです `New-PSWorkflowSession` 。</span><span class="sxs-lookup"><span data-stu-id="70d80-159">This command is the same as using the `New-PSWorkflowSession` cmdlet.</span></span>

   <span data-ttu-id="70d80-160">別の方法として、コマンドレットを使用することも `New-PSSession` できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-160">An alternative is to use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="70d80-161">ConfigurationName **のセッション構成** を指定するには、 **ConfigurationName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-161">Use the **ConfigurationName** parameter to specify the **Microsoft.PowerShell.Workflow** session configuration.</span></span>

   <span data-ttu-id="70d80-162">ローカルコンピューターの場合:</span><span class="sxs-lookup"><span data-stu-id="70d80-162">On the local computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession
   ```

   <span data-ttu-id="70d80-163">リモートコンピューターの場合:</span><span class="sxs-lookup"><span data-stu-id="70d80-163">On a remote computer:</span></span>

   ```powershell
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

   <span data-ttu-id="70d80-164">ワークフローセッションコンピューターの管理者である場合は、コマンドレットを使用して、 `New-PSWorkflowExecutionOption` ワークフローセッション構成のカスタムオプション設定を作成できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-164">If you are an Administrator on the workflow session computer, you can use the `New-PSWorkflowExecutionOption` cmdlet to create custom option settings for the workflow session configuration.</span></span> <span data-ttu-id="70d80-165">また、コマンドレットを使用して、 `Set-PSSessionConfiguration` セッション構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="70d80-165">And, use the `Set-PSSessionConfiguration` cmdlet to change the session configuration.</span></span>

   ```powershell
   $sto = New-PSWorkflowExecutionOption -MaxConnectedSessions 150
   Invoke-Command -ComputerName Server01 `
   {Set-PSSessionConfiguration Microsoft.PowerShell.Workflow `
   -SessionTypeOption $Using:sto}
   $ws = New-PSWorkflowSession -ComputerName Server01 `
   -Credential Domain01\Admin01
   ```

1. <span data-ttu-id="70d80-166">ワークフローセッションでワークフローを実行します。</span><span class="sxs-lookup"><span data-stu-id="70d80-166">Run the workflow in the workflow session.</span></span> <span data-ttu-id="70d80-167">管理対象ノードの名前 (対象コンピューター) を指定するには、 **PSComputerName** workflow 共通パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="70d80-167">To specify the names of the managed nodes, target computers, use the **PSComputerName** workflow common parameter.</span></span>

   <span data-ttu-id="70d80-168">次の例では、" **Test-workflow** " という名前のワークフローを実行します。</span><span class="sxs-lookup"><span data-stu-id="70d80-168">The following examples run the workflow named **Test-Workflow**.</span></span>

   <span data-ttu-id="70d80-169">ここで、管理ノードは、ワークフローセッションをホストするコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="70d80-169">Where the managed node is the computer that hosts the workflow session:</span></span>

   ```powershell
   Invoke-Command -Session $ws {Test-Workflow}
   ```

   <span data-ttu-id="70d80-170">管理対象ノードがリモートコンピューターの場合。</span><span class="sxs-lookup"><span data-stu-id="70d80-170">Where the managed nodes are remote computers.</span></span>

   ```powershell
   Invoke-Command -Session $ws{
   Test-Workflow -PSComputerName Server01, Server02 }
   ```

   <span data-ttu-id="70d80-171">次の例では、数百のコンピューターで **テストワークフロー** を実行します。</span><span class="sxs-lookup"><span data-stu-id="70d80-171">The following example runs the **Test-Workflow** on hundreds of computers.</span></span> <span data-ttu-id="70d80-172">`Get-Content`コマンドレットは、テキストファイルからコンピューター名を取得し、 `$Servers` ローカルコンピューター上の変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="70d80-172">The `Get-Content` cmdlet gets the computer names from a text file and saves them in the `$Servers` variable on the local computer.</span></span>

   <span data-ttu-id="70d80-173">`Invoke-Command` スコープ修飾子を使用して、 `$Using` `$Servers` ローカルセッションで変数を定義します。</span><span class="sxs-lookup"><span data-stu-id="70d80-173">`Invoke-Command` uses the `$Using` scope modifier to define the `$Servers` variable in the local session.</span></span> <span data-ttu-id="70d80-174">スコープ修飾子の詳細については `$Using` 、「 [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-174">For more information about the `$Using` scope modifier, see [about_Remote_Variables](../../Microsoft.PowerShell.Core/About/about_Remote_Variables.md).</span></span>

   ```powershell
   $Servers = Get-Content Servers.txt
   Invoke-Command -Session $ws {Test-Workflow -PSComputerName $Using:Servers }
   ```

## <a name="using-workflow-common-parameters"></a><span data-ttu-id="70d80-175">ワークフロー共通パラメーターの使用</span><span class="sxs-lookup"><span data-stu-id="70d80-175">Using workflow common parameters</span></span>

<span data-ttu-id="70d80-176">ワークフロー共通パラメーターは、PowerShell がすべてのワークフローに自動的に追加するパラメーターのセットです。</span><span class="sxs-lookup"><span data-stu-id="70d80-176">The workflow common parameters are a set of parameters that PowerShell adds automatically to all workflows.</span></span> <span data-ttu-id="70d80-177">PowerShell では、ワークフローでコマンドレット **バインド** 属性が使用されていない場合でも、すべてのワークフローにコマンドレットの共通パラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="70d80-177">PowerShell adds the cmdlet common parameters to all workflows, even if the workflow doesn't use the **CmdletBinding** attribute.</span></span>

<span data-ttu-id="70d80-178">たとえば、次のワークフローではパラメーターが定義されていません。</span><span class="sxs-lookup"><span data-stu-id="70d80-178">For example, the following workflow defines no parameters.</span></span> <span data-ttu-id="70d80-179">ただし、ワークフローを実行すると、 **commonparameters** と **workflowcommonparameters** の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="70d80-179">However, when you run the workflow, it has both the **CommonParameters** and **WorkflowCommonParameters**.</span></span>

```powershell
workflow Test-Workflow {Get-Process}
Get-Command Test-Workflow -Syntax
```

```powershell
Test-Workflow [<WorkflowCommonParameters>] [<CommonParameters>]
```

<span data-ttu-id="70d80-180">ワークフロー共通パラメーターには、ワークフローを実行するために必要ないくつかのパラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70d80-180">The workflow common parameters include several parameters that are essential to running workflows.</span></span> <span data-ttu-id="70d80-181">たとえば、 **PSComputerName** common パラメーターは、ワークフローが影響するマネージノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="70d80-181">For example, the **PSComputerName** common parameter specifies the managed nodes that the workflow affects.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02
}
```

<span data-ttu-id="70d80-182">**Pspersist** ワークフロー共通パラメーターは、ワークフローデータを永続化するタイミングを決定します。</span><span class="sxs-lookup"><span data-stu-id="70d80-182">The **PSPersist** workflow common parameter determines when workflow data is persisted.</span></span> <span data-ttu-id="70d80-183">永続化ポイントを定義しないワークフローに、アクティビティ間の永続化ポイントを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="70d80-183">It enables you to add persistence point between activities to workflows that don't define persistence points.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPersist:$True
}
```

<span data-ttu-id="70d80-184">その他のワークフロー共通パラメーターを使用すると、管理対象ノードへのリモート接続の特性を指定できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-184">Other workflow common parameters let you specify the characteristics of the remote connection to the managed nodes.</span></span> <span data-ttu-id="70d80-185">これらの名前と機能は、などのリモート処理コマンドレットのパラメーターに似てい `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="70d80-185">Their names and functionality are similar to the parameters of remoting cmdlets, including `Invoke-Command`.</span></span>

```powershell
Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSPort 443
}
```

<span data-ttu-id="70d80-186">ワークフローセッションの接続を定義するリモート処理パラメーターは、管理対象ノードへの接続を定義する、 **PS プレフィックス** が付けられたワークフロー共通パラメーターから区別するように注意してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-186">Take care to distinguish the remoting parameters that define the connection for the workflow session from the **PS-prefixed** workflow common parameters that define the connection to the managed nodes.</span></span>

```powershell
$ws = New-PSSession -ComputerName Server01 -ConfigurationName Microsoft.PowerShell.Workflow

Invoke-Command -Session $ws {
  Test-Workflow -PSComputerName Server01, Server02 -PSConfigurationName Microsoft.PowerShell.Workflow
}
```

<span data-ttu-id="70d80-187">ワークフロー共通パラメーターの中には、ワークフローに固有のものがあります。たとえば、 **PSParameterCollection** パラメーターを使用すると、さまざまなリモートノードに異なるワークフロー共通パラメーター値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="70d80-187">Some workflow common parameters are unique to workflows, such as the **PSParameterCollection** parameter that lets you specify different workflow common parameter values for different remote nodes.</span></span> <span data-ttu-id="70d80-188">ワークフロー共通パラメーターの一覧と説明については、「 [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70d80-188">For a list and description of the workflow common parameters, see [about_WorkflowCommonParameters](about_WorkflowCommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="70d80-189">関連項目</span><span class="sxs-lookup"><span data-stu-id="70d80-189">See also</span></span>

[<span data-ttu-id="70d80-190">Invoke-AsWorkflow</span><span class="sxs-lookup"><span data-stu-id="70d80-190">Invoke-AsWorkflow</span></span>](xref:PSWorkflowUtility.Invoke-AsWorkflow)

[<span data-ttu-id="70d80-191">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="70d80-191">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

<span data-ttu-id="70d80-192">[Psworkflow](xref:PSWorkflow) コマンドレット</span><span class="sxs-lookup"><span data-stu-id="70d80-192">[PSWorkflow](xref:PSWorkflow) cmdlets</span></span>

[<span data-ttu-id="70d80-193">ワークフロー ガイド</span><span class="sxs-lookup"><span data-stu-id="70d80-193">Workflows Guide</span></span>](/previous-versions/powershell/scripting/components/workflows-guide)

[<span data-ttu-id="70d80-194">Windows PowerShell ワークフローを記述する</span><span class="sxs-lookup"><span data-stu-id="70d80-194">Writing a Windows PowerShell Workflow</span></span>](/previous-versions/powershell/scripting/developer/workflow/writing-a-windows-powershell-workflow)
