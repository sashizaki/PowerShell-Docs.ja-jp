---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC on Nano Server の使用
ms.openlocfilehash: fd81fe56d16100f45d9ee2dfd8fdc303c2a6c17a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402565"
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="17e4a-103">DSC on Nano Server の使用</span><span class="sxs-lookup"><span data-stu-id="17e4a-103">Using DSC on Nano Server</span></span>

> <span data-ttu-id="17e4a-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="17e4a-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="17e4a-105">**DSC on Nano Server** は、Windows Server 2016 メディアの `NanoServer\Packages` フォルダーに含まれるオプションのパッケージです。</span><span class="sxs-lookup"><span data-stu-id="17e4a-105">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="17e4a-106">このパッケージをインストールするには、Nano Server の VHD を作成するときに、**New-NanoServerImage** 関数の **Packages** パラメーターの値として **Microsoft-NanoServer-DSC-Package** を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e4a-106">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="17e4a-107">たとえば、仮想マシンの VHD を作成する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="17e4a-107">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="17e4a-108">Nano Server のインストールと使用、および PowerShell リモート処理による Nano Server の管理方法については、「[Getting Started with Nano Server (Nano Server の概要)](/windows-server/get-started/getting-started-with-nano-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e4a-108">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span></span>

## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="17e4a-109">Nano Server で使用できる DSC 機能</span><span class="sxs-lookup"><span data-stu-id="17e4a-109">DSC features available on Nano Server</span></span>

<span data-ttu-id="17e4a-110">Nano Server でサポートされる API のセットは、通常版の Windows Server と比べると限定的であるため、当面の間、DSC on Nano Server では、すべての SKU で DSC が動作する、完全に機能するパリティを利用できません。</span><span class="sxs-lookup"><span data-stu-id="17e4a-110">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="17e4a-111">DSC on Nano Server は現在開発中であり、まだ完全な機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="17e4a-111">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

<span data-ttu-id="17e4a-112">現在、Nano Server で使用できる DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17e4a-112">The following DSC features are currently available on Nano Server:</span></span>

<span data-ttu-id="17e4a-113">プッシュ モードとプル モード</span><span class="sxs-lookup"><span data-stu-id="17e4a-113">Both push and pull modes</span></span>

- <span data-ttu-id="17e4a-114">以下を含む、通常版の Windows Server に存在するすべての DSC コマンドレット</span><span class="sxs-lookup"><span data-stu-id="17e4a-114">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
- [<span data-ttu-id="17e4a-115">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="17e4a-115">Get-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [<span data-ttu-id="17e4a-116">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="17e4a-116">Set-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [<span data-ttu-id="17e4a-117">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="17e4a-117">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [<span data-ttu-id="17e4a-118">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="17e4a-118">Disable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [<span data-ttu-id="17e4a-119">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-119">Start-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [<span data-ttu-id="17e4a-120">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-120">Stop-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [<span data-ttu-id="17e4a-121">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-121">Get-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [<span data-ttu-id="17e4a-122">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-122">Test-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [<span data-ttu-id="17e4a-123">Publish-DscConfiguraiton</span><span class="sxs-lookup"><span data-stu-id="17e4a-123">Publish-DscConfiguraiton</span></span>](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [<span data-ttu-id="17e4a-124">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-124">Update-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [<span data-ttu-id="17e4a-125">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="17e4a-125">Restore-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [<span data-ttu-id="17e4a-126">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="17e4a-126">Remove-DscConfigurationDocument</span></span>](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [<span data-ttu-id="17e4a-127">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="17e4a-127">Get-DscConfigurationStatus</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [<span data-ttu-id="17e4a-128">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="17e4a-128">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [<span data-ttu-id="17e4a-129">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="17e4a-129">Find-DscResource</span></span>](https://technet.microsoft.com/en-us/library/mt517874.aspx)
- [<span data-ttu-id="17e4a-130">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="17e4a-130">Get-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [<span data-ttu-id="17e4a-131">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="17e4a-131">New-DscChecksum</span></span>](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- <span data-ttu-id="17e4a-132">構成のコンパイル (「[DSC 構成](../configurations/configurations.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-132">Compiling configurations (see [DSC configurations](../configurations/configurations.md))</span></span>

  <span data-ttu-id="17e4a-133">**問題 #1629**パスワードの暗号化 (を参照してください[MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)) の構成時にコンパイルは機能しません。</span><span class="sxs-lookup"><span data-stu-id="17e4a-133">**Issue:** Password encryption (see [Securing the MOF File](../pull-server/secureMOF.md)) during configuration compilation doesn't work.</span></span>

- <span data-ttu-id="17e4a-134">メタ構成のコンパイル (「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-134">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md))</span></span>

- <span data-ttu-id="17e4a-135">ユーザー コンテキストでのリソースの実行 ([ユーザーの資格情報を指定した DSC の実行 (RunAs)](../configurations/runAsUser.md) に関するページを参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-135">Running a resource under user context (see [Running DSC with user credentials (RunAs)](../configurations/runAsUser.md))</span></span>

- <span data-ttu-id="17e4a-136">クラスベースのリソース (「[PowerShell クラスを使用したカスタム DSC リソースの記述](../resources/authoringResourceClass.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-136">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](../resources/authoringResourceClass.md))</span></span>

- <span data-ttu-id="17e4a-137">DSC リソースのデバッグ (「[DSC リソースのデバッグ](../troubleshooting/debugResource.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-137">Debugging of DSC resources (see [Debugging DSC resources](../troubleshooting/debugResource.md))</span></span>

  <span data-ttu-id="17e4a-138">**問題 #1629**リソースが PsDscRunAsCredential を使用する場合は機能しません (を参照してください[ユーザー資格情報で実行されている DSC](../configurations/runAsUser.md))</span><span class="sxs-lookup"><span data-stu-id="17e4a-138">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](../configurations/runAsUser.md))</span></span>

- [<span data-ttu-id="17e4a-139">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="17e4a-139">Specifying cross-node dependencies</span></span>](../configurations/crossNodeDependencies.md)

- [<span data-ttu-id="17e4a-140">リソースのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="17e4a-140">Resource versioning</span></span>](../configurations/sxsResource.md)

- <span data-ttu-id="17e4a-141">プル クライアント (構成とリソース) (「[構成名を使用したプル クライアントのセットアップ](../pull-server/pullClientConfigNames.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-141">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](../pull-server/pullClientConfigNames.md))</span></span>

- [<span data-ttu-id="17e4a-142">部分構成 (プルとプッシュ)</span><span class="sxs-lookup"><span data-stu-id="17e4a-142">Partial configurations (pull & push)</span></span>](../pull-server/partialConfigs.md)

- [<span data-ttu-id="17e4a-143">プル サーバーへの報告</span><span class="sxs-lookup"><span data-stu-id="17e4a-143">Reporting to pull server</span></span>](../pull-server/reportServer.md)

- <span data-ttu-id="17e4a-144">MOF 暗号化</span><span class="sxs-lookup"><span data-stu-id="17e4a-144">MOF encryption</span></span>

- <span data-ttu-id="17e4a-145">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="17e4a-145">Event logging</span></span>

- <span data-ttu-id="17e4a-146">Azure Automation DSC レポート</span><span class="sxs-lookup"><span data-stu-id="17e4a-146">Azure Automation DSC reporting</span></span>

- <span data-ttu-id="17e4a-147">完全に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="17e4a-147">Resources that are fully functional</span></span>

- <span data-ttu-id="17e4a-148">**Archive**</span><span class="sxs-lookup"><span data-stu-id="17e4a-148">**Archive**</span></span>
- <span data-ttu-id="17e4a-149">**Environment**</span><span class="sxs-lookup"><span data-stu-id="17e4a-149">**Environment**</span></span>
- <span data-ttu-id="17e4a-150">**File**</span><span class="sxs-lookup"><span data-stu-id="17e4a-150">**File**</span></span>
- <span data-ttu-id="17e4a-151">**Log**</span><span class="sxs-lookup"><span data-stu-id="17e4a-151">**Log**</span></span>
- <span data-ttu-id="17e4a-152">**ProcessSet**</span><span class="sxs-lookup"><span data-stu-id="17e4a-152">**ProcessSet**</span></span>
- <span data-ttu-id="17e4a-153">**Registry**</span><span class="sxs-lookup"><span data-stu-id="17e4a-153">**Registry**</span></span>
- <span data-ttu-id="17e4a-154">**Script**</span><span class="sxs-lookup"><span data-stu-id="17e4a-154">**Script**</span></span>
- <span data-ttu-id="17e4a-155">**WindowsPackageCab**</span><span class="sxs-lookup"><span data-stu-id="17e4a-155">**WindowsPackageCab**</span></span>
- <span data-ttu-id="17e4a-156">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="17e4a-156">**WindowsProcess**</span></span>
- <span data-ttu-id="17e4a-157">**WaitForAll** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-157">**WaitForAll** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
- <span data-ttu-id="17e4a-158">**WaitForAny** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-158">**WaitForAny** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
- <span data-ttu-id="17e4a-159">**WaitForSome** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="17e4a-159">**WaitForSome** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>

- <span data-ttu-id="17e4a-160">部分的に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="17e4a-160">Resources that are partially functional</span></span>
- <span data-ttu-id="17e4a-161">**グループ**</span><span class="sxs-lookup"><span data-stu-id="17e4a-161">**Group**</span></span>
- <span data-ttu-id="17e4a-162">**GroupSet**</span><span class="sxs-lookup"><span data-stu-id="17e4a-162">**GroupSet**</span></span>

  <span data-ttu-id="17e4a-163">**問題 #1629**上記のリソースの失敗特定のインスタンスが 2 回呼び出された場合 (同じ構成を 2 回の実行)</span><span class="sxs-lookup"><span data-stu-id="17e4a-163">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

- <span data-ttu-id="17e4a-164">**Service**</span><span class="sxs-lookup"><span data-stu-id="17e4a-164">**Service**</span></span>
- <span data-ttu-id="17e4a-165">**ServiceSet**</span><span class="sxs-lookup"><span data-stu-id="17e4a-165">**ServiceSet**</span></span>

  <span data-ttu-id="17e4a-166">**問題 #1629**専用のサービス (状態) の開始/停止します。</span><span class="sxs-lookup"><span data-stu-id="17e4a-166">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="17e4a-167">StartupType、資格情報、説明などのほかのサービス属性を変更しようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="17e4a-167">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="17e4a-168">次のようなエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="17e4a-168">The error thrown is similar to:</span></span>

  <span data-ttu-id="17e4a-169">*型 [management.managementobject] が見つかりません。この型を含むアセンブリが読み込まれていることを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="17e4a-169">*Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.*</span></span>

- <span data-ttu-id="17e4a-170">機能しないリソース</span><span class="sxs-lookup"><span data-stu-id="17e4a-170">Resources that are not functional</span></span>
- <span data-ttu-id="17e4a-171">**User**</span><span class="sxs-lookup"><span data-stu-id="17e4a-171">**User**</span></span>

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="17e4a-172">Nano Server で使用できない DSC 機能</span><span class="sxs-lookup"><span data-stu-id="17e4a-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="17e4a-173">現在、Nano Server で使用できない DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="17e4a-173">The following DSC features are not currently available on Nano Server:</span></span>

- <span data-ttu-id="17e4a-174">暗号化パスワードを使用した MOF ドキュメントの暗号化解除</span><span class="sxs-lookup"><span data-stu-id="17e4a-174">Decrypting MOF document with encrypted password(s)</span></span>
- <span data-ttu-id="17e4a-175">プル サーバー - 現在、Nano Server でプル サーバーをセットアップすることはできません</span><span class="sxs-lookup"><span data-stu-id="17e4a-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
- <span data-ttu-id="17e4a-176">動作する機能の一覧に含まれていないもの</span><span class="sxs-lookup"><span data-stu-id="17e4a-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="17e4a-177">Nano Server でのカスタム DSC リソースの使用</span><span class="sxs-lookup"><span data-stu-id="17e4a-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="17e4a-178">Nano Server で使用できる Windows API と CLR ライブラリは限定されているため、完全な CLR バージョンの Windows で動作する DSC は、必ずしも Nano Server で動作するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="17e4a-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="17e4a-179">DSC カスタム リソースを運用環境に展開する前に、エンド ツー エンドのテストを完了してください。</span><span class="sxs-lookup"><span data-stu-id="17e4a-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="17e4a-180">参照</span><span class="sxs-lookup"><span data-stu-id="17e4a-180">See Also</span></span>

- [<span data-ttu-id="17e4a-181">Nano Server の概要</span><span class="sxs-lookup"><span data-stu-id="17e4a-181">Getting Started with Nano Server</span></span>](/windows-server/get-started/getting-started-with-nano-server)