---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 66ceea383b78b2654caa4f1de16a30beea0e7fd3
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="desired-state-configuration-dsc-known-issues-and-limitations"></a><span data-ttu-id="4978a-102">Desired State Configuration (DSC) の既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="4978a-102">Desired State Configuration (DSC) Known Issues and Limitations</span></span>

<a name="breaking-change-certificates-used-to-encryptdecrypt-passwords-in-dsc-configurations-may-not-work-after-installing-wmf-50-rtm"></a><span data-ttu-id="4978a-103">重要な変更: WMF 5.0 RTM をインストールした後、DSC 構成でパスワードの暗号化/暗号化の解除に使用される証明書が機能しない場合がある</span><span class="sxs-lookup"><span data-stu-id="4978a-103">Breaking Change: Certificates used to encrypt/decrypt passwords in DSC configurations may not work after installing WMF 5.0 RTM</span></span>
--------------------------------------------------------------------------------------------------------------------------------

<span data-ttu-id="4978a-104">WMF 4.0 および WMF 5.0 Preview リリースでは、DSC の構成内で 121 文字を超える長さのパスワードを使用できません。</span><span class="sxs-lookup"><span data-stu-id="4978a-104">In WMF 4.0 and WMF 5.0 Preview releases, DSC would not allow passwords in the configuration to be of length more than 121 characters.</span></span> <span data-ttu-id="4978a-105">DSC では、長い強力なパスワードが必要な場合でも、短いパスワードを使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="4978a-105">DSC was forcing to use short passwords even if lengthy and strong password was desired.</span></span> <span data-ttu-id="4978a-106">この重要な変更により、DSC 構成で任意の長さのパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4978a-106">This breaking change allows passwords to be of arbitrary length in the DSC configuration.</span></span>

<span data-ttu-id="4978a-107">**解決策:** データの暗号化またはキーの暗号化のキーの使用法と、ドキュメントの暗号化拡張キー使用法 (1.3.6.1.4.1.311.80.1) を含む証明書を再作成します。</span><span class="sxs-lookup"><span data-stu-id="4978a-107">**Resolution:** Re-create the certificate with Data Encipherment or Key Encipherment Key usage, and Document Encryption Enhanced Key usage (1.3.6.1.4.1.311.80.1).</span></span> <span data-ttu-id="4978a-108">Technet の記事 <https://technet.microsoft.com/library/dn807171.aspx> に詳しい説明があります。</span><span class="sxs-lookup"><span data-stu-id="4978a-108">Technet article <https://technet.microsoft.com/library/dn807171.aspx> has more information.</span></span>


<a name="dsc-cmdlets-may-fail-after-installing-wmf-50-rtm"></a><span data-ttu-id="4978a-109">WMF 5.0 RTM をインストールした後、DSC のコマンドレットが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="4978a-109">DSC cmdlets may fail after installing WMF 5.0 RTM</span></span>
------------------------------------------------------------------------------------
<span data-ttu-id="4978a-110">WMF 5.0 RTM をインストールした後、Start-DscConfiguration および他の DSC コマンドレットが次のエラーで失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="4978a-110">Start-DscConfiguration and other DSC cmdlets may fail after installing WMF 5.0 RTM with the following error:</span></span>
```powershell
    LCM failed to retrieve the property PendingJobStep from the object of class dscInternalCache .
    + CategoryInfo : ObjectNotFound: (root/Microsoft/...gurationManager:String) [], CimException
    + FullyQualifiedErrorId : MI RESULT 6
    + PSComputerName : localhost
```

<span data-ttu-id="4978a-111">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して DSCEngineCache.mof を削除します。</span><span class="sxs-lookup"><span data-stu-id="4978a-111">**Resolution:** Delete DSCEngineCache.mof by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Remove-Item -Path $env:SystemRoot\system32\Configuration\DSCEngineCache.mof
```


<a name="dsc-cmdlets-may-not-work-if-wmf-50-rtm-is-installed-on-top-of-wmf-50-production-preview"></a><span data-ttu-id="4978a-112">WMF 5.0 RTM を WMF 5.0 Production Preview の上にインストールした場合、DSC コマンドレットが機能しない場合がある。</span><span class="sxs-lookup"><span data-stu-id="4978a-112">DSC cmdlets may not work if WMF 5.0 RTM is installed on top of WMF 5.0 Production Preview</span></span>
------------------------------------------------------
<span data-ttu-id="4978a-113">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4978a-113">**Resolution:** Run the following command in an elevated PowerShell session (run as administrator):</span></span>
```powershell
    mofcomp $env:windir\system32\wbem\DscCoreConfProv.mof
```


<a name="lcm-can-go-into-an-unstable-state-while-using-get-dscconfiguration-in-debugmode"></a><span data-ttu-id="4978a-114">Get-DscConfiguration を DebugMode で使用しているときに LCM が不安定な状態になることがある</span><span class="sxs-lookup"><span data-stu-id="4978a-114">LCM can go into an unstable state while using Get-DscConfiguration in DebugMode</span></span>
-------------------------------------------------------------------------------

<span data-ttu-id="4978a-115">LCM が DebugMode の場合、CTRL + C キーを押して Get-DscConfiguration の処理を停止すると、DSC コマンドレットの大部分が機能しないような不安定な状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="4978a-115">If LCM is in DebugMode, pressing CTRL+C to stop the processing of Get-DscConfiguration can cause LCM to go into an unstable state such that majority of DSC cmdlets won’t work.</span></span>

<span data-ttu-id="4978a-116">**解決策:** Get-DscConfiguration コマンドレットのデバッグ中に CTRL + C キーを押さないようにします。</span><span class="sxs-lookup"><span data-stu-id="4978a-116">**Resolution:** Don’t press CTRL+C while debugging Get-DscConfiguration cmdlet.</span></span>


<a name="stop-dscconfiguration-may-hang-in-debugmode"></a><span data-ttu-id="4978a-117">Stop-DscConfiguration が DebugMode でハングすることがある</span><span class="sxs-lookup"><span data-stu-id="4978a-117">Stop-DscConfiguration may hang in DebugMode</span></span>
------------------------------------------------------------------------------------------------------------------------
<span data-ttu-id="4978a-118">LCM が DebugMode の場合、Get-DscConfiguration で開始された操作を停止しようとすると Stop-DscConfiguration がハングする場合があります。</span><span class="sxs-lookup"><span data-stu-id="4978a-118">If LCM is in DebugMode, Stop-DscConfiguration may hang while trying to stop an operation started by Get-DscConfiguration</span></span>

<span data-ttu-id="4978a-119">**解決策:** Get-DscConfiguration で開始された操作のデバッグを「[DSC リソースのデバッグ](https://msdn.microsoft.com/powershell/dsc/debugresource)」セクションの説明に従って終了します。</span><span class="sxs-lookup"><span data-stu-id="4978a-119">**Resolution:** Finish the debugging of the operation started by Get-DscConfiguration as outlined in section ‘[Debugging DSC resources](https://msdn.microsoft.com/powershell/dsc/debugresource)’.</span></span>


<a name="no-verbose-error-messages-are-shown-in-debugmode"></a><span data-ttu-id="4978a-120">DebugMode で詳細なエラー メッセージが表示されない</span><span class="sxs-lookup"><span data-stu-id="4978a-120">No Verbose Error Messages are shown in DebugMode</span></span>
-----------------------------------------------------------------------------------
<span data-ttu-id="4978a-121">LCM が DebugMode の場合は、DSC リソースから詳細なエラー メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="4978a-121">If LCM is in DebugMode, no verbose error messages are displayed from DSC Resources.</span></span>

<span data-ttu-id="4978a-122">**解決策:** リソースからの詳細なメッセージを表示するには、*DebugMode* を無効にします。</span><span class="sxs-lookup"><span data-stu-id="4978a-122">**Resolution:** Disable *DebugMode* to see verbose messages from the resource</span></span>


<a name="invoke-dscresource-operations-cannot-be-retrieved-by-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="4978a-123">Get-DscConfigurationStatus コマンドレットで Invoke-DscResource 操作を取得できない</span><span class="sxs-lookup"><span data-stu-id="4978a-123">Invoke-DscResource operations cannot be retrieved by Get-DscConfigurationStatus cmdlet</span></span>
--------------------------------------------------------------------------------------
<span data-ttu-id="4978a-124">Invoke-DscResource コマンドレットを使用してリソースのメソッドを直接呼び出した後、このような操作のレコードを Get-DscConfigurationStatus によって取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="4978a-124">After using Invoke-DscResource cmdlet to directly invoke any resource’s methods, the records of such operation cannot be retrieved through Get-DscConfigurationStatus at a later time.</span></span>

<span data-ttu-id="4978a-125">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-125">**Resolution:** None.</span></span>


<a name="get-dscconfigurationstatus-returns-pull-cycle-operations-as-type-consistency"></a><span data-ttu-id="4978a-126">Get-DscConfigurationStatus でプル サイクル操作がタイプ *Consistency* として返される</span><span class="sxs-lookup"><span data-stu-id="4978a-126">Get-DscConfigurationStatus returns pull cycle operations as type *Consistency*</span></span>
---------------------------------------------------------------------------------
<span data-ttu-id="4978a-127">ノードがプル更新モードに設定されている場合、プル操作を実行するたびに、Get-DscConfigurationStatus コマンドレットで操作のタイプが *Initial* ではなく *Consistency* としてレポートされます。</span><span class="sxs-lookup"><span data-stu-id="4978a-127">When a node is set to PULL refresh mode, for each pull operation performed, Get-DscConfigurationStatus cmdlet reports the operation type as *Consistency* instead of *Initial*</span></span>

<span data-ttu-id="4978a-128">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-128">**Resolution:** None.</span></span>

<a name="invoke-dscresource-cmdlet-does-not-return-message-in-the-order-they-were-produced"></a><span data-ttu-id="4978a-129">Invoke-DscResource コマンドレットで、メッセージが生成された順序で返されない</span><span class="sxs-lookup"><span data-stu-id="4978a-129">Invoke-DscResource cmdlet does not return message in the order they were produced</span></span>
---------------------------------------------------------------------------------
<span data-ttu-id="4978a-130">Invoke-DscResource コマンドレットでは、詳細、警告、およびエラー メッセージは LCM または DSC リソースによって生成された順序で返されません。</span><span class="sxs-lookup"><span data-stu-id="4978a-130">The Invoke-DscResource cmdlet does not return verbose, warning, and error messages in the order they were produced by LCM or the DSC resource.</span></span>

<span data-ttu-id="4978a-131">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-131">**Resolution:** None.</span></span>


<a name="dsc-resources-cannot-be-debugged-easily-when-used-with-invoke-dscresource"></a><span data-ttu-id="4978a-132">Invoke-DscResource と共に使用すると、DSC リソースを簡単にデバッグできない</span><span class="sxs-lookup"><span data-stu-id="4978a-132">DSC Resources cannot be debugged easily when used with Invoke-DscResource</span></span>
-----------------------------------------------------------------------
<span data-ttu-id="4978a-133">LCM がデバッグ モードで実行されている場合 (詳細については「[DSC リソースのデバッグ](https://msdn.microsoft.com/powershell/dsc/debugresource)」を参照)、Invoke-DscResource コマンドレットはデバッグ用に接続する実行空間に関する情報を提供しません。</span><span class="sxs-lookup"><span data-stu-id="4978a-133">When LCM is running in debug mode (see [Debugging DSC resources](https://msdn.microsoft.com/powershell/dsc/debugresource) for more details), Invoke-DscResource cmdlet does not give information about runspace to connect to for debugging.</span></span>
<span data-ttu-id="4978a-134">**解決策:** **Get-PSHostProcessInfo**、**Enter-PSHostProcess**、**Get-Runspace**、および **Debug-Runspace** コマンドレットを使用して実行空間を検出して接続し、DSC リソースをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="4978a-134">**Resolution:** Discover and attach to the runspace using cmdlets **Get-PSHostProcessInfo**, **Enter-PSHostProcess** , **Get-Runspace** and **Debug-Runspace** to debug the DSC resource.</span></span>

```powershell
# Find all the processes hosting PowerShell
Get-PSHostProcessInfo

ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell 3932 DefaultAppDomain
powershell_ise 2304 DefaultAppDomain
WmiPrvSE 3396 DscPsPluginWkr_AppDomain

# Enter the process that is hosting DSC engine (WMI process with DscPsPluginWkr_Appdomain)
Enter-PSHostProcess -Id 3396 -AppDomainName DscPsPluginWkr_AppDomain

# Find all the available rusnspaces in that process
Get-Runspace

Id Name ComputerName Type State Availability
-- ---- ------------ ---- ----- ------------
2 Runspace2 localhost Local Opened InBreakpoint
5 RemoteHost localhost Local Opened Busy

# Debug the runspace that is in **InBreakpoint** availability state
Debug-Runspace -Id 2
```


<a name="various-partial-configuration-documents-for-same-node-cannot-have-identical-resource-names"></a><span data-ttu-id="4978a-135">同じノードのさまざまな部分構成ドキュメントが同じリソース名を持つことができない</span><span class="sxs-lookup"><span data-stu-id="4978a-135">Various Partial Configuration documents for same node cannot have identical resource names</span></span>
------------------------------------------------------------------------------------------

<span data-ttu-id="4978a-136">1 つのノード上に展開される複数の部分構成では、リソース名が同一であることが実行時エラーの原因となります。</span><span class="sxs-lookup"><span data-stu-id="4978a-136">For several partial configurations that are deployed onto a single node, identical names of resources cause run time error.</span></span>

<span data-ttu-id="4978a-137">**解決策:** 異なる部分構成では、同じリソースでも異なる名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="4978a-137">**Resolution:** Use different names for even same resources in different partial configurations.</span></span>


<a name="start-dscconfiguration-useexisting-does-not-work-with--credential"></a><span data-ttu-id="4978a-138">Start-DscConfiguration -UseExisting が -Credential で機能しない</span><span class="sxs-lookup"><span data-stu-id="4978a-138">Start-DscConfiguration –UseExisting does not work with -Credential</span></span>
------------------------------------------------------------------

<span data-ttu-id="4978a-139">Start-DscConfiguration を -UseExisting パラメーターと共に使用すると、-Credential パラメーターが無視されます。</span><span class="sxs-lookup"><span data-stu-id="4978a-139">When using Start-DscConfiguration with –UseExisting parameter, the –Credential parameter is ignored.</span></span> <span data-ttu-id="4978a-140">DSC では、既定のプロセス ID を使用して操作を続行します。</span><span class="sxs-lookup"><span data-stu-id="4978a-140">DSC uses default process identity to proceed the operation.</span></span> <span data-ttu-id="4978a-141">これにより、リモート ノードで処理を続行するために別の資格情報が必要になった場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4978a-141">This causes error when a different credential is needed to proceed on remote node.</span></span>

<span data-ttu-id="4978a-142">**解決策:** リモート DSC 操作に CIM セッションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4978a-142">**Resolution:** Use CIM session for remote DSC operations:</span></span>
```powershell
$session = New-CimSession -ComputerName $node -Credential $credential
Start-DscConfiguration -UseExisting -CimSession $session
```


<a name="ipv6-addresses-as-node-names-in-dsc-configurations"></a><span data-ttu-id="4978a-143">DSC 構成内のノード名としての IPv6 アドレス</span><span class="sxs-lookup"><span data-stu-id="4978a-143">IPv6 Addresses as Node Names in DSC configurations</span></span>
--------------------------------------------------
<span data-ttu-id="4978a-144">DSC 構成スクリプトでのノード名としての IPv6 アドレスは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4978a-144">IPv6 addresses as node names in DSC configuration scripts are not supported in this release.</span></span>

<span data-ttu-id="4978a-145">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-145">**Resolution:** None.</span></span>


<a name="debugging-of-class-based-dsc-resources"></a><span data-ttu-id="4978a-146">クラスベースの DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="4978a-146">Debugging of Class-Based DSC Resources</span></span>
--------------------------------------
<span data-ttu-id="4978a-147">クラスベースの DSC リソースのデバッグは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4978a-147">Debugging of class-based DSC Resources is not supported in this release.</span></span>

<span data-ttu-id="4978a-148">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-148">**Resolution:** None.</span></span>


<a name="variables--functions-defined-in-script-scope-in-dsc-class-based-resource-are-not-preserved-across-multiple-calls-to-a-dsc-resource"></a><span data-ttu-id="4978a-149">DSC クラスベース リソースの $script スコープで定義された変数と関数が、DSC リソースへの複数の呼び出しで保持されない</span><span class="sxs-lookup"><span data-stu-id="4978a-149">Variables & Functions defined in $script scope in DSC Class-Based Resource are not preserved across multiple calls to a DSC Resource</span></span>
-------------------------------------------------------------------------------------------------------------------------------------

<span data-ttu-id="4978a-150">変数または関数が $script スコープで定義されたクラスベース リソースが構成で使用されている場合、Start-DSCConfiguration への複数の連続した呼び出しは失敗します。</span><span class="sxs-lookup"><span data-stu-id="4978a-150">Multiple consecutive calls to Start-DSCConfiguration will fail if configuration is using any class-based resource which has variables or functions defined in $script scope.</span></span>

<span data-ttu-id="4978a-151">**解決策:** すべての変数と関数を DSC リソース クラス自体で定義します。</span><span class="sxs-lookup"><span data-stu-id="4978a-151">**Resolution:** Define all variables and functions in DSC Resource class itself.</span></span> <span data-ttu-id="4978a-152">$script スコープの変数や関数を使用しません。</span><span class="sxs-lookup"><span data-stu-id="4978a-152">No $script scope variables/functions.</span></span>


<a name="dsc-resource-debugging-when-a-resource-is-using-psdscrunascredential"></a><span data-ttu-id="4978a-153">リソースが PSDscRunAsCredential を使用している場合の DSC リソースのデバッグ</span><span class="sxs-lookup"><span data-stu-id="4978a-153">DSC Resource Debugging when a resource is using PSDscRunAsCredential</span></span>
----------------------------------------------------------------------
<span data-ttu-id="4978a-154">構成でリソースが *PSDscRunAsCredential* プロパティを使用している場合の DSC リソースのデバッグは、このリリースではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4978a-154">DSC Resource debugging when a resource is using the *PSDscRunAsCredential* property in the configuration is not suported in this release.</span></span>

<span data-ttu-id="4978a-155">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-155">**Resolution:** None.</span></span>


<a name="psdscrunascredential-is-not-supported-for-dsc-composite-resources"></a><span data-ttu-id="4978a-156">PsDscRunAsCredential が DSC 複合リソースでサポートされない</span><span class="sxs-lookup"><span data-stu-id="4978a-156">PsDscRunAsCredential is not supported for DSC Composite Resources</span></span>
----------------------------------------------------------------

<span data-ttu-id="4978a-157">**解決策:** 利用可能な場合は、資格情報プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="4978a-157">**Resolution:** Use Credential property if available.</span></span> <span data-ttu-id="4978a-158">例 ServiceSet および WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="4978a-158">Example ServiceSet and WindowsFeatureSet</span></span>


<a name="get-dscresource--syntax-does-not-reflect-psdscrunascredential-correctly"></a><span data-ttu-id="4978a-159">*Get-DscResource -Syntax* が PsDscRunAsCredential correctly を正しく反映しない</span><span class="sxs-lookup"><span data-stu-id="4978a-159">*Get-DscResource -Syntax* does not reflect PsDscRunAsCredential correctly</span></span>
-------------------------------------------------------------------------
<span data-ttu-id="4978a-160">リソースで必須とマークされていない場合、またはサポートされていない場合、Get-DscResource -Syntax は PsDscRunAsCredential を正しく反映しません。</span><span class="sxs-lookup"><span data-stu-id="4978a-160">Get-DscResource -Syntax does not reflect PsDscRunAsCredential correctly when resource marks it as mandatory or does not support it.</span></span>

<span data-ttu-id="4978a-161">**解決策:** なし。</span><span class="sxs-lookup"><span data-stu-id="4978a-161">**Resolution:** None.</span></span> <span data-ttu-id="4978a-162">ただし、ISE で構成を作成すると、IntelliSense の使用時に、PsDscRunAsCredential プロパティに関する正しいメタデータが反映されます。</span><span class="sxs-lookup"><span data-stu-id="4978a-162">However, authoring configuration in ISE reflects correct metadata about PsDscRunAsCredential property when using IntelliSense.</span></span>


<a name="windowsoptionalfeature-is-not-available-in-windows-7"></a><span data-ttu-id="4978a-163">WindowsOptionalFeature を Windows 7 で使用できない</span><span class="sxs-lookup"><span data-stu-id="4978a-163">WindowsOptionalFeature is not available in Windows 7</span></span>
-----------------------------------------------------

<span data-ttu-id="4978a-164">WindowsOptionalFeature DSC リソースは、Windows 7 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="4978a-164">The WindowsOptionalFeature DSC resource is not available in Windows 7.</span></span> <span data-ttu-id="4978a-165">このリソースには、Windows 8 以降のリリースの Windows オペレーティング システムで利用可能な DISM コマンドレット、および DISM モジュールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4978a-165">This resource requires the DISM module, and DISM cmdlets that are available starting in Windows 8 and newer releases of the Windows operating system.</span></span>

<a name="for-class-based-dsc-resources-import-dscresource--moduleversion-may-not-work-as-expected"></a><span data-ttu-id="4978a-166">クラス ベースの DSC リソースでは、Import-DscResource -ModuleVersion が正常に動作しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4978a-166">For Class-based DSC resources, Import-DscResource -ModuleVersion may not work as expected</span></span>
------------------------------------------------------------------------------------------
<span data-ttu-id="4978a-167">コンパイル ノードにクラス ベースの DSC リソース モジュールが複数ある場合、`Import-DscResource -ModuleVersion` から指定されたバージョンが取得されず、次のコンパイル エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4978a-167">If the compilation node has multiple version of a class-based DSC resource module, `Import-DscResource -ModuleVersion` does not pick the specified version and results in following compilation error.</span></span>

```
ImportClassResourcesFromModule : Exception calling "ImportClassResourcesFromModule" with "3" argument(s): "Keyword 'MyTestResource' already defined in the configuration."
At C:\Windows\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:2035 char:35
+ ... rcesFound = ImportClassResourcesFromModule -Module $mod -Resources $r ...
+                 ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [ImportClassResourcesFromModule], MethodInvocationException
    + FullyQualifiedErrorId : PSInvalidOperationException,ImportClassResourcesFromModule
```

<span data-ttu-id="4978a-168">**解決策:** 次のように `RequiredVersion` キーを指定して `-ModuleName` に *ModuleSpecification* オブジェクトを定義することで、必要なバージョンをインポートします。</span><span class="sxs-lookup"><span data-stu-id="4978a-168">**Resolution:** Import the required version by defining the *ModuleSpecification* object to the `-ModuleName` with `RequiredVersion` key specified as follows:</span></span>
``` PowerShell
Import-DscResource -ModuleName @{ModuleName='MyModuleName';RequiredVersion='1.2'}
```

<a name="some-dsc-resources-like-registry-resource-may-start-to-take-a-long-time-to-process-the-request"></a><span data-ttu-id="4978a-169">レジストリ リソースなどの一部の DSC リソースは、要求の処理に長い時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="4978a-169">Some DSC resources like registry resource may start to take a long time to process the request.</span></span>
--------------------------------------------------------------------------------------------------------------------------------

<span data-ttu-id="4978a-170">**解決方法 1:** 次のフォルダーを定期的にクリーンアップするタスクのスケジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="4978a-170">**Resolution1:** Create a schedule task that cleans up the following folder periodically.</span></span>
``` PowerShell
$env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis
```

<span data-ttu-id="4978a-171">**解決方法 2:** 構成の最後に *CommandAnalysis* フォルダーをクリーンアップするように DSC 構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="4978a-171">**Resolution2:** Change the DSC configuration to clean up the *CommandAnalysis* folder at the end of the configuration.</span></span>
``` PowerShell
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
        DependsOn="[Registry]SetRegisteredOwner"
        getscript="@{}"
        testscript = 'Remove-Item -Path $env:windir\system32\config\systemprofile\AppData\Local\Microsoft\Windows\PowerShell\CommandAnalysis -Force -Recurse -ErrorAction SilentlyContinue -ErrorVariable ev | out-null;$true'
        setscript = '$true'
    }
}
```