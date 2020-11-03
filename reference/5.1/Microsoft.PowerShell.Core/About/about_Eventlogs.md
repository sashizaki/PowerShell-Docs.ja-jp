---
description: Windows powershell では、windows PowerShell イベントを記録するために、"Windows PowerShell" という名前の Windows イベントログが作成されます。 このログを表示するにはイベントビューアーまたはコマンドレットなどのイベントを取得するコマンドレットを使用し `Get-EventLog` ます。 既定では、Windows PowerShell エンジンとプロバイダーのイベントはイベントログに記録されますが、イベントログのユーザー設定変数を使用してイベントログをカスタマイズできます。 たとえば、Windows PowerShell コマンドに関するイベントを追加できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_eventlogs?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Eventlogs
ms.openlocfilehash: eb92333c6a6e220e287dcbec1441d2d05aa9275b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223507"
---
# <a name="about-eventlogs"></a><span data-ttu-id="5ad18-107">Eventlogs について</span><span class="sxs-lookup"><span data-stu-id="5ad18-107">About Eventlogs</span></span>

## <a name="short-description"></a><span data-ttu-id="5ad18-108">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="5ad18-108">Short Description</span></span>

<span data-ttu-id="5ad18-109">Windows powershell では、windows PowerShell イベントを記録するために、"Windows PowerShell" という名前の Windows イベントログが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-109">Windows PowerShell creates a Windows event log that is named "Windows PowerShell" to record Windows PowerShell events.</span></span> <span data-ttu-id="5ad18-110">このログを表示するにはイベントビューアーまたはコマンドレットなどのイベントを取得するコマンドレットを使用し `Get-EventLog` ます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-110">You can view this log in Event Viewer or by using cmdlets that get events, such as the `Get-EventLog` cmdlet.</span></span> <span data-ttu-id="5ad18-111">既定では、Windows PowerShell エンジンとプロバイダーのイベントはイベントログに記録されますが、イベントログのユーザー設定変数を使用してイベントログをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-111">By default, Windows PowerShell engine and provider events are recorded in the event log, but you can use the event log preference variables to customize the event log.</span></span> <span data-ttu-id="5ad18-112">たとえば、Windows PowerShell コマンドに関するイベントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-112">For example, you can add events about Windows PowerShell commands.</span></span>

## <a name="long-description"></a><span data-ttu-id="5ad18-113">長い説明</span><span class="sxs-lookup"><span data-stu-id="5ad18-113">Long Description</span></span>

<span data-ttu-id="5ad18-114">Windows powershell イベントログには、プログラムエンジンの起動と停止、Windows PowerShell プロバイダーの起動と停止など、Windows PowerShell の操作の詳細が記録されます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-114">The Windows PowerShell event log records details of Windows PowerShell operations, such as starting and stopping the program engine and starting and stopping the Windows PowerShell providers.</span></span> <span data-ttu-id="5ad18-115">Windows PowerShell コマンドの詳細をログに記録することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-115">You can also log details about Windows PowerShell commands.</span></span>

<span data-ttu-id="5ad18-116">Windows PowerShell イベントログは、[アプリケーションとサービスログ] グループにあります。</span><span class="sxs-lookup"><span data-stu-id="5ad18-116">The Windows PowerShell event log is in the Application and Services Logs group.</span></span> <span data-ttu-id="5ad18-117">Windows PowerShell ログは、Windows イベントのテクノロジを使用しない従来のイベントログです。</span><span class="sxs-lookup"><span data-stu-id="5ad18-117">The Windows PowerShell log is a classic event log that does not use the Windows Eventing technology.</span></span> <span data-ttu-id="5ad18-118">ログを表示するには、などの従来のイベントログ用に設計されたコマンドレットを使用し `Get-EventLog` ます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-118">To view the log, use the cmdlets designed for classic event logs, such as `Get-EventLog`.</span></span>

## <a name="viewing-the-windows-powershell-event-log"></a><span data-ttu-id="5ad18-119">Windows PowerShell イベントログの表示</span><span class="sxs-lookup"><span data-stu-id="5ad18-119">Viewing the Windows PowerShell Event Log</span></span>

<span data-ttu-id="5ad18-120">Windows PowerShell イベントログは、イベントビューアーで、または `Get-EventLog` コマンドレットとコマンドレットを使用して表示でき `Get-WmiObject` ます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-120">You can view the Windows PowerShell event log in Event Viewer or by using the `Get-EventLog` and `Get-WmiObject` cmdlets.</span></span> <span data-ttu-id="5ad18-121">Windows PowerShell ログの内容を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-121">To view the contents of the Windows PowerShell log, type:</span></span>

```powershell
Get-EventLog -LogName "Windows PowerShell"
```

<span data-ttu-id="5ad18-122">イベントとそのプロパティを調べるには、 `Sort-Object` コマンドレット、 `Group-Object` コマンドレット、および `Format` 動詞 (コマンドレット) を含むコマンド `Format` レットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-122">To examine the events and their properties, use the `Sort-Object` cmdlet, the `Group-Object` cmdlet, and the cmdlets that contain the `Format` verb (the `Format` cmdlets).</span></span>

<span data-ttu-id="5ad18-123">たとえば、イベント ID でグループ化されたログ内のイベントを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-123">For example, to view the events in the log grouped by the event ID, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" | Format-Table -GroupBy EventID
```

<span data-ttu-id="5ad18-124">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-124">Or, type:</span></span>

```powershell
Get-EventLog "Windows PowerShell" |
  Sort-Object EventID |
  Group-Object EventID
```

<span data-ttu-id="5ad18-125">すべてのクラシックイベントログを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-125">To view all the classic event logs, type:</span></span>

```powershell
Get-EventLog -List
```

<span data-ttu-id="5ad18-126">また、コマンドレットを使用して、イベント `Get-WmiObject` 関連の Windows Management Instrumentation (WMI) クラスを使用してイベントログを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-126">You can also use the `Get-WmiObject` cmdlet to use the event-related Windows Management Instrumentation (WMI) classes to examine the event log.</span></span> <span data-ttu-id="5ad18-127">たとえば、イベントログファイルのすべてのプロパティを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-127">For example, to view all the properties of the event log file, type:</span></span>

```powershell
Get-WmiObject Win32_NTEventlogFile |
  where LogFileName -EQ "Windows PowerShell" |
  Format-List -Property *
```

<span data-ttu-id="5ad18-128">Win32 イベント関連の WMI クラスを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-128">To find the Win32 event-related WMI classes, type:</span></span>

```powershell
Get-WmiObject -List | where Name -Like "win32*event*"
```

<span data-ttu-id="5ad18-129">詳細については、「Get-help Get-EventLog」と「Get-help Get-wmiobject」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="5ad18-129">For more information, type "Get-Help Get-EventLog" and "Get-Help Get-WmiObject".</span></span>

## <a name="selecting-events-for-the-windows-powershell-event-log"></a><span data-ttu-id="5ad18-130">Windows PowerShell イベントログのイベントの選択</span><span class="sxs-lookup"><span data-stu-id="5ad18-130">Selecting Events for the Windows PowerShell Event Log</span></span>

<span data-ttu-id="5ad18-131">イベントログのユーザー設定変数を使用して、Windows PowerShell イベントログに記録されるイベントを特定できます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-131">You can use the event log preference variables to determine which events are recorded in the Windows PowerShell event log.</span></span>

<span data-ttu-id="5ad18-132">イベントログのユーザー設定変数は6つあります。エンジン (Windows PowerShell プログラム)、プロバイダー、およびコマンドの3つの各ログコンポーネントに対して、2つの変数があります。</span><span class="sxs-lookup"><span data-stu-id="5ad18-132">There are six event log preference variables; two variables for each of the three logging components: the engine (the Windows PowerShell program), the providers, and the commands.</span></span> <span data-ttu-id="5ad18-133">LifeCycleEvent 変数は、通常の開始イベントと停止イベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-133">The LifeCycleEvent variables log normal starting and stopping events.</span></span> <span data-ttu-id="5ad18-134">正常性変数は、エラーイベントをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-134">The Health variables log error events.</span></span>

<span data-ttu-id="5ad18-135">次の表に、イベントログのユーザー設定変数を示します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-135">The following table lists the event log preference variables.</span></span>

|<span data-ttu-id="5ad18-136">変数</span><span class="sxs-lookup"><span data-stu-id="5ad18-136">Variable</span></span>                  |<span data-ttu-id="5ad18-137">説明</span><span class="sxs-lookup"><span data-stu-id="5ad18-137">Description</span></span>                                    |
|--------------------------|-----------------------------------------------|
|<span data-ttu-id="5ad18-138">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-138">$LogEngineLifeCycleEvent</span></span>  |<span data-ttu-id="5ad18-139">PowerShell の開始と停止をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-139">Logs the start and stop of PowerShell</span></span>          |
|<span data-ttu-id="5ad18-140">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-140">$LogEngineHealthEvent</span></span>     |<span data-ttu-id="5ad18-141">PowerShell プログラムエラーのログを記録します</span><span class="sxs-lookup"><span data-stu-id="5ad18-141">Logs PowerShell program errors</span></span>                 |
|<span data-ttu-id="5ad18-142">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-142">$LogProviderLifeCycleEvent</span></span>|<span data-ttu-id="5ad18-143">PowerShell プロバイダーの開始と停止をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-143">Logs the start and stop of PowerShell providers</span></span>|
|<span data-ttu-id="5ad18-144">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-144">$LogProviderHealthEvent</span></span>   |<span data-ttu-id="5ad18-145">PowerShell プロバイダーのエラーをログに記録します</span><span class="sxs-lookup"><span data-stu-id="5ad18-145">Logs PowerShell provider errors</span></span>                |
|<span data-ttu-id="5ad18-146">$LogCommandLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-146">$LogCommandLifeCycleEvent</span></span> |<span data-ttu-id="5ad18-147">コマンドの開始と完了をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-147">Logs the starting and completion of commands</span></span>   |
|<span data-ttu-id="5ad18-148">$LogCommandHealthEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-148">$LogCommandHealthEvent</span></span>    |<span data-ttu-id="5ad18-149">ログコマンドエラー</span><span class="sxs-lookup"><span data-stu-id="5ad18-149">Logs command errors</span></span>                            |

<span data-ttu-id="5ad18-150">(Windows PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5ad18-150">(For information about Windows PowerShell providers, see [about_Providers](about_Providers.md).)</span></span>

<span data-ttu-id="5ad18-151">既定では、次のイベントの種類のみが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="5ad18-151">By default, only the following event types are enabled:</span></span>

* <span data-ttu-id="5ad18-152">$LogEngineLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-152">$LogEngineLifeCycleEvent</span></span>
* <span data-ttu-id="5ad18-153">$LogEngineHealthEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-153">$LogEngineHealthEvent</span></span>
* <span data-ttu-id="5ad18-154">$LogProviderLifeCycleEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-154">$LogProviderLifeCycleEvent</span></span>
* <span data-ttu-id="5ad18-155">$LogProviderHealthEvent</span><span class="sxs-lookup"><span data-stu-id="5ad18-155">$LogProviderHealthEvent</span></span>

<span data-ttu-id="5ad18-156">イベントの種類を有効にするには、そのイベントの種類のユーザー設定変数を $true に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-156">To enable an event type, set the preference variable for that event type to $true.</span></span> <span data-ttu-id="5ad18-157">たとえば、コマンドのライフサイクルイベントを有効にするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-157">For example, to enable command life-cycle events, type:</span></span>

```powershell
$LogCommandLifeCycleEvent
```

<span data-ttu-id="5ad18-158">または、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-158">Or, type:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="5ad18-159">イベントの種類を無効にするには、そのイベントの種類のユーザー設定変数を $false に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-159">To disable an event type, set the preference variable for that event type to $false.</span></span> <span data-ttu-id="5ad18-160">たとえば、コマンドのライフサイクルイベントを無効にするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-160">For example, to disable command life-cycle events, type:</span></span>

```powershell
$LogProviderLifeCycleEvent = $false
```

<span data-ttu-id="5ad18-161">Windows PowerShell エンジンとコアプロバイダーが起動していることを示すイベントを除き、任意のイベントを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-161">You can disable any event, except for the events that indicate that the Windows PowerShell engine and the core providers are started.</span></span> <span data-ttu-id="5ad18-162">これらのイベントは、Windows PowerShell プロファイルが実行される前、およびホストプログラムがコマンドを受け入れる準備が整う前に生成されます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-162">These events are generated before the Windows PowerShell profiles are run and before the host program is ready to accept commands.</span></span>

<span data-ttu-id="5ad18-163">変数の設定は、現在の Windows PowerShell セッションに対してのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-163">The variable settings apply only for the current Windows PowerShell session.</span></span>
<span data-ttu-id="5ad18-164">すべての Windows PowerShell セッションに適用するには、Windows powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-164">To apply them to all Windows PowerShell sessions, add them to your Windows PowerShell profile.</span></span>

## <a name="logging-module-events"></a><span data-ttu-id="5ad18-165">モジュールイベントのログ記録</span><span class="sxs-lookup"><span data-stu-id="5ad18-165">Logging Module Events</span></span>

<span data-ttu-id="5ad18-166">Windows PowerShell 3.0 以降では、Windows PowerShell モジュールおよびスナップインのコマンドレットと関数の実行イベントを記録できます。これを行うには、モジュールとスナップインの LogPipelineExecutionDetails プロパティを TRUE に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-166">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets and functions in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="5ad18-167">Windows PowerShell 2.0 では、この機能はスナップインに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-167">In Windows PowerShell 2.0, this feature is available only for snap-ins.</span></span>

<span data-ttu-id="5ad18-168">LogPipelineExecutionDetails プロパティの値が TRUE () の場合 `$true` 、Windows powershell は、セッション内のコマンドレットと関数の実行イベントをイベントビューアーの Windows powershell ログに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-168">When the LogPipelineExecutionDetails property value is TRUE (`$true`), Windows PowerShell writes cmdlet and function execution events in the session to the Windows PowerShell log in Event Viewer.</span></span> <span data-ttu-id="5ad18-169">この設定は、現在のセッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="5ad18-169">The setting is effective only in the current session.</span></span>

<span data-ttu-id="5ad18-170">モジュール内のコマンドレットと関数の実行イベントのログ記録を有効にするには、次のコマンドシーケンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-170">To enable logging of execution events of cmdlets and functions in a module, use the following command sequence.</span></span>

```powershell
Import-Module <ModuleName>
$m = Get-Module <ModuleName>
$m.LogPipelineExecutionDetails = $true
```

<span data-ttu-id="5ad18-171">スナップインでコマンドレットの実行イベントのログ記録を有効にするには、次のコマンドシーケンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5ad18-171">To enable logging of execution events of cmdlets in a snap-in, use the following command sequence.</span></span>

```powershell
$m = Get-PSSnapin <SnapInName> [-Registered]
$m.LogPipelineExecutionDetails = $True
```

<span data-ttu-id="5ad18-172">ログ記録を無効にするには、同じコマンドシーケンスを使用して、プロパティ値を FALSE () に設定し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-172">To disable logging, use the same command sequence to set the property value to FALSE (`$false`).</span></span>

<span data-ttu-id="5ad18-173">また、[モジュールのログ記録を有効にする] グループポリシー設定を使用して、モジュールおよびスナップインのログ記録を有効または無効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-173">You can also use the "Turn on Module Logging" Group Policy setting to enable and disable module and snap-in logging.</span></span> <span data-ttu-id="5ad18-174">ポリシー値には、モジュール名とスナップイン名の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5ad18-174">The policy value includes a list of module and snap-in names.</span></span> <span data-ttu-id="5ad18-175">ワイルドカードを利用できます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-175">Wildcards are supported.</span></span>

<span data-ttu-id="5ad18-176">モジュールに [モジュールログをオンにする] が設定されている場合、モジュールの LogPipelineExecutionDetails プロパティの値はすべてのセッションで TRUE に設定され、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="5ad18-176">When "Turn on Module Logging" is set for a module, the value of the LogPipelineExecutionDetails property of the module is TRUE in all sessions and it cannot be changed.</span></span>

<span data-ttu-id="5ad18-177">[モジュールログを有効にする] グループポリシー設定は、次のグループポリシーパスにあります。</span><span class="sxs-lookup"><span data-stu-id="5ad18-177">The Turn On Module Logging group policy setting is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
     Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

<span data-ttu-id="5ad18-178">ユーザー構成ポリシーは、コンピューターの構成ポリシーよりも優先されます。両方のポリシーは、モジュールとスナップインの LogPipelineExecutionDetails プロパティの値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-178">The User Configuration policy takes precedence over the Computer Configuration policy, and both policies take preference over the value of the LogPipelineExecutionDetails property of modules and snap-ins.</span></span>

<span data-ttu-id="5ad18-179">このグループポリシー設定の詳細については、「 [about_Group_Policy_Settings](about_Group_Policy_Settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ad18-179">For more information about this Group Policy setting, see [about_Group_Policy_Settings](about_Group_Policy_Settings.md).</span></span>

## <a name="security-and-auditing"></a><span data-ttu-id="5ad18-180">セキュリティと監査</span><span class="sxs-lookup"><span data-stu-id="5ad18-180">Security and Auditing</span></span>

<span data-ttu-id="5ad18-181">Windows PowerShell イベントログは、アクティビティを示すと共に、トラブルシューティングのための操作の詳細を提供するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5ad18-181">The Windows PowerShell event log is designed to indicate activity and to provide operational details for troubleshooting.</span></span>

<span data-ttu-id="5ad18-182">ただし、ほとんどの Windows ベースのアプリケーションイベントログと同様に、Windows PowerShell イベントログはセキュリティで保護されていません。</span><span class="sxs-lookup"><span data-stu-id="5ad18-182">However, like most Windows-based application event logs, the Windows PowerShell event log is not designed to be secure.</span></span> <span data-ttu-id="5ad18-183">セキュリティの監査や機密情報の記録には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="5ad18-183">It should not be used to audit security or to record confidential or proprietary information.</span></span>

<span data-ttu-id="5ad18-184">イベントログは、ユーザーが読んで理解できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="5ad18-184">Event logs are designed to be read and understood by users.</span></span> <span data-ttu-id="5ad18-185">ユーザーは、ログの読み取りと書き込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-185">Users can read from and write to the log.</span></span> <span data-ttu-id="5ad18-186">悪意のあるユーザーが、ローカルコンピューターまたはリモートコンピューター上のイベントログを読み取り、偽のデータを記録して、それらのアクティビティのログ記録を防止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5ad18-186">A malicious user could read an event log on a local or remote computer, record false data, and then prevent the logging of their activities.</span></span>

## <a name="notes"></a><span data-ttu-id="5ad18-187">メモ</span><span class="sxs-lookup"><span data-stu-id="5ad18-187">Notes</span></span>

<span data-ttu-id="5ad18-188">モジュールの作成者は、モジュールにログ機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5ad18-188">Authors of module authors can add logging features to their modules.</span></span> <span data-ttu-id="5ad18-189">詳細については、「 [Windows PowerShell モジュールの記述](/powershell/scripting/developer/module/writing-a-windows-powershell-module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ad18-189">For more information, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

## <a name="see-also"></a><span data-ttu-id="5ad18-190">参照</span><span class="sxs-lookup"><span data-stu-id="5ad18-190">See Also</span></span>

[<span data-ttu-id="5ad18-191">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="5ad18-191">Get-EventLog</span></span>](xref:Microsoft.PowerShell.Management.Get-EventLog)

[<span data-ttu-id="5ad18-192">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="5ad18-192">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="5ad18-193">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="5ad18-193">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="5ad18-194">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="5ad18-194">about_Preference_Variables</span></span>](about_Preference_Variables.md)
