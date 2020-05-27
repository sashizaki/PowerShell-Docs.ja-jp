---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: Desired State Configuration (DSC) の既知の問題と制限事項
ms.openlocfilehash: a76c5bb336804c5b384e6b6ba6a705c6049ef7fb
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808698"
---
# <a name="desired-state-configuration-dsc-known-issues-and-limitations"></a><span data-ttu-id="d5c97-103">Desired State Configuration (DSC) の既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="d5c97-103">Desired State Configuration (DSC) Known Issues and Limitations</span></span>

## <a name="breaking-change-certificates-used-to-encryptdecrypt-passwords-in-dsc-configurations-may-not-work-after-installing-wmf-50-rtm"></a><span data-ttu-id="d5c97-104">重要な変更: WMF 5.0 RTM をインストールした後、DSC 構成でパスワードの暗号化/暗号化の解除に使用される証明書が機能しない場合がある</span><span class="sxs-lookup"><span data-stu-id="d5c97-104">Breaking Change: Certificates used to encrypt/decrypt passwords in DSC configurations may not work after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="d5c97-105">WMF 4.0 および WMF 5.0 Preview リリースでは、DSC の構成内で 121 文字を超える長さのパスワードを使用できません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-105">In WMF 4.0 and WMF 5.0 Preview releases, DSC would not allow passwords in the configuration to be of length more than 121 characters.</span></span> <span data-ttu-id="d5c97-106">DSC では、長い強力なパスワードが必要な場合でも、短いパスワードを使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d5c97-106">DSC was forcing to use short passwords even if lengthy and strong password was desired.</span></span> <span data-ttu-id="d5c97-107">この重要な変更により、DSC 構成で任意の長さのパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5c97-107">This breaking change allows passwords to be of arbitrary length in the DSC configuration.</span></span>

<span data-ttu-id="d5c97-108">**解決策:** データの暗号化またはキーの暗号化のキー使用法と、ドキュメントの暗号化の拡張キー使用法 (1.3.6.1.4.1.311.80.1) を含む証明書を再作成します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-108">**Resolution:** Re-create the certificate with Data Encipherment or Key Encipherment Key usage, and Document Encryption Enhanced Key usage (1.3.6.1.4.1.311.80.1).</span></span> <span data-ttu-id="d5c97-109">詳細については、「[Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5c97-109">For more information, see [Protect-CmsMessage](/powershell/module/Microsoft.PowerShell.Security/Protect-CmsMessage).</span></span>

## <a name="dsc-cmdlets-may-fail-after-installing-wmf-50-rtm"></a><span data-ttu-id="d5c97-110">WMF 5.0 RTM をインストールした後、DSC のコマンドレットが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="d5c97-110">DSC cmdlets may fail after installing WMF 5.0 RTM</span></span>

<span data-ttu-id="d5c97-111">WMF 5.0 RTM をインストールした後、`Start-DscConfiguration` および他の DSC コマンドレットが次のエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="d5c97-111">`Start-DscConfiguration` and other DSC cmdlets may fail after installing WMF 5.0 RTM with the following error:</span></span>

```Output
LCM failed to retrieve the property PendingJobStep from the object of class dscInternalCache .
+ CategoryInfo : ObjectNotFound: (root/Microsoft/...gurationManager:String) [], CimException
+ FullyQualifiedErrorId : MI RESULT 6
+ PSComputerName : localhost
```

<span data-ttu-id="d5c97-112">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して DSCEngineCache.mof を削除します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-112">**Resolution:** Delete DSCEngineCache.mof by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Remove-Item -Path $env:SystemRoot\system32\Configuration\DSCEngineCache.mof
```

## <a name="dsc-cmdlets-may-not-work-if-wmf-50-rtm-is-installed-on-top-of-wmf-50-production-preview"></a><span data-ttu-id="d5c97-113">WMF 5.0 RTM を WMF 5.0 Production Preview の上にインストールした場合、DSC コマンドレットが機能しない場合がある。</span><span class="sxs-lookup"><span data-stu-id="d5c97-113">DSC cmdlets may not work if WMF 5.0 RTM is installed on top of WMF 5.0 Production Preview</span></span>

<span data-ttu-id="d5c97-114">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-114">**Resolution:** Run the following command in an elevated PowerShell session (run as administrator):</span></span>

```powershell
mofcomp $env:windir\system32\wbem\DscCoreConfProv.mof
```

## <a name="lcm-can-go-into-an-unstable-state-while-using-get-dscconfiguration-in-debugmode"></a><span data-ttu-id="d5c97-115">Get-DscConfiguration を DebugMode で使用しているときに LCM が不安定な状態になることがある</span><span class="sxs-lookup"><span data-stu-id="d5c97-115">LCM can go into an unstable state while using Get-DscConfiguration in DebugMode</span></span>

<span data-ttu-id="d5c97-116">LCM が DebugMode の場合、Ctrl + C キーを押して `Get-DscConfiguration` の処理を停止すると、DSC コマンドレットの大部分が機能しないような不安定な状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="d5c97-116">If LCM is in DebugMode, pressing CTRL+C to stop the processing of `Get-DscConfiguration` can cause LCM to go into an unstable state such that majority of DSC cmdlets won’t work.</span></span>

<span data-ttu-id="d5c97-117">**解決策:** `Get-DscConfiguration` コマンドレットのデバッグ中は、Ctrl + C キーを押さないでください。</span><span class="sxs-lookup"><span data-stu-id="d5c97-117">**Resolution:** Don’t press CTRL+C while debugging `Get-DscConfiguration` cmdlet.</span></span>

## <a name="stop-dscconfiguration-may-not-respond-in-debugmode"></a><span data-ttu-id="d5c97-118">Stop-DscConfiguration が DebugMode で応答しないことがある</span><span class="sxs-lookup"><span data-stu-id="d5c97-118">Stop-DscConfiguration may not respond in DebugMode</span></span>

<span data-ttu-id="d5c97-119">LCM が DebugMode の場合、`Get-DscConfiguration` で開始された操作を停止しようとすると、`Stop-DscConfiguration` が応答しない場合があります</span><span class="sxs-lookup"><span data-stu-id="d5c97-119">If LCM is in DebugMode, `Stop-DscConfiguration` may not respond while trying to stop an operation started by `Get-DscConfiguration`</span></span>

<span data-ttu-id="d5c97-120">**解決策:** `Get-DscConfiguration` で開始された操作のデバッグを「[DSC リソースのデバッグ](/powershell/scripting/dsc/troubleshooting/debugResource)」の説明に従って終了します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-120">**Resolution:** Finish the debugging of the operation started by `Get-DscConfiguration` as outlined in [Debugging DSC resources](/powershell/scripting/dsc/troubleshooting/debugResource).</span></span>

## <a name="no-verbose-error-messages-are-shown-in-debugmode"></a><span data-ttu-id="d5c97-121">DebugMode で詳細なエラー メッセージが表示されない</span><span class="sxs-lookup"><span data-stu-id="d5c97-121">No Verbose Error Messages are shown in DebugMode</span></span>

<span data-ttu-id="d5c97-122">LCM が **DebugMode** の場合は、DSC リソースから詳細なエラー メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-122">If LCM is in **DebugMode**, no verbose error messages are displayed from DSC Resources.</span></span>

<span data-ttu-id="d5c97-123">**解決策:** リソースからの詳細なメッセージを表示するには、**DebugMode** を無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5c97-123">**Resolution:** Disable **DebugMode** to see verbose messages from the resource</span></span>

## <a name="invoke-dscresource-operations-cannot-be-retrieved-by-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="d5c97-124">Get-DscConfigurationStatus コマンドレットで Invoke-DscResource 操作を取得できない</span><span class="sxs-lookup"><span data-stu-id="d5c97-124">Invoke-DscResource operations cannot be retrieved by Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="d5c97-125">`Invoke-DscResource` コマンドレットを使用してリソースのメソッドを直接呼び出した後、このような操作のレコードを `Get-DscConfigurationStatus` によって取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-125">After using `Invoke-DscResource` cmdlet to directly invoke any resource’s methods, the records of such operation cannot be retrieved through `Get-DscConfigurationStatus`.</span></span>

<span data-ttu-id="d5c97-126">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-126">**Resolution:** None.</span></span>

## <a name="get-dscconfigurationstatus-returns-pull-cycle-operations-as-type-consistency"></a><span data-ttu-id="d5c97-127">Get-DscConfigurationStatus でプル サイクル操作がタイプ **Consistency** として返される</span><span class="sxs-lookup"><span data-stu-id="d5c97-127">Get-DscConfigurationStatus returns pull cycle operations as type **Consistency**</span></span>

<span data-ttu-id="d5c97-128">ノードがプル更新モードに設定されている場合、プル操作を実行するたびに、`Get-DscConfigurationStatus` コマンドレットで操作のタイプが *Initial* ではなく **Consistency** としてレポートされます</span><span class="sxs-lookup"><span data-stu-id="d5c97-128">When a node is set to PULL refresh mode, for each pull operation performed, `Get-DscConfigurationStatus` cmdlet reports the operation type as **Consistency** instead of *Initial*</span></span>

<span data-ttu-id="d5c97-129">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-129">**Resolution:** None.</span></span>

## <a name="invoke-dscresource-cmdlet-does-not-return-message-in-the-order-they-were-produced"></a><span data-ttu-id="d5c97-130">Invoke-DscResource コマンドレットで、メッセージが生成された順序で返されない</span><span class="sxs-lookup"><span data-stu-id="d5c97-130">Invoke-DscResource cmdlet does not return message in the order they were produced</span></span>

<span data-ttu-id="d5c97-131">`Invoke-DscResource` コマンドレットでは、詳細、警告、およびエラー メッセージは LCM または DSC リソースによって生成された順序で返されません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-131">The `Invoke-DscResource` cmdlet does not return verbose, warning, and error messages in the order they were produced by LCM or the DSC resource.</span></span>

<span data-ttu-id="d5c97-132">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-132">**Resolution:** None.</span></span>

## <a name="dsc-resources-cannot-be-debugged-easily-when-used-with-invoke-dscresource"></a><span data-ttu-id="d5c97-133">Invoke-DscResource と共に使用すると、DSC リソースを簡単にデバッグできない</span><span class="sxs-lookup"><span data-stu-id="d5c97-133">DSC Resources cannot be debugged easily when used with Invoke-DscResource</span></span>

<span data-ttu-id="d5c97-134">LCM がデバッグ モードで実行されている場合、`Invoke-DscResource` コマンドレットでデバッグ用に接続する実行空間に関する情報が提供されません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-134">When LCM is running in debug mode, `Invoke-DscResource` cmdlet does not give information about runspace to connect to for debugging.</span></span> <span data-ttu-id="d5c97-135">詳細については、「[DSC リソースのデバッグ](/powershell/scripting/dsc/troubleshooting/debugResource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5c97-135">For more information, see [Debugging DSC resources](/powershell/scripting/dsc/troubleshooting/debugResource).</span></span>

<span data-ttu-id="d5c97-136">**解決策:** `Get-PSHostProcessInfo`、`Enter-PSHostProcess`、`Get-Runspace`、および `Debug-Runspace` コマンドレットを使用して実行空間を検出してアタッチし、DSC リソースをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="d5c97-136">**Resolution:** Discover and attach to the runspace using cmdlets `Get-PSHostProcessInfo`, `Enter-PSHostProcess` , `Get-Runspace` and `Debug-Runspace` to debug the DSC resource.</span></span>

```powershell
# Find all the processes hosting PowerShell
Get-PSHostProcessInfo

ProcessName    ProcessId AppDomainName
-----------    --------- -------------
powershell          3932 DefaultAppDomain
powershell_ise      2304 DefaultAppDomain
WmiPrvSE            3396 DscPsPluginWkr_AppDomain

# Enter the process that is hosting DSC engine (WMI process with DscPsPluginWkr_Appdomain)
Enter-PSHostProcess -Id 3396 -AppDomainName DscPsPluginWkr_AppDomain

# Find all the available rusnspaces in that process
Get-Runspace

Id Name       ComputerName Type  State  Availability
-- ----       ------------ ----  -----  ------------
 2 Runspace2  localhost    Local Opened InBreakpoint
 5 RemoteHost localhost    Local Opened Busy

# Debug the runspace that is in **InBreakpoint** availability state
Debug-Runspace -Id 2
```

## <a name="various-partial-configuration-documents-for-same-node-cannot-have-identical-resource-names"></a><span data-ttu-id="d5c97-137">同じノードのさまざまな部分構成ドキュメントが同じリソース名を持つことができない</span><span class="sxs-lookup"><span data-stu-id="d5c97-137">Various Partial Configuration documents for same node cannot have identical resource names</span></span>

<span data-ttu-id="d5c97-138">1 つのノード上に展開される複数の部分構成では、リソース名が同一であることが実行時エラーの原因となります。</span><span class="sxs-lookup"><span data-stu-id="d5c97-138">For several partial configurations that are deployed onto a single node, identical names of resources cause run time error.</span></span>

<span data-ttu-id="d5c97-139">**解決策:** 異なる部分構成では、同じリソースでも異なる名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-139">**Resolution:** Use different names for even same resources in different partial configurations.</span></span>

## <a name="start-dscconfiguration-useexisting-does-not-work-with--credential"></a><span data-ttu-id="d5c97-140">Start-DscConfiguration -UseExisting が -Credential で機能しない</span><span class="sxs-lookup"><span data-stu-id="d5c97-140">Start-DscConfiguration –UseExisting does not work with -Credential</span></span>

<span data-ttu-id="d5c97-141">`Start-DscConfiguration` を **UseExisting** パラメーターと共に使用すると、**Credential** パラメーターが無視されます。</span><span class="sxs-lookup"><span data-stu-id="d5c97-141">When using `Start-DscConfiguration` with **UseExisting** parameter, the **Credential** parameter is ignored.</span></span> <span data-ttu-id="d5c97-142">DSC では、既定のプロセス ID を使用して操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-142">DSC uses default process identity to proceed the operation.</span></span> <span data-ttu-id="d5c97-143">これにより、リモート ノードで処理を続行するために別の資格情報が必要になった場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-143">This causes error when a different credential is needed to proceed on remote node.</span></span>

<span data-ttu-id="d5c97-144">**解決策:** リモート DSC 操作に CIM セッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-144">**Resolution:** Use CIM session for remote DSC operations:</span></span>

```powershell
$session = New-CimSession -ComputerName $node -Credential $credential
Start-DscConfiguration -UseExisting -CimSession $session
```

## <a name="ipv6-addresses-as-node-names-in-dsc-configurations"></a><span data-ttu-id="d5c97-145">DSC 構成内のノード名としての IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="d5c97-145">IPv6 Addresses as Node Names in DSC configurations</span></span>

<span data-ttu-id="d5c97-146">DSC 構成スクリプトでのノード名としての IPv6 アドレスは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-146">IPv6 addresses as node names in DSC configuration scripts are not supported in this release.</span></span>

<span data-ttu-id="d5c97-147">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-147">**Resolution:** None.</span></span>

## <a name="debugging-of-class-based-dsc-resources"></a><span data-ttu-id="d5c97-148">`Class-Based` DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d5c97-148">Debugging of `Class-Based` DSC Resources</span></span>

<span data-ttu-id="d5c97-149">クラスベースの DSC リソースのデバッグは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-149">Debugging of class-based DSC Resources is not supported in this release.</span></span>

<span data-ttu-id="d5c97-150">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-150">**Resolution:** None.</span></span>

## <a name="variables-and-functions-defined-in-script-scope-in-dsc-class-based-resource-are-not-preserved-across-multiple-calls-to-a-dsc-resource"></a><span data-ttu-id="d5c97-151">DSC クラスベース リソースの $script スコープで定義された変数と関数が、DSC リソースへの複数の呼び出しで保持されない</span><span class="sxs-lookup"><span data-stu-id="d5c97-151">Variables and functions defined in $script scope in DSC Class-Based Resource are not preserved across multiple calls to a DSC Resource</span></span>

<span data-ttu-id="d5c97-152">変数または関数が `$script` スコープで定義されたクラスベース リソースが構成で使用されている場合、`Start-DSCConfiguration` への複数の連続した呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-152">Multiple consecutive calls to `Start-DSCConfiguration` fails if the configuration is using any class-based resource which has variables or functions defined in `$script` scope.</span></span>

<span data-ttu-id="d5c97-153">**解決策:** すべての変数と関数を DSC リソース クラス自体で定義します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-153">**Resolution:** Define all variables and functions in DSC Resource class itself.</span></span> <span data-ttu-id="d5c97-154">`$script` スコープの変数や関数を使用しません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-154">No `$script` scope variables/functions.</span></span>

## <a name="dsc-resource-debugging-when-a-resource-is-using-psdscrunascredential"></a><span data-ttu-id="d5c97-155">リソースが PSDscRunAsCredential を使用している場合の DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="d5c97-155">DSC Resource Debugging when a resource is using PSDscRunAsCredential</span></span>

<span data-ttu-id="d5c97-156">構成でリソースが **PSDscRunAsCredential** プロパティを使用している場合の DSC リソースのデバッグは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-156">DSC Resource debugging when a resource is using the **PSDscRunAsCredential** property in the configuration is not supported in this release.</span></span>

<span data-ttu-id="d5c97-157">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-157">**Resolution:** None.</span></span>

## <a name="psdscrunascredential-is-not-supported-for-dsc-composite-resources"></a><span data-ttu-id="d5c97-158">PsDscRunAsCredential が DSC 複合リソースでサポートされない</span><span class="sxs-lookup"><span data-stu-id="d5c97-158">PsDscRunAsCredential is not supported for DSC Composite Resources</span></span>

<span data-ttu-id="d5c97-159">**解決策:** 利用可能な場合は、資格情報プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-159">**Resolution:** Use Credential property if available.</span></span> <span data-ttu-id="d5c97-160">例 ServiceSet および WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="d5c97-160">Example ServiceSet and WindowsFeatureSet</span></span>

## <a name="get-dscresource--syntax-does-not-reflect-psdscrunascredential-correctly"></a><span data-ttu-id="d5c97-161">Get-DscResource -Syntax で PsDscRunAsCredential correctly が正しく反映されない</span><span class="sxs-lookup"><span data-stu-id="d5c97-161">Get-DscResource -Syntax does not reflect PsDscRunAsCredential correctly</span></span>

<span data-ttu-id="d5c97-162">リソースで必須とマークされていない場合、またはサポートされていない場合、**Syntax** パラメーターで **PsDscRunAsCredential** が正しく反映されません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-162">The **Syntax** parameter does not reflect **PsDscRunAsCredential** correctly when resource marks it as mandatory or does not support it.</span></span>

<span data-ttu-id="d5c97-163">**解決策:** [なし] :</span><span class="sxs-lookup"><span data-stu-id="d5c97-163">**Resolution:** None.</span></span> <span data-ttu-id="d5c97-164">ただし、ISE で構成を作成すると、IntelliSense の使用時に、**PsDscRunAsCredential** プロパティに関する正しいメタデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="d5c97-164">However, authoring configuration in ISE reflects correct metadata about **PsDscRunAsCredential** property when using IntelliSense.</span></span>

## <a name="windowsoptionalfeature-is-not-available-in-windows-7"></a><span data-ttu-id="d5c97-165">WindowsOptionalFeature を Windows 7 で使用できない</span><span class="sxs-lookup"><span data-stu-id="d5c97-165">WindowsOptionalFeature is not available in Windows 7</span></span>

<span data-ttu-id="d5c97-166">**WindowsOptionalFeature** DSC リソースは、Windows 7 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="d5c97-166">The **WindowsOptionalFeature** DSC resource is not available in Windows 7.</span></span> <span data-ttu-id="d5c97-167">このリソースには、Windows 8 以降のリリースの Windows オペレーティング システムで利用可能な DISM コマンドレット、および DISM モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="d5c97-167">This resource requires the DISM module, and DISM cmdlets that are available starting in Windows 8 and newer releases of the Windows operating system.</span></span>

## <a name="for-class-based-dsc-resources-import-dscresource--moduleversion-may-not-work-as-expected"></a><span data-ttu-id="d5c97-168">クラス ベースの DSC リソースでは、Import-DscResource -ModuleVersion が正常に動作しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5c97-168">For Class-based DSC resources, Import-DscResource -ModuleVersion may not work as expected</span></span>

<span data-ttu-id="d5c97-169">コンパイル ノードにクラス ベースの DSC リソース モジュールが複数ある場合、`Import-DscResource -ModuleVersion` から指定されたバージョンが取得されず、次のコンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-169">If the compilation node has multiple versions of a class-based DSC resource module, `Import-DscResource -ModuleVersion` does not pick the specified version and results in following compilation error.</span></span>

```Output
ImportClassResourcesFromModule : Exception calling "ImportClassResourcesFromModule" with "3" argument(s):
 "Keyword 'MyTestResource' already defined in the configuration."
At C:\Windows\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:2035 char:35
+ ... rcesFound = ImportClassResourcesFromModule -Module $mod -Resources $r ...
+                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [ImportClassResourcesFromModule], MethodInvocationException
    + FullyQualifiedErrorId : PSInvalidOperationException,ImportClassResourcesFromModule
```

<span data-ttu-id="d5c97-170">**解決策:** 次のように、**RequiredVersion** キーを指定して **ModuleName** パラメーターに **ModuleSpecification** オブジェクトを定義することで、必要なバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="d5c97-170">**Resolution:** Import the required version by defining the **ModuleSpecification** object to the **ModuleName** parameter with **RequiredVersion** key specified as follows:</span></span>

```powershell
Import-DscResource -ModuleName @{ModuleName='MyModuleName';RequiredVersion='1.2'}
```

## <a name="some-dsc-resources-like-registry-resource-may-start-to-take-a-long-time-to-process-the-request"></a><span data-ttu-id="d5c97-171">レジストリ リソースなどの一部の DSC リソースは、要求の処理に長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5c97-171">Some DSC resources like registry resource may start to take a long time to process the request.</span></span>

<span data-ttu-id="d5c97-172">**解決策 1:** 次のフォルダーを定期的にクリーンアップするタスクのスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-172">**Resolution 1:** Create a schedule task that cleans up the following folder periodically.</span></span>

```powershell
$env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis
```

<span data-ttu-id="d5c97-173">**解決策 2:** 構成の最後に *CommandAnalysis* フォルダーをクリーンアップするように DSC 構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="d5c97-173">**Resolution 2:** Change the DSC configuration to clean up the *CommandAnalysis* folder at the end of the configuration.</span></span>

```powershell
Configuration $configName
{

   # User Data
    Registry SetRegisteredOwner
    {
        Ensure = 'Present'
        Force = $True
        Key = $Node.RegisteredKey
        ValueName = $Node.RegisteredOwnerValue
        ValueType = 'String'
        ValueData = $Node.RegisteredOwnerData
    }
    #
    # Script to delete the config
    #
    script DeleteCommandAnalysisCache
    {
        DependsOn = "[Registry]SetRegisteredOwner"
        getscript = "@{}"
        testscript = 'Remove-Item -Path $env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis -Force -Recurse -ErrorAction SilentlyContinue -ErrorVariable ev | out-null;$true'
        setscript = '$true'
    }
}
```
