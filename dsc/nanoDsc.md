---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC on Nano Server の使用
ms.openlocfilehash: 9e26c525b48e8656a3479db9c0a760eaeb8cf58a
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="using-dsc-on-nano-server"></a><span data-ttu-id="c7131-103">DSC on Nano Server の使用</span><span class="sxs-lookup"><span data-stu-id="c7131-103">Using DSC on Nano Server</span></span>

> <span data-ttu-id="c7131-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c7131-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="c7131-105">**DSC on Nano Server** は、Windows Server 2016 メディアの `NanoServer\Packages` フォルダーに含まれるオプションのパッケージです。</span><span class="sxs-lookup"><span data-stu-id="c7131-105">**DSC on Nano Server** is an optional package in the `NanoServer\Packages` folder of the Windows Server 2016 media.</span></span> <span data-ttu-id="c7131-106">このパッケージをインストールするには、Nano Server の VHD を作成するときに、**New-NanoServerImage** 関数の **Packages** パラメーターの値として **Microsoft-NanoServer-DSC-Package** を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7131-106">The package can be installed when you create a VHD for a Nano Server by specifying **Microsoft-NanoServer-DSC-Package** as the value of the **Packages** parameter of the **New-NanoServerImage** function.</span></span> <span data-ttu-id="c7131-107">たとえば、仮想マシンの VHD を作成する場合、コマンドは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c7131-107">For example, if you are creating a VHD for a virtual machine, the command would look like the following:</span></span>

```powershell
New-NanoServerImage -Edition Standard -DeploymentType Guest -MediaPath f:\ -BasePath .\Base -TargetPath .\Nano1\Nano.vhd -ComputerName Nano1 -Packages Microsoft-NanoServer-DSC-Package
```

<span data-ttu-id="c7131-108">Nano Server のインストールと使用、および PowerShell リモート処理による Nano Server の管理方法については、「[Getting Started with Nano Server (Nano Server の概要)](https://technet.microsoft.com/library/mt126167.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7131-108">For information about installing and using Nano Server, as well as how to manage Nano Server with PowerShell Remoting, see [Getting Started with Nano Server](https://technet.microsoft.com/library/mt126167.aspx).</span></span>


## <a name="dsc-features-available-on-nano-server"></a><span data-ttu-id="c7131-109">Nano Server で使用できる DSC 機能</span><span class="sxs-lookup"><span data-stu-id="c7131-109">DSC features available on Nano Server</span></span>

 <span data-ttu-id="c7131-110">Nano Server でサポートされる API のセットは、通常版の Windows Server と比べると限定的であるため、当面の間、DSC on Nano Server では、すべての SKU で DSC が動作する、完全に機能するパリティを利用できません。</span><span class="sxs-lookup"><span data-stu-id="c7131-110">Because Nano Server supports only a limited set of APIs compared to a full version of Windows Server, DSC on Nano Server does not have full functional parity with DSC running on full SKUs for the time being.</span></span> <span data-ttu-id="c7131-111">DSC on Nano Server は現在開発中であり、まだ完全な機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="c7131-111">DSC on Nano Server is in active development and is not yet feature complete.</span></span>

 <span data-ttu-id="c7131-112">現在、Nano Server で使用できる DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7131-112">The following DSC features are currently available on Nano Server:</span></span>


* <span data-ttu-id="c7131-113">プッシュ モードとプル モード</span><span class="sxs-lookup"><span data-stu-id="c7131-113">Both push and pull modes</span></span>

* <span data-ttu-id="c7131-114">以下を含む、通常版の Windows Server に存在するすべての DSC コマンドレット</span><span class="sxs-lookup"><span data-stu-id="c7131-114">All DSC cmdlets that exist on a full version of Windows Server, including the following:</span></span>
  * [<span data-ttu-id="c7131-115">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="c7131-115">Get-DscLocalConfigurationManager</span></span>](https://technet.microsoft.com/library/dn407378.aspx)
  * [<span data-ttu-id="c7131-116">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="c7131-116">Set-DscLocalConfigurationManager</span></span>](https://technet.microsoft.com/library/dn521621.aspx)
  * [<span data-ttu-id="c7131-117">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="c7131-117">Enable-DscDebug</span></span>](https://technet.microsoft.com/en-us/library/mt517870.aspx)
  * [<span data-ttu-id="c7131-118">Disable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="c7131-118">Disable-DscDebug</span></span>](https://technet.microsoft.com/en-us/library/mt517872.aspx)
  * [<span data-ttu-id="c7131-119">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-119">Start-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn521623.aspx)
  * [<span data-ttu-id="c7131-120">Stop-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-120">Stop-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/mt143542.aspx)
  * [<span data-ttu-id="c7131-121">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-121">Get-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407379.aspx)
  * [<span data-ttu-id="c7131-122">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-122">Test-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407382.aspx)
  * [<span data-ttu-id="c7131-123">Publish-DscConfiguraiton</span><span class="sxs-lookup"><span data-stu-id="c7131-123">Publish-DscConfiguraiton</span></span>](https://technet.microsoft.com/en-us/library/mt517875.aspx)
  * [<span data-ttu-id="c7131-124">Update-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-124">Update-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/mt143541.aspx)
  * [<span data-ttu-id="c7131-125">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7131-125">Restore-DscConfiguration</span></span>](https://technet.microsoft.com/en-us/library/dn407383.aspx)
  * [<span data-ttu-id="c7131-126">Remove-DscConfigurationDocument</span><span class="sxs-lookup"><span data-stu-id="c7131-126">Remove-DscConfigurationDocument</span></span>](https://technet.microsoft.com/en-us/library/mt143544.aspx)
  * [<span data-ttu-id="c7131-127">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="c7131-127">Get-DscConfigurationStatus</span></span>](https://technet.microsoft.com/en-us/library/mt517868.aspx)
  * [<span data-ttu-id="c7131-128">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="c7131-128">Invoke-DscResource</span></span>](https://technet.microsoft.com/en-us/library/mt517869.aspx)
  * [<span data-ttu-id="c7131-129">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="c7131-129">Find-DscResource</span></span>](https://technet.microsoft.com/en-us/library/mt517874.aspx)
  * [<span data-ttu-id="c7131-130">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="c7131-130">Get-DscResource</span></span>](https://technet.microsoft.com/en-us/library/dn521625.aspx)
  * [<span data-ttu-id="c7131-131">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="c7131-131">New-DscChecksum</span></span>](https://technet.microsoft.com/en-us/library/dn521622.aspx)

* <span data-ttu-id="c7131-132">構成のコンパイル (「[DSC 構成](configurations.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-132">Compiling configurations (see [DSC configurations](configurations.md))</span></span>

  <span data-ttu-id="c7131-133">**問題:** 構成のコンパイル中にパスワードの暗号化 (「[MOF ファイルのセキュリティ保護](securemof.md)」を参照) が機能しません。</span><span class="sxs-lookup"><span data-stu-id="c7131-133">**Issue:** Password encryption (see [Securing the MOF File](securemof.md)) during configuration compilation doesn't work.</span></span>

* <span data-ttu-id="c7131-134">メタ構成のコンパイル (「[ローカル構成マネージャーの構成](metaConfig.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-134">Compiling metaconfigurations (see [Configuring the Local Configuration Manager](metaConfig.md))</span></span>

* <span data-ttu-id="c7131-135">ユーザー コンテキストでのリソースの実行 ([ユーザーの資格情報を指定した DSC の実行 (RunAs)](runAsUser.md) に関するページを参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-135">Running a resource under user context (see [Running DSC with user credentials (RunAs)](runAsUser.md))</span></span>

* <span data-ttu-id="c7131-136">クラスベースのリソース (「[PowerShell クラスを使用したカスタム DSC リソースの記述](authoringResourceClass.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-136">Class-based resources (see [Writing a custom DSC resource with PowerShell classes](authoringResourceClass.md))</span></span>

* <span data-ttu-id="c7131-137">DSC リソースのデバッグ (「[DSC リソースのデバッグ](debugresource.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-137">Debugging of DSC resources (see [Debugging DSC resources](debugresource.md))</span></span>

  <span data-ttu-id="c7131-138">**問題:** リソースで PsDscRunAsCredential が使用されている場合に機能しません (「[ユーザーの資格情報を指定して DSC を実行する](runAsUser.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-138">**Issue:** Doesn't work if a resource is using PsDscRunAsCredential (see [Running DSC with user credentials](runAsUser.md))</span></span>

* [<span data-ttu-id="c7131-139">ノードの相互依存関係の指定</span><span class="sxs-lookup"><span data-stu-id="c7131-139">Specifying cross-node dependencies</span></span>](crossNodeDependencies.md)

* [<span data-ttu-id="c7131-140">リソースのバージョン管理</span><span class="sxs-lookup"><span data-stu-id="c7131-140">Resource versioning</span></span>](sxsResource.md)

* <span data-ttu-id="c7131-141">プル クライアント (構成とリソース) (「[構成名を使用したプル クライアントのセットアップ](pullClientConfigNames.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-141">Pull client (configurations & resources) (see [Setting up a pull client using configuration names](pullClientConfigNames.md))</span></span>

* [<span data-ttu-id="c7131-142">部分構成 (プルとプッシュ)</span><span class="sxs-lookup"><span data-stu-id="c7131-142">Partial configurations (pull & push)</span></span>](partialConfigs.md)

* [<span data-ttu-id="c7131-143">プル サーバーへの報告</span><span class="sxs-lookup"><span data-stu-id="c7131-143">Reporting to pull server</span></span>](reportServer.md)

* <span data-ttu-id="c7131-144">MOF 暗号化</span><span class="sxs-lookup"><span data-stu-id="c7131-144">MOF encryption</span></span>

* <span data-ttu-id="c7131-145">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="c7131-145">Event logging</span></span>

* <span data-ttu-id="c7131-146">Azure Automation DSC レポート</span><span class="sxs-lookup"><span data-stu-id="c7131-146">Azure Automation DSC reporting</span></span>

* <span data-ttu-id="c7131-147">完全に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="c7131-147">Resources that are fully functional</span></span>
  * [<span data-ttu-id="c7131-148">Archive</span><span class="sxs-lookup"><span data-stu-id="c7131-148">Archive</span></span>](archiveResource.md)
  * [<span data-ttu-id="c7131-149">Environment</span><span class="sxs-lookup"><span data-stu-id="c7131-149">Environment</span></span>](environmentResource.md)
  * [<span data-ttu-id="c7131-150">File</span><span class="sxs-lookup"><span data-stu-id="c7131-150">File</span></span>](fileResource.md)
  * [<span data-ttu-id="c7131-151">Log</span><span class="sxs-lookup"><span data-stu-id="c7131-151">Log</span></span>](logResource.md)
  * <span data-ttu-id="c7131-152">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="c7131-152">ProcessSet</span></span>
  * [<span data-ttu-id="c7131-153">Registry</span><span class="sxs-lookup"><span data-stu-id="c7131-153">Registry</span></span>](registryResource.md)
  * [<span data-ttu-id="c7131-154">Script</span><span class="sxs-lookup"><span data-stu-id="c7131-154">Script</span></span>](scriptResource.md)
  * <span data-ttu-id="c7131-155">WindowsPackageCab</span><span class="sxs-lookup"><span data-stu-id="c7131-155">WindowsPackageCab</span></span>
  * [<span data-ttu-id="c7131-156">WindowsProcess</span><span class="sxs-lookup"><span data-stu-id="c7131-156">WindowsProcess</span></span>](windowsProcessResource.md)
  * <span data-ttu-id="c7131-157">WaitForAll (「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-157">WaitForAll (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>
  * <span data-ttu-id="c7131-158">WaitForAny (「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-158">WaitForAny (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>
  * <span data-ttu-id="c7131-159">WaitForSome (「[ノードの相互依存関係の指定](crossNodeDependencies.md)」を参照)</span><span class="sxs-lookup"><span data-stu-id="c7131-159">WaitForSome (see [Specifying cross-node dependencies](crossNodeDependencies.md))</span></span>

* <span data-ttu-id="c7131-160">部分的に機能するリソース</span><span class="sxs-lookup"><span data-stu-id="c7131-160">Resources that are partially functional</span></span>
  * [<span data-ttu-id="c7131-161">グループ</span><span class="sxs-lookup"><span data-stu-id="c7131-161">Group</span></span>](groupResource.md)
  * <span data-ttu-id="c7131-162">GroupSet</span><span class="sxs-lookup"><span data-stu-id="c7131-162">GroupSet</span></span>

  <span data-ttu-id="c7131-163">**問題:** 特定のインスタンスを 2 回呼び出す (同じ構成を 2 回実行する) と上記のリソースでエラーが発生します</span><span class="sxs-lookup"><span data-stu-id="c7131-163">**Issue:** Above resources fail if specific instance is called twice (running the same configuration twice)</span></span>

  * [<span data-ttu-id="c7131-164">Service</span><span class="sxs-lookup"><span data-stu-id="c7131-164">Service</span></span>](serviceResource.md)
  * <span data-ttu-id="c7131-165">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="c7131-165">ServiceSet</span></span>

  <span data-ttu-id="c7131-166">**問題:** サービス (状態) の開始/停止でのみ正常に動作します。</span><span class="sxs-lookup"><span data-stu-id="c7131-166">**Issue:** Only works for starting/stopping (status) service.</span></span> <span data-ttu-id="c7131-167">StartupType、資格情報、説明などのほかのサービス属性を変更しようとするとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c7131-167">Fails, if one tries to change other service attributes like startuptype, credentials, description etc..</span></span> <span data-ttu-id="c7131-168">次のようなエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="c7131-168">The error thrown is similar to:</span></span>

  <span data-ttu-id="c7131-169">*型 [management.managementobject] が見つかりません。この型を含むアセンブリが読み込まれていることを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="c7131-169">*Cannot find type [management.managementobject]: verify that the assembly containing this type is loaded.*</span></span>

* <span data-ttu-id="c7131-170">機能しないリソース</span><span class="sxs-lookup"><span data-stu-id="c7131-170">Resources that are not functional</span></span>
  * [<span data-ttu-id="c7131-171">User</span><span class="sxs-lookup"><span data-stu-id="c7131-171">User</span></span>](userResource.md)


## <a name="dsc-features-not-available-on-nano-server"></a><span data-ttu-id="c7131-172">Nano Server で使用できない DSC 機能</span><span class="sxs-lookup"><span data-stu-id="c7131-172">DSC features not available on Nano Server</span></span>

<span data-ttu-id="c7131-173">現在、Nano Server で使用できない DSC 機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c7131-173">The following DSC features are not currently available on Nano Server:</span></span>

* <span data-ttu-id="c7131-174">暗号化パスワードを使用した MOF ドキュメントの暗号化解除</span><span class="sxs-lookup"><span data-stu-id="c7131-174">Decrypting MOF document with encrypted password(s)</span></span>
* <span data-ttu-id="c7131-175">プル サーバー - 現在、Nano Server でプル サーバーをセットアップすることはできません</span><span class="sxs-lookup"><span data-stu-id="c7131-175">Pull Server--you cannot currently set up a pull server on Nano Server</span></span>
* <span data-ttu-id="c7131-176">動作する機能の一覧に含まれていないもの</span><span class="sxs-lookup"><span data-stu-id="c7131-176">Anything that is not in the list of feature works</span></span>

## <a name="using-custom-dsc-resources-on-nano-server"></a><span data-ttu-id="c7131-177">Nano Server でのカスタム DSC リソースの使用</span><span class="sxs-lookup"><span data-stu-id="c7131-177">Using custom DSC resources on Nano Server</span></span>

<span data-ttu-id="c7131-178">Nano Server で使用できる Windows API と CLR ライブラリは限定されているため、完全な CLR バージョンの Windows で動作する DSC は、必ずしも Nano Server で動作するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="c7131-178">Due to a limited sets of Windows APIs and CLR libraries available on Nano Server, DSC resources that work on the full CLR version of Windows do not necessarily work on Nano Server.</span></span>
<span data-ttu-id="c7131-179">DSC カスタム リソースを運用環境に展開する前に、エンド ツー エンドのテストを完了してください。</span><span class="sxs-lookup"><span data-stu-id="c7131-179">Complete end-to-end testing before deploying any DSC custom resources to a production environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7131-180">参照</span><span class="sxs-lookup"><span data-stu-id="c7131-180">See Also</span></span>
- [<span data-ttu-id="c7131-181">Nano Server の概要</span><span class="sxs-lookup"><span data-stu-id="c7131-181">Getting Started with Nano Server</span></span>](https://technet.microsoft.com/library/mt126167.aspx)