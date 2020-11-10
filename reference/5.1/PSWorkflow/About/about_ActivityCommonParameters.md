---
description: Windows PowerShell ワークフローによってアクティビティに追加されるパラメーターについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psworkflow/about/about_activitycommonparameters?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_ActivityCommonParameters
ms.openlocfilehash: 93fdcdb9c5afe0b73e843baf2474ec7d3f96a6cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94387806"
---
# <a name="about-activitycommonparameters"></a><span data-ttu-id="37c6b-104">ActivityCommonParameters について</span><span class="sxs-lookup"><span data-stu-id="37c6b-104">About ActivityCommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="37c6b-105">概要</span><span class="sxs-lookup"><span data-stu-id="37c6b-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="37c6b-106">Windows PowerShell ワークフローによってアクティビティに追加されるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-106">Describes the parameters that Windows PowerShell Workflow adds to activities.</span></span>

## <a name="long-description"></a><span data-ttu-id="37c6b-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="37c6b-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="37c6b-108">Windows PowerShell ワークフローは、PSActivity 基本クラスから派生したアクティビティにアクティビティ共通パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-108">Windows PowerShell Workflow adds the activity common parameters to activities that are derived from the PSActivity base class.</span></span> <span data-ttu-id="37c6b-109">このカテゴリには、アクティビティとして実装されている InlineScript アクティビティおよび Windows PowerShell コマンドレットが含まれます。たとえば、Get-Process や Get-WinEvent などです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-109">This category includes the InlineScript activity and Windows PowerShell cmdlets that are implemented as activities, such as Get-Process and Get-WinEvent.</span></span>

<span data-ttu-id="37c6b-110">アクティビティ共通パラメーターは Suspend-Workflow および Checkpoint-Workflow アクティビティでは無効であり、InlineScript スクリプトブロックまたは同様のアクティビティで Windows PowerShell ワークフローが自動的に実行するコマンドレットや式には追加されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-110">The activity common parameters are not valid on the Suspend-Workflow and Checkpoint-Workflow activities and they are not added to cmdlets or expressions that Windows PowerShell Workflow automatically runs in an InlineScript script block or similar activity.</span></span> <span data-ttu-id="37c6b-111">アクティビティ共通パラメーターは、InlineScript アクティビティでは使用できますが、InlineScript スクリプト ブロックのコマンドには使用できません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-111">The activity common parameters are available on the InlineScript activity, but not on commands in the InlineScript script block.</span></span>

<span data-ttu-id="37c6b-112">アクティビティ共通パラメーターのいくつかは、ワークフロー共通パラメーターまたは Windows PowerShell 共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-112">Several of the activity common parameters are also workflow common parameters or Windows PowerShell common parameters.</span></span> <span data-ttu-id="37c6b-113">その他のアクティビティ共通パラメーターは、アクティビティに固有です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-113">Other activity common parameters are unique to activities.</span></span>

<span data-ttu-id="37c6b-114">ワークフロー共通パラメーターについては、「about_WorkflowCommonParameters」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-114">For information about the workflow common parameters, see about_WorkflowCommonParameters.</span></span> <span data-ttu-id="37c6b-115">Windows PowerShell の共通パラメーターの詳細については、「about_CommonParameters」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-115">For information about the Windows PowerShell common parameters, see about_CommonParameters.</span></span>

### <a name="list-of-activity-common-parameters"></a><span data-ttu-id="37c6b-116">アクティビティ共通パラメーターの一覧</span><span class="sxs-lookup"><span data-stu-id="37c6b-116">LIST OF ACTIVITY COMMON PARAMETERS</span></span>

```
AppendOutput                      PSDebug
Debug                             PSDisableSerialization
DisplayName                       PSDisableSerializationPreference
ErrorAction                       PSError
Input                             PSPersist
MergeErrorToOutput                PSPort
PSActionRetryCount                PSProgress
PSActionRetryIntervalSec          PSProgressMessage
PSActionRunningTimeoutSec         PSRemotingBehavior
PSApplicationName                 PSRequiredModules
PSAuthentication                  PSSessionOption
PSCertificateThumbprint           PSUseSSL
PSComputerName                    PSVerbose
PSConfigurationName               PSWarning
PSConnectionRetryCount            Result
PSConnectionRetryIntervalSec      UseDefaultInput
PSConnectionURI                   Verbose
PSCredential                      WarningAction
```

### <a name="parameter-descriptions"></a><span data-ttu-id="37c6b-117">パラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="37c6b-117">PARAMETER DESCRIPTIONS</span></span>

<span data-ttu-id="37c6b-118">ここでは、アクティビティ共通パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-118">This section describes the activity common parameters.</span></span>

#### <a name="appendoutput-boolean"></a><span data-ttu-id="37c6b-119">AppendOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-119">AppendOutput \<Boolean\></span></span>

<span data-ttu-id="37c6b-120">値をにすると、 `$True` アクティビティの出力が変数の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-120">A value of `$True` adds the output of the activity to the value of the variable.</span></span>
<span data-ttu-id="37c6b-121">値をに `$False` しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-121">A value of `$False` has no effect.</span></span> <span data-ttu-id="37c6b-122">既定では、変数に値を代入することで変数の値が置き換わります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-122">By default, assigning a value to a variable replaces the variable value.</span></span>

<span data-ttu-id="37c6b-123">たとえば、次のコマンドは、変数内のサービスオブジェクトにプロセスオブジェクトを追加し `$x` ます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-123">For example, the following commands add a process object to the service object in the `$x` variable.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x = Get-Process -AppendOutput $true
}
```

<span data-ttu-id="37c6b-124">このパラメーターは、XAML ベースのワークフロー用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="37c6b-124">This parameter is designed for XAML-based workflows.</span></span> <span data-ttu-id="37c6b-125">スクリプトワークフローでは、次の例に示すように、+ = 代入演算子を使用して、出力を変数の値に追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-125">In script workflows, you can also use the += assignment operator to add output to the value of a variable, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $x = Get-Service
    $x += Get-Process
}
```

#### <a name="debug-switchparameter"></a><span data-ttu-id="37c6b-126">デバック \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="37c6b-126">Debug \<SwitchParameter\></span></span>

<span data-ttu-id="37c6b-127">コマンドによって実行される操作に関するプログラマレベルの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-127">Displays programmer-level detail about the operation performed by the command.</span></span>
<span data-ttu-id="37c6b-128">Debug パラメーターは、現在のコマンドの $DebugPreference 変数の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-128">The Debug parameter overrides the value of the $DebugPreference variable for the current command.</span></span> <span data-ttu-id="37c6b-129">このパラメーターは、コマンドによってデバッグメッセージが生成される場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-129">This parameter works only when the command generates debugging messages.</span></span> <span data-ttu-id="37c6b-130">このパラメーターは、Windows PowerShell 共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-130">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="displayname-string"></a><span data-ttu-id="37c6b-131">名 \<String\></span><span class="sxs-lookup"><span data-stu-id="37c6b-131">DisplayName \<String\></span></span>

<span data-ttu-id="37c6b-132">アクティビティのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-132">Specifies a friendly name for the activity.</span></span> <span data-ttu-id="37c6b-133">DisplayName の値は、ワークフローの実行中に進行状況バーに表示され、ワークフロージョブの Progress プロパティの値に表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-133">The DisplayName value appears in the progress bar while the workflow runs and in the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="37c6b-134">Psprogress Message パラメーターもコマンドに含まれている場合、進行状況バーの内容は次の形式で表示され \<DisplayName\> \<PSProgressMessage\> ます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-134">When the PSProgressMessage parameter is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

#### <a name="erroraction-actionpreference"></a><span data-ttu-id="37c6b-135">ErrorAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="37c6b-135">ErrorAction \<ActionPreference\></span></span>

<span data-ttu-id="37c6b-136">コマンドからの終了しないエラーに対してアクティビティがどのように応答するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-136">Determines how the activity responds to a non-terminating error from the command.</span></span> <span data-ttu-id="37c6b-137">終了エラーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-137">It has no effect on termination errors.</span></span> <span data-ttu-id="37c6b-138">このパラメーターは、コマンドが Write-Error コマンドレットなどの終了しないエラーを生成した場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-138">This parameter works only when the command generates a non-terminating error, such as those from the Write-Error cmdlet.</span></span> <span data-ttu-id="37c6b-139">ErrorAction パラメーターは、現在のコマンドの $ErrorActionPreference 変数の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-139">The ErrorAction parameter overrides the value of the $ErrorActionPreference variable for the current command.</span></span> <span data-ttu-id="37c6b-140">このパラメーターは、Windows PowerShell 共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-140">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="37c6b-141">有効な値:</span><span class="sxs-lookup"><span data-stu-id="37c6b-141">Valid values:</span></span>

- <span data-ttu-id="37c6b-142">まま.</span><span class="sxs-lookup"><span data-stu-id="37c6b-142">Continue.</span></span> <span data-ttu-id="37c6b-143">エラーメッセージを表示し、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-143">Displays the error message and continues executing the command.</span></span> <span data-ttu-id="37c6b-144">"Continue" が既定値です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-144">"Continue" is the default value.</span></span>

- <span data-ttu-id="37c6b-145">無視。</span><span class="sxs-lookup"><span data-stu-id="37c6b-145">Ignore.</span></span> <span data-ttu-id="37c6b-146">エラーメッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-146">Suppresses the error message and continues executing the command.</span></span>
  <span data-ttu-id="37c6b-147">SilentlyContinue とは異なり、Ignore では、エラーメッセージが $Error 自動変数に追加されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-147">Unlike SilentlyContinue, Ignore does not add the error message to the $Error automatic variable.</span></span> <span data-ttu-id="37c6b-148">Ignore 値は、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="37c6b-148">The Ignore value is introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="37c6b-149">Gina.</span><span class="sxs-lookup"><span data-stu-id="37c6b-149">Inquire.</span></span> <span data-ttu-id="37c6b-150">エラーメッセージを表示し、実行を続行する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-150">Displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="37c6b-151">この値はほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-151">This value is rarely used.</span></span>

- <span data-ttu-id="37c6b-152">中断 : </span><span class="sxs-lookup"><span data-stu-id="37c6b-152">Suspend.</span></span> <span data-ttu-id="37c6b-153">では、ワークフロージョブが自動的に中断され、さらに調査できるようになります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-153">Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="37c6b-154">調査後、ワークフローを再開できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-154">After investigation, the workflow can be resumed.</span></span>

- <span data-ttu-id="37c6b-155">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="37c6b-155">SilentlyContinue.</span></span> <span data-ttu-id="37c6b-156">エラーメッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-156">Suppresses the error message and continues executing the command.</span></span>

- <span data-ttu-id="37c6b-157">停止。</span><span class="sxs-lookup"><span data-stu-id="37c6b-157">Stop.</span></span> <span data-ttu-id="37c6b-158">エラーメッセージを表示し、コマンドの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-158">Displays the error message and stops executing the command.</span></span>

#### <a name="input-object"></a><span data-ttu-id="37c6b-159">代入 \<Object[]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-159">Input \<Object[]\></span></span>

<span data-ttu-id="37c6b-160">オブジェクトのコレクションをアクティビティに送信します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-160">Submits a collection of objects to an activity.</span></span> <span data-ttu-id="37c6b-161">これは、オブジェクトを 1 つずつアクティビティにパイプ処理することに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-161">This is an alternative to piping objects to the activity one at a time.</span></span>

#### <a name="mergeerrortooutput-boolean"></a><span data-ttu-id="37c6b-162">MergeErrorToOutput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-162">MergeErrorToOutput \<Boolean\></span></span>

<span data-ttu-id="37c6b-163">値をにすると、 `$True` エラーが出力ストリームに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-163">A value of `$True` adds errors to the output stream.</span></span> <span data-ttu-id="37c6b-164">の値は無効 `$False` です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-164">A value of `$False` has not effect.</span></span> <span data-ttu-id="37c6b-165">このパラメーターを Parallel およびキーワードと共に使用して、 `ForEach -Parallel` 1 つのコレクション内の複数の並列コマンドからのエラーと出力を収集します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-165">Use this parameter with the Parallel and `ForEach -Parallel` keywords to collect errors and output from multiple parallel commands in a single collection.</span></span>

#### <a name="psactionretrycount-int32"></a><span data-ttu-id="37c6b-166">PSActionRetryCount \<Int32\></span><span class="sxs-lookup"><span data-stu-id="37c6b-166">PSActionRetryCount \<Int32\></span></span>

<span data-ttu-id="37c6b-167">最初の試行が失敗した場合に、そのアクティビティの実行を繰り返し試みます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-167">Tries repeatedly to run the activity if the first attempt fails.</span></span> <span data-ttu-id="37c6b-168">既定値は 0 で、再試行は行いません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-168">The default value, 0, does not retry.</span></span>

#### <a name="psactionretryintervalsec-int32"></a><span data-ttu-id="37c6b-169">PSActionRetryIntervalSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="37c6b-169">PSActionRetryIntervalSec \<Int32\></span></span>

<span data-ttu-id="37c6b-170">操作の再試行の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-170">Determines the interval between action retries in seconds.</span></span> <span data-ttu-id="37c6b-171">既定値は 0 で、操作をすぐに再試行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-171">The default value, 0, retries the action immediately.</span></span> <span data-ttu-id="37c6b-172">このパラメーターは、PSActionRetryCount パラメーターがコマンドでも使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-172">This parameter is valid only when the PSActionRetryCount parameter is also used in the command.</span></span>

#### <a name="psactionrunningtimeoutsec-int32"></a><span data-ttu-id="37c6b-173">PSActionRunningTimeoutSec \<Int32\></span><span class="sxs-lookup"><span data-stu-id="37c6b-173">PSActionRunningTimeoutSec \<Int32\></span></span>

<span data-ttu-id="37c6b-174">アクティビティをそれぞれのターゲット コンピューターでどれくらいの時間にわたって実行できるかを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-174">Determines how long the activity can run on each target computer.</span></span> <span data-ttu-id="37c6b-175">タイムアウトの期限が切れる前にアクティビティが完了しない場合、Windows PowerShell ワークフローは終了エラーを生成し、影響を受けるターゲットコンピューターでのワークフローの処理を停止します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-175">If the activity does not complete before the timeout expires, Windows PowerShell Workflow generates a terminating error and stops processing the workflow on the affected target computer.</span></span>

#### <a name="psallowredirection-boolean"></a><span data-ttu-id="37c6b-176">PSAllowRedirection \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-176">PSAllowRedirection \<Boolean\></span></span>

<span data-ttu-id="37c6b-177">値 $True を指定すると、ターゲットコンピューターへの接続をリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-177">A value of $True allows redirection of the connection to the target computers.</span></span>
<span data-ttu-id="37c6b-178">$False の値は無効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-178">A value of $False has no effect.</span></span> <span data-ttu-id="37c6b-179">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-179">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-180">PSConnectionURI パラメーターを使用すると、リモートの送信先は別の URI にリダイレクトする命令を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-180">When you use the PSConnectionURI parameter, the remote destination can return an instruction to redirect to a different URI.</span></span> <span data-ttu-id="37c6b-181">既定では、Windows PowerShell は接続をリダイレクトしませんが、PSAllowRedirection パラメーターを $True の値と共に使用して、ターゲットコンピューターへの接続のリダイレクトを許可することができます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-181">By default, Windows PowerShell does not redirect connections, but you can use the PSAllowRedirection parameter with a value of $True to allow redirection of the connection to the target computer.</span></span>

<span data-ttu-id="37c6b-182">また、ユーザー設定変数の MaximumConnectionRedirectionCount プロパティを設定することによって、 `$PSSessionOption` またはセッションを作成するコマンドレットの SSessionOption パラメーターの値の MaximumConnectionRedirectionCount プロパティを設定することによって、接続をリダイレクトする回数を制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-182">You can also limit the number of times that the connection is redirected by setting the MaximumConnectionRedirectionCount property of the `$PSSessionOption` preference variable, or the MaximumConnectionRedirectionCount property of the value of the SSessionOption parameter of cmdlets that create a session.</span></span> <span data-ttu-id="37c6b-183">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-183">The default value is 5.</span></span>

#### <a name="psapplicationname-string"></a><span data-ttu-id="37c6b-184">PSApplicationName \<String\></span><span class="sxs-lookup"><span data-stu-id="37c6b-184">PSApplicationName \<String\></span></span>

<span data-ttu-id="37c6b-185">ターゲットコンピューターへの接続に使用される接続 URI のアプリケーション名セグメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-185">Specifies the application name segment of the connection URI that is used to connect to the target computers.</span></span> <span data-ttu-id="37c6b-186">コマンドで ConnectionURI パラメーターを使用しない場合は、このパラメーターを使用してアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-186">Use this parameter to specify the application name when you are not using the ConnectionURI parameter in the command.</span></span> <span data-ttu-id="37c6b-187">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-187">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-188">既定値は、対象のコンピューターのユーザー設定変数の値です `$PSSessionApplicationName` 。</span><span class="sxs-lookup"><span data-stu-id="37c6b-188">The default value is the value of the `$PSSessionApplicationName` preference variable on the target computer.</span></span> <span data-ttu-id="37c6b-189">このユーザー設定変数が定義されていない場合、既定値は WSMAN です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-189">If this preference variable is not defined, the default value is WSMAN.</span></span> <span data-ttu-id="37c6b-190">この値はほとんどの用途に適しています。</span><span class="sxs-lookup"><span data-stu-id="37c6b-190">This value is appropriate for most uses.</span></span> <span data-ttu-id="37c6b-191">詳細については、「 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-191">For more information, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="37c6b-192">WinRM サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-192">The WinRM service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="37c6b-193">このパラメーターの値は、リモート コンピューター上のリスナーの URLPrefix プロパティの値に一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-193">The value of this parameter should match the value of the URLPrefix property of a listener on the remote computer.</span></span>

#### <a name="psauthentication-authenticationmechanism"></a><span data-ttu-id="37c6b-194">PSAuthentication \<AuthenticationMechanism\></span><span class="sxs-lookup"><span data-stu-id="37c6b-194">PSAuthentication \<AuthenticationMechanism\></span></span>

<span data-ttu-id="37c6b-195">対象のコンピュータに接続するときに、ユーザーの資格情報を認証するために使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-195">Specifies the mechanism that is used to authenticate the user's credentials when connecting to the target computers.</span></span> <span data-ttu-id="37c6b-196">有効な値は、Default、Basic、Credssp、Digest、Kerberos、Negotiate、および NegotiateWithImplicitCredential です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-196">Valid values are Default, Basic, Credssp, Digest, Kerberos, Negotiate, and NegotiateWithImplicitCredential.</span></span> <span data-ttu-id="37c6b-197">既定値は Default です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-197">The default value is Default.</span></span> <span data-ttu-id="37c6b-198">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-198">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-199">このパラメーターの値の詳細については、PowerShell SDK の「 **システムの管理** 」列挙型の説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-199">For information about the values of this parameter, see the description of the **System.Management.Automation.Runspaces.AuthenticationMechanism** enumeration in the PowerShell SDK.</span></span>

> [!WARNING]
> <span data-ttu-id="37c6b-200">ユーザーの資格情報が認証対象のリモート コンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモート ネットワーク共有にアクセスする場合など、複数のリソースの認証を必要とするコマンドを対象としています。</span><span class="sxs-lookup"><span data-stu-id="37c6b-200">Credential Security Service Provider (CredSSP) authentication, in which the user's credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="37c6b-201">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-201">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="37c6b-202">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-202">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

#### <a name="pscertificatethumbprint-string"></a><span data-ttu-id="37c6b-203">PSCertificateThumbprint \<String\></span><span class="sxs-lookup"><span data-stu-id="37c6b-203">PSCertificateThumbprint \<String\></span></span>

<span data-ttu-id="37c6b-204">この処理を実行するアクセス許可を持つユーザー アカウントのデジタル公開キー証明書 (X509) を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-204">Specifies the digital public key certificate (X509) of a user account that has permission to perform this action.</span></span> <span data-ttu-id="37c6b-205">証明書の拇印を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-205">Enter the certificate thumbprint of the certificate.</span></span> <span data-ttu-id="37c6b-206">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-206">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-207">証明書は、クライアント証明書ベースの認証で使用されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-207">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="37c6b-208">これらの証明書は、ローカル ユーザー アカウントにしかマップできません。ドメイン アカウントでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-208">They can only be mapped to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="37c6b-209">証明書を取得するには、Windows PowerShell Cert: ドライブで [Get Item](xref:Microsoft.PowerShell.Management.Get-Item) または [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-209">To get a certificate, use the [Get-Item](xref:Microsoft.PowerShell.Management.Get-Item) or [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) cmdlets in the Windows PowerShell Cert: drive.</span></span>

#### <a name="pscomputername-string"></a><span data-ttu-id="37c6b-210">PSComputerName \<String[]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-210">PSComputerName \<String[]\></span></span>

<span data-ttu-id="37c6b-211">アクティビティを実行する対象のコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-211">Specifies the target computers on which the activity run.</span></span> <span data-ttu-id="37c6b-212">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-212">The default is the local computer.</span></span> <span data-ttu-id="37c6b-213">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-213">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-214">1 台または複数のコンピューターの NETBIOS 名、IP アドレス、または完全修飾ドメイン名をコンマ区切りリストで入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-214">Type the NETBIOS name, IP address, or fully-qualified domain name of one or more computers in a comma-separated list.</span></span> <span data-ttu-id="37c6b-215">ローカルのコンピューターを指定するには、コンピューター名、「localhost」、またはドット (.) を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-215">To specify the local computer, type the computer name, "localhost", or a dot (.).</span></span>

<span data-ttu-id="37c6b-216">PSComputerName パラメーターの値にローカルコンピューターを含めるには、[管理者として実行] オプションを使用して Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-216">To include the local computer in the value of the PSComputerName parameter, open Windows PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="37c6b-217">コマンドでこのパラメーターを省略した場合、または値が $null または空の文字列の場合、ワークフローターゲットはローカルコンピューターであり、Windows PowerShell リモート処理はコマンドの実行には使用されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-217">If this parameter is omitted from the command, or it value is $null or an empty string, the workflow target is the local computer and Windows PowerShell remoting is not used to run the command.</span></span>

<span data-ttu-id="37c6b-218">ComputerName パラメーターの値に IP アドレスを使用するには、コマンドに PSCredential パラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-218">To use an IP address in the value of the ComputerName parameter, the command must include the PSCredential parameter.</span></span> <span data-ttu-id="37c6b-219">また、HTTPS トランスポート用にコンピューターを構成するか、リモート コンピューターの IP アドレスをローカル コンピューター上の WinRM TrustedHosts 一覧に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-219">Also, the computer must be configured for HTTPS transport or the IP address of the remote computer must be included in the WinRM TrustedHosts list on the local computer.</span></span> <span data-ttu-id="37c6b-220">TrustedHosts の一覧にコンピューター名を追加する手順については、 [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md)の「信頼されたホストの一覧にコンピューターを追加する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-220">For instructions for adding a computer name to the TrustedHosts list, see "How to Add a Computer to the Trusted Host List" in [about_Remote_Troubleshooting](../../Microsoft.PowerShell.Core/About/about_Remote_Troubleshooting.md).</span></span>

#### <a name="psconfigurationname-string"></a><span data-ttu-id="37c6b-221">PSConfigurationName \<String\></span><span class="sxs-lookup"><span data-stu-id="37c6b-221">PSConfigurationName \<String\></span></span>

<span data-ttu-id="37c6b-222">対象のコンピューターでセッションを作成するために使用されるセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-222">Specifies the session configurations that are used to create sessions on the target computers.</span></span> <span data-ttu-id="37c6b-223">ワークフローを実行しているコンピューターではなく、対象のコンピューターにセッション構成の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-223">Enter the name of a session configuration on the target computers (not on the computer that is running the workflow.</span></span> <span data-ttu-id="37c6b-224">既定値は、Microsoft. PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-224">The default is Microsoft.PowerShell.</span></span> <span data-ttu-id="37c6b-225">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-225">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretrycount-uint"></a><span data-ttu-id="37c6b-226">PSConnectionRetryCount \<UInt\></span><span class="sxs-lookup"><span data-stu-id="37c6b-226">PSConnectionRetryCount \<UInt\></span></span>

<span data-ttu-id="37c6b-227">最初の接続試行が失敗した場合に、各ターゲットコンピュータへの接続試行回数の最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-227">Specifies the maximum number of attempts to connect to each target computer if the first connection attempt fails.</span></span> <span data-ttu-id="37c6b-228">1から 4294967295 (UInt) までの数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-228">Enter a number between 1 and 4,294,967,295 (UInt.MaxValue).</span></span> <span data-ttu-id="37c6b-229">既定値のゼロ (0) は、再試行の回数を表します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-229">The default value, zero (0), represents no retry attempts.</span></span>
<span data-ttu-id="37c6b-230">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-230">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionretryintervalsec-uint"></a><span data-ttu-id="37c6b-231">PSConnectionRetryIntervalSec \<UInt\></span><span class="sxs-lookup"><span data-stu-id="37c6b-231">PSConnectionRetryIntervalSec \<UInt\></span></span>

<span data-ttu-id="37c6b-232">接続再試行の間隔を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-232">Specifies the delay between connection retry attempts in seconds.</span></span> <span data-ttu-id="37c6b-233">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-233">The default value is zero (0).</span></span> <span data-ttu-id="37c6b-234">このパラメーターは、PSConnectionRetryCount の値が1以上の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-234">This parameter is valid only when the value of PSConnectionRetryCount is at least 1.</span></span> <span data-ttu-id="37c6b-235">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-235">This activity common parameter is also a workflow common parameter.</span></span>

#### <a name="psconnectionuri-systemuri"></a><span data-ttu-id="37c6b-236">PSConnectionURI \<System.Uri\></span><span class="sxs-lookup"><span data-stu-id="37c6b-236">PSConnectionURI \<System.Uri\></span></span>

<span data-ttu-id="37c6b-237">ターゲットコンピューター上のアクティビティの接続エンドポイントを定義する Uniform Resource Identifier (URI) を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-237">Specifies a Uniform Resource Identifier (URI) that defines the connection endpoint for the activity on the target computer.</span></span> <span data-ttu-id="37c6b-238">URI は完全修飾名にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-238">The URI must be fully qualified.</span></span> <span data-ttu-id="37c6b-239">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-239">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-240">この文字列の形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-240">The format of this string is as follows:</span></span>

```
<Transport>://<ComputerName>:<Port>/<ApplicationName>
```

<span data-ttu-id="37c6b-241">既定値は `http://localhost:5985/WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-241">The default value is `http://localhost:5985/WSMAN`.</span></span>

<span data-ttu-id="37c6b-242">PSConnectionURI を指定しない場合は、PSUseSSL、PSComputerName、PSPort、および PSApplicationName パラメーターを使用して PSConnectionURI 値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-242">If you do not specify a PSConnectionURI, you can use the PSUseSSL, PSComputerName, PSPort, and PSApplicationName parameters to specify the PSConnectionURI values.</span></span>

<span data-ttu-id="37c6b-243">URI のトランスポート セグメントの有効な値は、HTTP および HTTPS です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-243">Valid values for the Transport segment of the URI are HTTP and HTTPS.</span></span> <span data-ttu-id="37c6b-244">トランスポートセグメントを使用して接続 URI を指定し、ポートを指定しない場合、セッションは標準ポート80で HTTP 用および 443 (HTTPS 用) で作成されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-244">If you specify a connection URI with a Transport segment, but do not specify a port, the session is created with standards ports: 80 for HTTP and 443 for HTTPS.</span></span> <span data-ttu-id="37c6b-245">Windows PowerShell リモート処理用の既定のポートを使用するには、HTTP の場合は 5985、HTTPS の場合は 5986 を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-245">To use the default ports for Windows PowerShell remoting, specify port 5985 for HTTP or 5986 for HTTPS.</span></span>

#### <a name="pscredential-pscredential"></a><span data-ttu-id="37c6b-246">PSCredential \<PSCredential\></span><span class="sxs-lookup"><span data-stu-id="37c6b-246">PSCredential \<PSCredential\></span></span>

<span data-ttu-id="37c6b-247">対象のコンピューターでアクティビティを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-247">Specifies a user account that has permission to run the activity on the target computer.</span></span> <span data-ttu-id="37c6b-248">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-248">The default is the current user.</span></span> <span data-ttu-id="37c6b-249">このパラメーターは、PSComputerName パラメーターがコマンドに含まれている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-249">This parameter is valid only when the PSComputerName parameter is included in the command.</span></span> <span data-ttu-id="37c6b-250">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-250">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-251">"User01" や "Domain01\user01」" などのユーザー名を入力するか、Get-Credential コマンドレットから返されるような PSCredential オブジェクトを含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-251">Type a user name, such as "User01" or "Domain01\User01", or enter a variable that contains a PSCredential object, such as one that the Get-Credential cmdlet returns.</span></span> <span data-ttu-id="37c6b-252">ユーザー名のみを入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-252">If you enter only a user name, you will be prompted for a password.</span></span>

#### <a name="psdebug-psdatacollectiondebugrecord"></a><span data-ttu-id="37c6b-253">Set-psdebug \<PSDataCollection[DebugRecord]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-253">PSDebug \<PSDataCollection[DebugRecord]\></span></span>

<span data-ttu-id="37c6b-254">デバッグメッセージをコンソールに書き込むのではなく、指定されたデバッグレコードコレクションに追加します。また、ワークフロージョブの Debug プロパティの値にも追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-254">Adds debug messages from the activity to the specified debug record collection, instead of writing the debug messages to the console or to the value of the Debug property of the workflow job.</span></span> <span data-ttu-id="37c6b-255">複数のアクティビティからのデバッグ メッセージを、同じデバッグ レコード コレクション オブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-255">You can add debug messages from multiple activities to the same debug record collection object.</span></span>

<span data-ttu-id="37c6b-256">このアクティビティ共通パラメーターを使用するには、New-Object コマンドレットを使用して、DebugRecord 型の PSDataCollection オブジェクトを作成し、そのオブジェクトを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-256">To use this activity common parameter, use the New-Object cmdlet to create a PSDataCollection object with a type of DebugRecord and save the object in a variable.</span></span> <span data-ttu-id="37c6b-257">その後、次の例に示すように、1つ以上のアクティビティの PSDebug パラメーターの値として変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-257">Then, use the variable as the value of the PSDebug parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
    $debugCollection = New-Object -Type `
    System.Management.Automation.PSDataCollection[System.Management.Automation.DebugRecord]
    InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSDebug $debugCollection -Debug $True
    if ($debugCollection -like "Missing") { ...}
}
```

#### <a name="psdisableserialization-boolean"></a><span data-ttu-id="37c6b-258">PSDisableSerialization 場合 \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-258">PSDisableSerialization \<Boolean\></span></span>

<span data-ttu-id="37c6b-259">"ライブ" (シリアル化されていない) オブジェクトをワークフローに返すことをアクティビティに指示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-259">Directs the activity to return "live" (not serialized) objects to the workflow.</span></span>
<span data-ttu-id="37c6b-260">結果として得ることができるオブジェクトには、メソッドと共にプロパティがありますが、チェックポイントの取得時に保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-260">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>

#### <a name="psdisableserializationpreference-boolean"></a><span data-ttu-id="37c6b-261">PSDisableSerializationPreference \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-261">PSDisableSerializationPreference \<Boolean\></span></span>

<span data-ttu-id="37c6b-262">PSDisableSerialization パラメーターに相当するものを、アクティビティだけでなく、ワークフロー全体に適用します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-262">Applies the equivalent of the PSDisableSerialization parameter to the entire workflow, not just the activity.</span></span> <span data-ttu-id="37c6b-263">オブジェクトをシリアル化しないワークフローは再開または永続化できないため、通常、このパラメーターを追加することは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-263">Adding this parameter is generally not recommended, because a workflow that doesn't serialize its objects cannot be resumed or persisted.</span></span>

<span data-ttu-id="37c6b-264">有効な値:</span><span class="sxs-lookup"><span data-stu-id="37c6b-264">Valid values:</span></span>

- <span data-ttu-id="37c6b-265">標準省略した場合、PSDisableSerialization パラメーターをアクティビティに追加していないと、オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-265">(Default) If omitted, and you have also not added the PSDisableSerialization parameter to an activity, objects are serialized.</span></span>

- <span data-ttu-id="37c6b-266">`$True`.</span><span class="sxs-lookup"><span data-stu-id="37c6b-266">`$True`.</span></span> <span data-ttu-id="37c6b-267">ワークフロー内のすべてのアクティビティに、"ライブ" (シリアル化されていない) オブジェクトを返すよう指示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-267">Directs all activities within a workflow to return "live" (not serialized) objects.</span></span> <span data-ttu-id="37c6b-268">結果として得ることができるオブジェクトには、メソッドと共にプロパティがありますが、チェックポイントの取得時に保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-268">The resulting objects have methods, as well as properties, but they cannot be saved when a checkpoint is taken.</span></span>
- <span data-ttu-id="37c6b-269">`$False`.</span><span class="sxs-lookup"><span data-stu-id="37c6b-269">`$False`.</span></span> <span data-ttu-id="37c6b-270">ワークフロー オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-270">Workflow objects are serialized.</span></span>

#### <a name="pserror-psdatacollectionerrorrecord"></a><span data-ttu-id="37c6b-271">PSError \<PSDataCollection[ErrorRecord]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-271">PSError \<PSDataCollection[ErrorRecord]\></span></span>

<span data-ttu-id="37c6b-272">エラーメッセージをコンソールやワークフロージョブの Error プロパティの値に書き込む代わりに、アクティビティからのエラーメッセージを、指定したエラーレコードコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-272">Adds error messages from the activity to the specified error record collection, instead of writing the error messages to the console or to the value of the Error property of the workflow job.</span></span> <span data-ttu-id="37c6b-273">複数のアクティビティからのエラー メッセージを、同じエラー レコード コレクション オブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-273">You can add error messages from multiple activities to the same error record collection object.</span></span>

<span data-ttu-id="37c6b-274">このアクティビティ共通パラメーターを使用するには、コマンドレットを使用して、 `New-Object` ErrorRecord 型の PSDataCollection オブジェクトを作成し、そのオブジェクトを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-274">To use this activity common parameter, use the `New-Object` cmdlet to create a PSDataCollection object with a type of ErrorRecord and save the object in a variable.</span></span> <span data-ttu-id="37c6b-275">次に、次の例に示すように、1つ以上のアクティビティの PSError パラメーターの値として変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-275">Then, use the variable as the value of the PSError parameter of one or more activities, as shown in the following example.</span></span>

```powershell
Workflow Test-Workflow
{
   $typeName = "System.Management.Automation.PSDataCollection"
   $typeName += '[System.Management.Automation.ErrorRecord]'
   $ec = New-Object $typeName
   InlineScript {\Server01\Share01\Get-AssetData.ps1} -PSError $ec
   InlineScript {\Server01\Share01\Set-AssetData.ps1} -PSError $ec
   if ($ec.Count -gt 2)
   {
      # Do Some Work.
   }
}
```

#### <a name="pspersist-boolean"></a><span data-ttu-id="37c6b-276">PSPersist \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-276">PSPersist \<Boolean\></span></span>

<span data-ttu-id="37c6b-277">は、アクティビティの後にチェックポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-277">Takes a checkpoint after the activity.</span></span> <span data-ttu-id="37c6b-278">このチェックポイントは、ワークフローで指定されているすべてのチェックポイントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-278">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span> <span data-ttu-id="37c6b-279">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-279">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-280">"チェックポイント" または "永続化ポイント" とは、ワークフローの実行中にキャプチャされ、ディスク上の永続化ストアに保存される、ワークフローの状態とデータのスナップショットです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-280">A "checkpoint" or "persistence point" is a snapshot of the workflow state and data that is captured while the workflow runs and is saved to a persistence store on disk.</span></span> <span data-ttu-id="37c6b-281">Windows PowerShell ワークフローでは、保存されたデータを使用して、ワークフローを再開するのではなく、最後の永続化ポイントから中断または中断されたワークフローを再開します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-281">Windows PowerShell Workflow uses the saved data to resume a suspended or interrupted workflow from the last persistence point, rather than to restart the workflow.</span></span>

<span data-ttu-id="37c6b-282">有効な値:</span><span class="sxs-lookup"><span data-stu-id="37c6b-282">Valid values:</span></span>

- <span data-ttu-id="37c6b-283">標準このパラメーターを省略すると、チェックポイントは追加されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-283">(Default) If you omit this parameter, no checkpoints are added.</span></span> <span data-ttu-id="37c6b-284">チェックポイントは、ワークフローの設定に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-284">Checkpoints are taken based on the settings for the workflow.</span></span>

- <span data-ttu-id="37c6b-285">`$True`.</span><span class="sxs-lookup"><span data-stu-id="37c6b-285">`$True`.</span></span> <span data-ttu-id="37c6b-286">アクティビティの完了後に、チェックポイントを取得します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-286">Takes a checkpoint after the activity completes.</span></span>
  <span data-ttu-id="37c6b-287">このチェックポイントは、ワークフローで指定されているすべてのチェックポイントに追加されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-287">This checkpoint is in addition to any checkpoints that are specified in the workflow.</span></span>

- <span data-ttu-id="37c6b-288">`$False`.</span><span class="sxs-lookup"><span data-stu-id="37c6b-288">`$False`.</span></span> <span data-ttu-id="37c6b-289">チェックポイントは追加されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-289">No checkpoints are added.</span></span> <span data-ttu-id="37c6b-290">チェックポイントは、ワークフローで指定されている場合にのみ取得されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-290">Checkpoints are taken only when specified in the workflow.</span></span>

#### <a name="psport-int32"></a><span data-ttu-id="37c6b-291">PSPort \<Int32\></span><span class="sxs-lookup"><span data-stu-id="37c6b-291">PSPort \<Int32\></span></span>

<span data-ttu-id="37c6b-292">ターゲットコンピューターのネットワークポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-292">Specifies the network port on the target computers.</span></span> <span data-ttu-id="37c6b-293">既定のポート番号は 5985 (HTTP 用の WinRM ポート) と 5986 (HTTPS 用の WinRM ポート) です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-293">The default ports are 5985 (the WinRM port for HTTP) and 5986 (the WinRM port for HTTPS).</span></span> <span data-ttu-id="37c6b-294">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-294">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-295">必要な場合を除き、PSPort パラメーターは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-295">Do not use the PSPort parameter unless you must.</span></span> <span data-ttu-id="37c6b-296">コマンドで設定されたポートは、コマンドを実行するすべてのコンピューターまたはセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-296">The port set in the command applies to all computers or sessions on which the command runs.</span></span> <span data-ttu-id="37c6b-297">代替ポートの設定によっては、コマンドがすべてのコンピューターで実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-297">An alternate port setting might prevent the command from running on all computers.</span></span> <span data-ttu-id="37c6b-298">代替ポートを使用する前に、そのポートでリッスンするようにリモート コンピューター上の WinRM リスナーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-298">Before using an alternate port, you must configure the WinRM listener on the remote computer to listen at that port.</span></span>

#### <a name="psprogress-psdatacollectionprogressrecord"></a><span data-ttu-id="37c6b-299">PSProgress \<PSDataCollection[ProgressRecord]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-299">PSProgress \<PSDataCollection[ProgressRecord]\></span></span>

<span data-ttu-id="37c6b-300">進行状況メッセージをコンソールに書き込むのではなく、アクティビティからの進行状況メッセージを、ワークフロージョブの progress プロパティの値に追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-300">Adds progress messages from the activity to the specified progress record collection, instead of writing the progress messages to the console or to the value of the Progress property of the workflow job.</span></span> <span data-ttu-id="37c6b-301">複数のアクティビティからの進行状況メッセージを、同じ進行状況レコード コレクション オブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-301">You can add progress messages from multiple activities to the same progress record collection object.</span></span>

#### <a name="psprogressmessage-string"></a><span data-ttu-id="37c6b-302">Ps進捗メッセージ \<String\></span><span class="sxs-lookup"><span data-stu-id="37c6b-302">PSProgressMessage \<String\></span></span>

<span data-ttu-id="37c6b-303">アクティビティに関するわかりやすい説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-303">Specifies a friendly description of the activity.</span></span> <span data-ttu-id="37c6b-304">Psprogress メッセージ値は、ワークフローの実行中に進行状況バーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-304">The PSProgressMessage value appears in the progress bar while the workflow runs.</span></span> <span data-ttu-id="37c6b-305">DisplayName がコマンドにも含まれている場合、進行状況バーの内容は次の形式で表示され \<DisplayName\> \<PSProgressMessage\> ます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-305">When the DisplayName is also included in the command, the progress bar content appears in \<DisplayName\>:\<PSProgressMessage\> format.</span></span>

<span data-ttu-id="37c6b-306">このパラメーターは、ForEach-Parallel スクリプトブロック内のアクティビティを識別する場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-306">This parameter is particularly useful for identifying activities in a ForEach -Parallel script block.</span></span> <span data-ttu-id="37c6b-307">このメッセージがない場合、すべての並列分岐内のアクティビティは、同じ名前で識別されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-307">Without this message, activities in all parallel branches are identified by the same name.</span></span>

#### <a name="psremotingbehavior-remotingbehavior"></a><span data-ttu-id="37c6b-308">PSRemotingBehavior \<RemotingBehavior\></span><span class="sxs-lookup"><span data-stu-id="37c6b-308">PSRemotingBehavior \<RemotingBehavior\></span></span>

<span data-ttu-id="37c6b-309">ターゲット コンピューターでのアクティビティの実行時にリモート処理を管理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-309">Specifies how remoting is managed when the activity is run on target computers.</span></span>
<span data-ttu-id="37c6b-310">PowerShell が既定値です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-310">PowerShell is the default.</span></span>

<span data-ttu-id="37c6b-311">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="37c6b-311">Valid values are:</span></span>

- <span data-ttu-id="37c6b-312">[なし]: このアクティビティは、リモートコンピューターでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-312">None: The activity is not run on remote computers.</span></span>

- <span data-ttu-id="37c6b-313">PowerShell: Windows PowerShell リモート処理は、対象のコンピューターでアクティビティを実行するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-313">PowerShell: Windows PowerShell remoting is used to run the activity on target computers.</span></span>

- <span data-ttu-id="37c6b-314">カスタム: アクティビティは、独自の種類のリモート処理をサポートします。</span><span class="sxs-lookup"><span data-stu-id="37c6b-314">Custom: The activity supports its own type of remoting.</span></span> <span data-ttu-id="37c6b-315">この値は、アクティビティとして実装されているコマンドレットが RemotingCapability ビリティ属性の値を SupportedByCommand に設定し、コマンドに ComputerName パラメーターが含まれている場合に有効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-315">This value is valid when the cmdlet that is being implemented as an activity sets the value of the RemotingCapability attribute to SupportedByCommand and the command includes the ComputerName parameter.</span></span>

#### <a name="psrequiredmodules-string"></a><span data-ttu-id="37c6b-316">PSRequiredModules \<String[]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-316">PSRequiredModules \<String[]\></span></span>

<span data-ttu-id="37c6b-317">コマンドの実行前に、指定されたモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="37c6b-317">Imports the specified modules before running the command.</span></span> <span data-ttu-id="37c6b-318">モジュール名を入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-318">Enter the module names.</span></span> <span data-ttu-id="37c6b-319">モジュールはターゲットコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-319">The modules must be installed on the target computer.</span></span>

<span data-ttu-id="37c6b-320">PSModulePath 環境変数で指定されたパスにインストールされているモジュールは、モジュール内のコマンドを初めて使用するときに自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-320">Modules that are installed in a path specified in the PSModulePath environment variable are automatically imported on first use of any command in the module.</span></span>
<span data-ttu-id="37c6b-321">PSModulePath の場所にないモジュールをインポートするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-321">Use this parameter to import modules that are not in a PSModulePath location.</span></span>

<span data-ttu-id="37c6b-322">ワークフロー内の各アクティビティは独自のセッションで実行されるため、Import-Module コマンドは、アクティビティが実行されるセッションにのみモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="37c6b-322">Because each activity in a workflow runs in its own session, an Import-Module command imports a module only into the session in which it runs.</span></span> <span data-ttu-id="37c6b-323">その他のアクティビティが実行されるセッションにはモジュールはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-323">It does not import the module into sessions in which other activities run.</span></span>

#### <a name="pssessionoption-pssessionoption"></a><span data-ttu-id="37c6b-324">PSSessionOption \<PSSessionOption\></span><span class="sxs-lookup"><span data-stu-id="37c6b-324">PSSessionOption \<PSSessionOption\></span></span>

<span data-ttu-id="37c6b-325">セッションの詳細オプションを対象のコンピューターに設定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-325">Sets advanced options for the sessions to the target computers.</span></span> <span data-ttu-id="37c6b-326">New-PSSessionOption コマンドレットを使用して作成したものなど、PSSessionOption オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-326">Enter a PSSessionOption object, such as one that you create by using the New-PSSessionOption cmdlet.</span></span> <span data-ttu-id="37c6b-327">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-327">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-328">セッションオプションの既定値は、設定されている場合は、ユーザー設定変数の値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-328">The default values for the session options are determined by the value of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="37c6b-329">それ以外の場合は、セッション構成で指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-329">Otherwise, the session uses the values specified in the session configuration.</span></span>

<span data-ttu-id="37c6b-330">既定値を含むセッションオプションの説明については、New-PSSessionOption コマンドレットの [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)のヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-330">For a description of the session options, including the default values, see the help topic for the New-PSSessionOption cmdlet [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="37c6b-331">$PSSessionOption ユーザー設定変数の詳細については、「 [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="37c6b-331">For more information about the $PSSessionOption preference variable, see [about_Preference_Variables](../../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

#### <a name="psusessl-boolean"></a><span data-ttu-id="37c6b-332">PSUseSSL \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-332">PSUseSSL \<Boolean\></span></span>

<span data-ttu-id="37c6b-333">$True の値は、Secure Sockets Layer (SSL) プロトコルを使用して、対象のコンピューターへの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-333">A value of $True uses the Secure Sockets Layer (SSL) protocol to establish a connection to the target computer.</span></span> <span data-ttu-id="37c6b-334">既定では、SSL は使用されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-334">By default, SSL is not used.</span></span> <span data-ttu-id="37c6b-335">$False の値は無効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-335">A value of $False has no effect.</span></span> <span data-ttu-id="37c6b-336">このアクティビティ共通パラメーターは、ワークフロー共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-336">This activity common parameter is also a workflow common parameter.</span></span>

<span data-ttu-id="37c6b-337">WS-Management は、ネットワークを介して転送されるすべての Windows PowerShell コンテンツを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-337">WS-Management encrypts all Windows PowerShell content transmitted over the network.</span></span> <span data-ttu-id="37c6b-338">UseSSL は、HTTP 経由ではなく HTTPS 経由でデータを送信するために追加された保護機能です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-338">UseSSL is an additional protection that sends the data across an HTTPS, instead of HTTP.</span></span> <span data-ttu-id="37c6b-339">コマンドに使用するポートで SSL が使用できない場合に、このパラメーターを指定すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-339">If you use this parameter, but SSL is not available on the port used for the command, the command fails.</span></span>

#### <a name="psverbose-psdatacollectionverboserecord"></a><span data-ttu-id="37c6b-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-340">PSVerbose \<PSDataCollection[VerboseRecord]\></span></span>

<span data-ttu-id="37c6b-341">詳細メッセージをコンソールに書き込むのではなく、アクティビティからの詳細メッセージを指定した詳細レコードコレクションに追加します。または、ワークフロージョブの Verbose プロパティの値にも追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-341">Adds verbose messages from the activity to the specified verbose record collection, instead of writing the verbose messages to the console or to the value of the Verbose property of the workflow job.</span></span> <span data-ttu-id="37c6b-342">複数のアクティビティからの詳細メッセージを、同じ詳細レコード コレクション オブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-342">You can add verbose messages from multiple activities to the same verbose record collection object.</span></span>

#### <a name="pswarning-psdatacollectionwarningrecord"></a><span data-ttu-id="37c6b-343">PSWarning \<PSDataCollection[WarningRecord]\></span><span class="sxs-lookup"><span data-stu-id="37c6b-343">PSWarning \<PSDataCollection[WarningRecord]\></span></span>

<span data-ttu-id="37c6b-344">警告メッセージをコンソールに書き込むのではなく、指定した警告レコードコレクションに警告メッセージを追加します。また、ワークフロージョブの Warning プロパティの値にも追加します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-344">Adds warning messages from the activity to the specified warning record collection, instead of writing the warning messages to the console or to the value of the Warning property of the workflow job.</span></span> <span data-ttu-id="37c6b-345">複数のアクティビティからの警告メッセージを、同じ警告レコード コレクション オブジェクトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-345">You can add warning messages from multiple activities to the same warning record collection object.</span></span>

#### <a name="result"></a><span data-ttu-id="37c6b-346">結果</span><span class="sxs-lookup"><span data-stu-id="37c6b-346">Result</span></span>

<span data-ttu-id="37c6b-347">このパラメーターは、XAML ワークフローでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-347">This parameter is valid only in XAML workflows.</span></span>

#### <a name="usedefaultinput-boolean"></a><span data-ttu-id="37c6b-348">UseDefaultInput \<Boolean\></span><span class="sxs-lookup"><span data-stu-id="37c6b-348">UseDefaultInput \<Boolean\></span></span>

<span data-ttu-id="37c6b-349">すべてのワークフロー入力を、アクティビティへの値ごとの入力として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-349">Accepts all workflow input as input to the activity by value.</span></span>

<span data-ttu-id="37c6b-350">たとえば、次のサンプル ワークフローの Get-Process アクティビティでは、UseDefaultInput アクティビティ共通パラメーターを使用して、ワークフローに渡される値を取得します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-350">For example, the Get-Process activity in the following sample workflow uses the UseDefaultInput activity common parameter to get input that is passed to the workflow.</span></span> <span data-ttu-id="37c6b-351">入力を伴うワークフローを実行する場合、その入力がアクティビティによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-351">When you run the workflow with input, that input is used by the activity.</span></span>

```powershell
workflow Test-Workflow
{
    Get-Service -UseDefaultInput $True
}

PS C:> Test-Workflow -InputObject WinRm
```

```output
Status   Name        DisplayName                            PSComputerName
------   ----        -----------                            --------------
Running  winrm       Windows Remote Management (WS-Manag... localhost
```

#### <a name="verbose-switchparameter"></a><span data-ttu-id="37c6b-352">な \<SwitchParameter\></span><span class="sxs-lookup"><span data-stu-id="37c6b-352">Verbose \<SwitchParameter\></span></span>

<span data-ttu-id="37c6b-353">コマンドによって実行される操作に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-353">Displays detailed information about the operation performed by the command.</span></span>
<span data-ttu-id="37c6b-354">この情報は、トレースまたはトランザクションログの情報に似ています。</span><span class="sxs-lookup"><span data-stu-id="37c6b-354">This information resembles the information in a trace or in a transaction log.</span></span>
<span data-ttu-id="37c6b-355">Verbose パラメーターは、現在のコマンドの $VerbosePreference 変数の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-355">The Verbose parameter overrides the value of the $VerbosePreference variable for the current command.</span></span> <span data-ttu-id="37c6b-356">このパラメーターは、コマンドによって詳細メッセージが生成された場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-356">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="37c6b-357">このパラメーターは、Windows PowerShell 共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-357">This parameter is also a Windows PowerShell common parameter.</span></span>

#### <a name="warningaction-actionpreference"></a><span data-ttu-id="37c6b-358">WarningAction \<ActionPreference\></span><span class="sxs-lookup"><span data-stu-id="37c6b-358">WarningAction \<ActionPreference\></span></span>

<span data-ttu-id="37c6b-359">アクティビティが警告に応答する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-359">Determines how the activity responds to a warning.</span></span> <span data-ttu-id="37c6b-360">"Continue" が既定値です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-360">"Continue" is the default value.</span></span> <span data-ttu-id="37c6b-361">Warnings Action パラメーターは、現在のコマンドの $WarningPreference 変数の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-361">The WarningAction parameter overrides the value of the $WarningPreference variable for the current command.</span></span> <span data-ttu-id="37c6b-362">このパラメーターは、コマンドで警告メッセージが生成された場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-362">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="37c6b-363">このパラメーターは、Windows PowerShell 共通パラメーターでもあります。</span><span class="sxs-lookup"><span data-stu-id="37c6b-363">This parameter is also a Windows PowerShell common parameter.</span></span>

<span data-ttu-id="37c6b-364">有効な値 :</span><span class="sxs-lookup"><span data-stu-id="37c6b-364">Valid Values:</span></span>

- <span data-ttu-id="37c6b-365">SilentlyContinue.</span><span class="sxs-lookup"><span data-stu-id="37c6b-365">SilentlyContinue.</span></span> <span data-ttu-id="37c6b-366">警告メッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-366">Suppresses the warning message and continues executing the command.</span></span>

- <span data-ttu-id="37c6b-367">まま.</span><span class="sxs-lookup"><span data-stu-id="37c6b-367">Continue.</span></span> <span data-ttu-id="37c6b-368">警告メッセージを表示し、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-368">Displays the warning message and continues executing the command.</span></span>
  <span data-ttu-id="37c6b-369">"Continue" が既定値です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-369">"Continue" is the default value.</span></span>

- <span data-ttu-id="37c6b-370">Gina.</span><span class="sxs-lookup"><span data-stu-id="37c6b-370">Inquire.</span></span> <span data-ttu-id="37c6b-371">警告メッセージを表示し、実行を続行する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-371">Displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="37c6b-372">この値はほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-372">This value is rarely used.</span></span>

- <span data-ttu-id="37c6b-373">停止。</span><span class="sxs-lookup"><span data-stu-id="37c6b-373">Stop.</span></span> <span data-ttu-id="37c6b-374">警告メッセージを表示し、コマンドの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-374">Displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="37c6b-375">パラメーターをコマンドで使用してスクリプトまたは関数を実行する場合、Warnings Action パラメーターは $WarningAction preference 変数の値をオーバーライドしません。</span><span class="sxs-lookup"><span data-stu-id="37c6b-375">The WarningAction parameter does not override the value of the $WarningAction preference variable when the parameter is used in a command to run a script or function.</span></span>

### <a name="examples"></a><span data-ttu-id="37c6b-376">例</span><span class="sxs-lookup"><span data-stu-id="37c6b-376">EXAMPLES</span></span>

<span data-ttu-id="37c6b-377">アクティビティ共通パラメーターはきわめて便利です。</span><span class="sxs-lookup"><span data-stu-id="37c6b-377">The activity common parameters are extremely useful.</span></span> <span data-ttu-id="37c6b-378">たとえば、PSComputerName パラメーターを使用して、対象のコンピューターのサブセットのみで特定のアクティビティを実行できます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-378">For example, you can use the PSComputerName parameter to run particular activities on only a subset of the target computers.</span></span>

<span data-ttu-id="37c6b-379">または、PSConnectionRetryCount パラメーターと PSConnectionRetryIntervalSec パラメーターを使用して、特定のアクティビティの再試行値を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="37c6b-379">Or, you might use the PSConnectionRetryCount and PSConnectionRetryIntervalSec parameters to adjust the retry values for particular activities.</span></span>

<span data-ttu-id="37c6b-380">次の例では、PSComputerName activity 共通パラメーターを使用して、特定のドメインにあるコンピューターでのみ Get-EventLog アクティビティを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37c6b-380">The following example shows how to use the PSComputerName activity common parameters to run a Get-EventLog activity only on computers it a particular domain.</span></span>

```powershell
Workflow Test-Workflow
{
    $UserDomain = Get-Content -Path '.\UserComputers.txt'
    $Log = (Get-EventLog -LogName "Windows PowerShell" `
      -PSComputerName $UserDomain)

    if ($Log)
    {
        # Do Work Here.
    }
}
```

<!--
# KEYWORDS
[about_Activity_Common_Parameters](about_Activity_Common_Parameters.md)
[about_Activity_Parameters](about_Activity_Parameters.md)
[about_ActivityParameters]()about_ActivityParameters.md) -->

## <a name="see-also"></a><span data-ttu-id="37c6b-381">関連項目</span><span class="sxs-lookup"><span data-stu-id="37c6b-381">SEE ALSO</span></span>

<span data-ttu-id="37c6b-382">[about_Workflows](about_workflows.md) 
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span><span class="sxs-lookup"><span data-stu-id="37c6b-382">[about_Workflows](about_workflows.md)
[about_WorkflowCommonParameters](about_WorkflowCommonParameters.md)</span></span>
