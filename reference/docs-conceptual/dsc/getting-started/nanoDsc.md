---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC on Nano Server の使用
description: DSC は、Windows Nano Server 用の VHD を作成するときにインストールできる、オプションのパッケージです。
ms.openlocfilehash: 18585323359abd85515d4db194dae4adbad7c3d8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92647079"
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="8dea0-104">DSC on Nano Server の使用</span><span class="sxs-lookup"><span data-stu-id="8dea0-104">Using DSC on Nano Server</span></span>

> <span data-ttu-id="8dea0-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8dea0-105">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="8dea0-106">**DSC on Nano Server** は、Windows Server 2016 メディアの `NanoServer\Packages` フォルダーに含まれるオプションのパッケージです。</span><span class="sxs-lookup"><span data-stu-id="8dea0-106">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="8dea0-107">このパッケージをインストールするには、Nano Server の VHD を作成するときに、 **New-NanoServerImage** 関数の **Packages** パラメーターの値として **Microsoft-NanoServer-DSC-Package** を指定します。</span><span class="sxs-lookup"><span data-stu-id="8dea0-107">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="8dea0-108">たとえば、仮想マシンの VHD を作成する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8dea0-108">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="8dea0-109">Nano Server のインストールと使用、および PowerShell リモート処理による Nano Server の管理方法については、「[Getting Started with Nano Server (Nano Server の概要)](/windows-server/get-started/getting-started-with-nano-server)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8dea0-109">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](/windows-server/get-started/getting-started-with-nano-server).</span></span>

## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="8dea0-110">Nano Server で使用できる DSC 機能</span><span class="sxs-lookup"><span data-stu-id="8dea0-110">DSC features available on Nano Server</span></span>

<span data-ttu-id="8dea0-111">Nano Server でサポートされる API のセットは、通常版の Windows Server と比べると限定的であるため、当面の間、DSC on Nano Server では、すべての SKU で DSC が動作する、完全に機能するパリティを利用できません。</span><span class="sxs-lookup"><span data-stu-id="8dea0-111">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="8dea0-112">DSC on Nano Server は現在開発中であり、まだ完全な機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="8dea0-112">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

<span data-ttu-id="8dea0-113">現在、Nano Server で使用できる DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8dea0-113">The following DSC features are currently available on Nano Server:</span></span>

<span data-ttu-id="8dea0-114">プッシュ モードとプル モード</span><span class="sxs-lookup"><span data-stu-id="8dea0-114">Both push and pull modes</span></span>

- <span data-ttu-id="8dea0-115">以下を含む、通常版の Windows Server に存在するすべての DSC コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8dea0-115">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
- [<span data-ttu-id="8dea0-116">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="8dea0-116">Get-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscLocalConfigurationManager)
- [<span data-ttu-id="8dea0-117">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="8dea0-117">Set-DscLocalConfigurationManager</span></span>](/powershell/module/PSDesiredStateConfiguration/Set-DscLocalConfigurationManager)
- [<span data-ttu-id="8dea0-118">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="8dea0-118">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)
- [<span data-ttu-id="8dea0-119">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="8dea0-119">Disable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Disable-DscDebug)
- [<span data-ttu-id="8dea0-120">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-120">Start-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)
- [<span data-ttu-id="8dea0-121">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-121">Stop-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)
- [<span data-ttu-id="8dea0-122">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-122">Get-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)
- [<span data-ttu-id="8dea0-123">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-123">Test-DscConfiguration</span></span>](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)
- [<span data-ttu-id="8dea0-124">Publish-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-124">Publish-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)
- [<span data-ttu-id="8dea0-125">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-125">Update-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Update-DscConfiguration)
- [<span data-ttu-id="8dea0-126">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="8dea0-126">Restore-DscConfiguration</span></span>](/powershell/module/PSDesiredStateConfiguration/Restore-DscConfiguration)
- [<span data-ttu-id="8dea0-127">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="8dea0-127">Remove-DscConfigurationDocument</span></span>](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)
- [<span data-ttu-id="8dea0-128">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="8dea0-128">Get-DscConfigurationStatus</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)
- [<span data-ttu-id="8dea0-129">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="8dea0-129">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)
- [<span data-ttu-id="8dea0-130">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="8dea0-130">Find-DscResource</span></span>](/powershell/module/powershellget/find-dscresource)
- [<span data-ttu-id="8dea0-131">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="8dea0-131">Get-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)
- [<span data-ttu-id="8dea0-132">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="8dea0-132">New-DscChecksum</span></span>](/powershell/module/PSDesiredStateConfiguration/New-DSCCheckSum)

- <span data-ttu-id="8dea0-133">構成のコンパイル (「[DSC 構成](../configurations/configurations.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-133">Compiling configurations (see [DSC configurations](../configurations/configurations.md))</span></span>

  <span data-ttu-id="8dea0-134">**問題:** 構成のコンパイル中にパスワードの暗号化 (「 [MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)」を参照) が機能しません。</span><span class="sxs-lookup"><span data-stu-id="8dea0-134">**Issue:** Password encryption (see [Securing the MOF File](../pull-server/secureMOF.md)) during configuration compilation doesn't work.</span></span>

- <span data-ttu-id="8dea0-135">メタ構成のコンパイル (「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-135">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](../managing-nodes/metaConfig.md))</span></span>

- <span data-ttu-id="8dea0-136">ユーザー コンテキストでのリソースの実行 ([ユーザーの資格情報を指定した DSC の実行 (RunAs)](../configurations/runAsUser.md) に関するページを参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-136">Running a resource under user context (see [Running DSC with user credentials (RunAs)](../configurations/runAsUser.md))</span></span>

- <span data-ttu-id="8dea0-137">クラスベースのリソース (「[PowerShell クラスを使用したカスタム DSC リソースの記述](/previous-versions//dn948461(v=technet.10))」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-137">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](/previous-versions//dn948461(v=technet.10)))</span></span>

- <span data-ttu-id="8dea0-138">DSC リソースのデバッグ (「[DSC リソースのデバッグ](../troubleshooting/debugResource.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-138">Debugging of DSC resources (see [Debugging DSC resources](../troubleshooting/debugResource.md))</span></span>

  <span data-ttu-id="8dea0-139">**問題:** リソースで PsDscRunAsCredential が使用されている場合に機能しません (「 [ユーザーの資格情報を指定して DSC を実行する](../configurations/runAsUser.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-139">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](../configurations/runAsUser.md))</span></span>

- [<span data-ttu-id="8dea0-140">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="8dea0-140">Specifying cross-node dependencies</span></span>](../configurations/crossNodeDependencies.md)

- [<span data-ttu-id="8dea0-141">リソースのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="8dea0-141">Resource versioning</span></span>](../configurations/sxsResource.md)

- <span data-ttu-id="8dea0-142">プル クライアント (構成とリソース) (「[構成名を使用したプル クライアントのセットアップ](../pull-server/pullClientConfigNames.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-142">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](../pull-server/pullClientConfigNames.md))</span></span>

- [<span data-ttu-id="8dea0-143">部分構成 (プルとプッシュ)</span><span class="sxs-lookup"><span data-stu-id="8dea0-143">Partial configurations (pull & push)</span></span>](../pull-server/partialConfigs.md)

- [<span data-ttu-id="8dea0-144">プル サーバーへの報告</span><span class="sxs-lookup"><span data-stu-id="8dea0-144">Reporting to pull server</span></span>](../pull-server/reportServer.md)

- <span data-ttu-id="8dea0-145">MOF 暗号化</span><span class="sxs-lookup"><span data-stu-id="8dea0-145">MOF encryption</span></span>

- <span data-ttu-id="8dea0-146">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="8dea0-146">Event logging</span></span>

- <span data-ttu-id="8dea0-147">Azure Automation DSC レポート</span><span class="sxs-lookup"><span data-stu-id="8dea0-147">Azure Automation DSC reporting</span></span>

- <span data-ttu-id="8dea0-148">完全に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="8dea0-148">Resources that are fully functional</span></span>

  - <span data-ttu-id="8dea0-149">**Archive**</span><span class="sxs-lookup"><span data-stu-id="8dea0-149">**Archive**</span></span>
  - <span data-ttu-id="8dea0-150">**Environment**</span><span class="sxs-lookup"><span data-stu-id="8dea0-150">**Environment**</span></span>
  - <span data-ttu-id="8dea0-151">**[最近使ったファイル]**</span><span class="sxs-lookup"><span data-stu-id="8dea0-151">**File**</span></span>
  - <span data-ttu-id="8dea0-152">**Log**</span><span class="sxs-lookup"><span data-stu-id="8dea0-152">**Log**</span></span>
  - <span data-ttu-id="8dea0-153">**ProcessSet**</span><span class="sxs-lookup"><span data-stu-id="8dea0-153">**ProcessSet**</span></span>
  - <span data-ttu-id="8dea0-154">**レジストリ**</span><span class="sxs-lookup"><span data-stu-id="8dea0-154">**Registry**</span></span>
  - <span data-ttu-id="8dea0-155">**スクリプト**</span><span class="sxs-lookup"><span data-stu-id="8dea0-155">**Script**</span></span>
  - <span data-ttu-id="8dea0-156">**WindowsPackageCab**</span><span class="sxs-lookup"><span data-stu-id="8dea0-156">**WindowsPackageCab**</span></span>
  - <span data-ttu-id="8dea0-157">**WindowsProcess**</span><span class="sxs-lookup"><span data-stu-id="8dea0-157">**WindowsProcess**</span></span>
  - <span data-ttu-id="8dea0-158">**WaitForAll** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-158">**WaitForAll** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="8dea0-159">**WaitForAny** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-159">**WaitForAny** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>
  - <span data-ttu-id="8dea0-160">**WaitForSome** (「[ノードの相互依存関係の指定](../configurations/crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="8dea0-160">**WaitForSome** (see [Specifying cross-node dependencies](../configurations/crossNodeDependencies.md))</span></span>

- <span data-ttu-id="8dea0-161">部分的に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="8dea0-161">Resources that are partially functional</span></span>

  - <span data-ttu-id="8dea0-162">**グループ**</span><span class="sxs-lookup"><span data-stu-id="8dea0-162">**Group**</span></span>
  - <span data-ttu-id="8dea0-163">**GroupSet**</span><span class="sxs-lookup"><span data-stu-id="8dea0-163">**GroupSet**</span></span>

    <span data-ttu-id="8dea0-164">**問題:** 特定のインスタンスを 2 回呼び出す (同じ構成を 2 回実行する) と上記のリソースでエラーが発生します</span><span class="sxs-lookup"><span data-stu-id="8dea0-164">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

  - <span data-ttu-id="8dea0-165">**サービス**</span><span class="sxs-lookup"><span data-stu-id="8dea0-165">**Service**</span></span>
  - <span data-ttu-id="8dea0-166">**ServiceSet**</span><span class="sxs-lookup"><span data-stu-id="8dea0-166">**ServiceSet**</span></span>

    <span data-ttu-id="8dea0-167">**問題:** サービス (状態) の開始/停止でのみ正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="8dea0-167">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="8dea0-168">StartupType、資格情報、説明などのほかのサービス属性を変更しようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8dea0-168">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="8dea0-169">次のようなエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="8dea0-169">The error thrown is similar to:</span></span>

    ```
    Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.
    ```

- <span data-ttu-id="8dea0-170">機能しないリソース</span><span class="sxs-lookup"><span data-stu-id="8dea0-170">Resources that are not functional</span></span>

  - <span data-ttu-id="8dea0-171">**User**</span><span class="sxs-lookup"><span data-stu-id="8dea0-171">**User**</span></span>

## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="8dea0-172">Nano Server で使用できない DSC 機能</span><span class="sxs-lookup"><span data-stu-id="8dea0-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="8dea0-173">現在、Nano Server で使用できない DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8dea0-173">The following DSC features are not currently available on Nano Server:</span></span>

- <span data-ttu-id="8dea0-174">暗号化パスワードを使用した MOF ドキュメントの暗号化解除</span><span class="sxs-lookup"><span data-stu-id="8dea0-174">Decrypting MOF document with encrypted password(s)</span></span>
- <span data-ttu-id="8dea0-175">プル サーバー - 現在、Nano Server でプル サーバーをセットアップすることはできません</span><span class="sxs-lookup"><span data-stu-id="8dea0-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
- <span data-ttu-id="8dea0-176">動作する機能の一覧に含まれていないもの</span><span class="sxs-lookup"><span data-stu-id="8dea0-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="8dea0-177">Nano Server でのカスタム DSC リソースの使用</span><span class="sxs-lookup"><span data-stu-id="8dea0-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="8dea0-178">Nano Server で使用できる Windows API と CLR ライブラリは限定されているため、完全な CLR バージョンの Windows で動作する DSC は、必ずしも Nano Server で動作するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="8dea0-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="8dea0-179">DSC カスタム リソースを運用環境に展開する前に、エンド ツー エンドのテストを完了してください。</span><span class="sxs-lookup"><span data-stu-id="8dea0-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dea0-180">参照</span><span class="sxs-lookup"><span data-stu-id="8dea0-180">See Also</span></span>

- [<span data-ttu-id="8dea0-181">Nano Server の概要</span><span class="sxs-lookup"><span data-stu-id="8dea0-181">Getting Started with Nano Server</span></span>](/windows-server/get-started/getting-started-with-nano-server)
