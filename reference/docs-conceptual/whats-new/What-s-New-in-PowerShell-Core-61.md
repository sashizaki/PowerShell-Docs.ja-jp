---
title: PowerShell Core 6.1 の新機能
description: PowerShell Core 6.1 でリリースされた新機能と変更
ms.date: 09/13/2018
ms.openlocfilehash: fe1e892d4a13a7758f5405867fdd7488c059f5cc
ms.sourcegitcommit: 806cf87488b80800b9f50a8af286e8379519a034
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293318"
---
# <a name="whats-new-in-powershell-core-61"></a><span data-ttu-id="e90a0-103">PowerShell Core 6.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="e90a0-103">What's New in PowerShell Core 6.1</span></span>

<span data-ttu-id="e90a0-104">以下では、PowerShell Core 6.1 で導入された主要な新機能と変更点からいくつか選んで説明します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-104">Below is a selection of some of the major new features and changes that have been introduced in PowerShell Core 6.1.</span></span>

<span data-ttu-id="e90a0-105">PowerShell をさらに速く安定したものにする**数多くの** "細かな新機能と変更" (それに多数のバグ修正) が他にもあります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-105">There's also **tons** of "boring stuff" that make PowerShell faster and more stable (plus lots and lots of bug fixes)!</span></span>
<span data-ttu-id="e90a0-106">すべての変更点のリストについては、[GitHub の変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md)に関するページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-106">For a full list of changes, check out our [changelog on GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span></span>

<span data-ttu-id="e90a0-107">以下では何人かの名前を挙げていますが、このリリースを可能にしてくれた[コミュニティのすべての共同作成者](https://github.com/PowerShell/PowerShell/graphs/contributors)に感謝します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-107">And while we call out some names below, thank you to [all of the community contributors](https://github.com/PowerShell/PowerShell/graphs/contributors) that made this release possible.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="e90a0-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-108">.NET Core 2.1</span></span>

<span data-ttu-id="e90a0-109">PowerShell Core 6.1 は [5 月のリリース](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/)後に .NET Core 2.1 に移行し、次のようないくつかの機能強化が行われました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-109">PowerShell Core 6.1 moved to .NET Core 2.1 after it was [released in May](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/), resulting in a number of improvements to PowerShell, including:</span></span>

- <span data-ttu-id="e90a0-110">パフォーマンスの向上 ([後述](#performance-improvements)を参照)</span><span class="sxs-lookup"><span data-stu-id="e90a0-110">performance improvements (see [below](#performance-improvements))</span></span>
- <span data-ttu-id="e90a0-111">Alpine Linux のサポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e90a0-111">Alpine Linux support (preview)</span></span>
- <span data-ttu-id="e90a0-112">[.NET グローバル ツールのサポート](/dotnet/core/tools/global-tools) - PowerShell では近日対応</span><span class="sxs-lookup"><span data-stu-id="e90a0-112">[.NET global tool support](/dotnet/core/tools/global-tools) - coming soon to PowerShell</span></span>
- [`Span<T>`](/dotnet/api/system.span-1?view=netcore-2.1)

## <a name="windows-compatibility-pack-for-net-core"></a><span data-ttu-id="e90a0-113">.NET Core 用の Windows 互換機能パック</span><span class="sxs-lookup"><span data-stu-id="e90a0-113">Windows Compatibility Pack for .NET Core</span></span>

<span data-ttu-id="e90a0-114">Windows の .NET チームが [.NET Core 用の Windows 互換機能パック](https://blogs.msdn.microsoft.com/dotnet/2017/11/16/announcing-the-windows-compatibility-pack-for-net-core/)を出荷しました。これは、削除された API を Windows の .NET Core に追加して戻すアセンブリのセットです。</span><span class="sxs-lookup"><span data-stu-id="e90a0-114">On Windows, the .NET team shipped the [Windows Compatibility Pack for .NET Core](https://blogs.msdn.microsoft.com/dotnet/2017/11/16/announcing-the-windows-compatibility-pack-for-net-core/), a set of assemblies that add a number of removed APIs back to .NET Core on Windows.</span></span>

<span data-ttu-id="e90a0-115">この Windows 互換機能パックを PowerShell Core 6.1 リリースに追加し、これらの API を使用するモジュールまたはスクリプトがそれらに依存できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-115">We've added the Windows Compatibility Pack to PowerShell Core 6.1 release so that any modules or scripts that use these APIs can rely on them being available.</span></span>

<span data-ttu-id="e90a0-116">Windows 互換機能パックにより、PowerShell Core では **Windows 10 October 2018 Update および Windows Server 2019 に付属する 1900 を超えるコマンドレット**を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-116">The Windows Compatibility Pack enables PowerShell Core to use **more than 1900 cmdlets that ship with Windows 10 October 2018 Update and Windows Server 2019**.</span></span>

## <a name="support-for-application-whitelisting"></a><span data-ttu-id="e90a0-117">アプリケーション ホワイトリストのサポート</span><span class="sxs-lookup"><span data-stu-id="e90a0-117">Support for Application Whitelisting</span></span>

<span data-ttu-id="e90a0-118">PowerShell Core 6.1 では、Windows PowerShell 5.1 と同じように、[AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) および [Device Guard](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control) のアプリケーション ホワイトリストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e90a0-118">PowerShell Core 6.1 has parity with Windows PowerShell 5.1 supporting [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) and [Device Guard](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control) application whitelisting.</span></span>
<span data-ttu-id="e90a0-119">アプリケーション ホワイトリストを使用すると、PowerShell の[制約付き言語モード](https://blogs.msdn.microsoft.com/powershell/2017/11/02/powershell-constrained-language-mode/)で実行できるバイナリを細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-119">Application whitelisting allows granular control of what binaries are allowed to be executed used with PowerShell [Constrained Language mode](https://blogs.msdn.microsoft.com/powershell/2017/11/02/powershell-constrained-language-mode/).</span></span>

## <a name="performance-improvements"></a><span data-ttu-id="e90a0-120">パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="e90a0-120">Performance improvements</span></span>

<span data-ttu-id="e90a0-121">PowerShell Core 6.0 では、いくつか大きなパフォーマンス向上が行われます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-121">PowerShell Core 6.0 made some significant performance improvements.</span></span>
<span data-ttu-id="e90a0-122">PowerShell Core 6.1 では引き続き、特定の操作の速度向上が行われています。</span><span class="sxs-lookup"><span data-stu-id="e90a0-122">PowerShell Core 6.1 continues to improve the speed of certain operations.</span></span>

<span data-ttu-id="e90a0-123">たとえば、`Group-Object` の速度は 66% 向上しました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-123">For example, `Group-Object` has been sped up by 66%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Group-Object }
```

|              | <span data-ttu-id="e90a0-124">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-124">Windows PowerShell 5.1</span></span> | <span data-ttu-id="e90a0-125">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="e90a0-125">PowerShell Core 6.0</span></span> | <span data-ttu-id="e90a0-126">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-126">PowerShell Core 6.1</span></span> |
|--------------|------------------------|---------------------|---------------------|
| <span data-ttu-id="e90a0-127">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="e90a0-127">Time (sec)</span></span>   | <span data-ttu-id="e90a0-128">25.178</span><span class="sxs-lookup"><span data-stu-id="e90a0-128">25.178</span></span>                 | <span data-ttu-id="e90a0-129">19.653</span><span class="sxs-lookup"><span data-stu-id="e90a0-129">19.653</span></span>              | <span data-ttu-id="e90a0-130">6.641</span><span class="sxs-lookup"><span data-stu-id="e90a0-130">6.641</span></span>               |
| <span data-ttu-id="e90a0-131">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-131">Speed-up (%)</span></span> | <span data-ttu-id="e90a0-132">なし</span><span class="sxs-lookup"><span data-stu-id="e90a0-132">N/A</span></span>                    | <span data-ttu-id="e90a0-133">21.9%</span><span class="sxs-lookup"><span data-stu-id="e90a0-133">21.9%</span></span>               | <span data-ttu-id="e90a0-134">66.2%</span><span class="sxs-lookup"><span data-stu-id="e90a0-134">66.2%</span></span>               |

<span data-ttu-id="e90a0-135">同様に、次のような並べ替えのシナリオが 15% 以上向上しています。</span><span class="sxs-lookup"><span data-stu-id="e90a0-135">Similarly, sorting scenarios like this one have improved by more than 15%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Sort-Object }
```

|              | <span data-ttu-id="e90a0-136">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-136">Windows PowerShell 5.1</span></span> | <span data-ttu-id="e90a0-137">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="e90a0-137">PowerShell Core 6.0</span></span> | <span data-ttu-id="e90a0-138">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-138">PowerShell Core 6.1</span></span> |
|--------------|------------------------|---------------------|---------------------|
| <span data-ttu-id="e90a0-139">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="e90a0-139">Time (sec)</span></span>   | <span data-ttu-id="e90a0-140">12.170</span><span class="sxs-lookup"><span data-stu-id="e90a0-140">12.170</span></span>                 | <span data-ttu-id="e90a0-141">8.493</span><span class="sxs-lookup"><span data-stu-id="e90a0-141">8.493</span></span>               | <span data-ttu-id="e90a0-142">7.08</span><span class="sxs-lookup"><span data-stu-id="e90a0-142">7.08</span></span>                |
| <span data-ttu-id="e90a0-143">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-143">Speed-up (%)</span></span> | <span data-ttu-id="e90a0-144">なし</span><span class="sxs-lookup"><span data-stu-id="e90a0-144">N/A</span></span>                    | <span data-ttu-id="e90a0-145">30.2%</span><span class="sxs-lookup"><span data-stu-id="e90a0-145">30.2%</span></span>               | <span data-ttu-id="e90a0-146">16.6%</span><span class="sxs-lookup"><span data-stu-id="e90a0-146">16.6%</span></span>               |

`Import-Csv` <span data-ttu-id="e90a0-147">は Windows PowerShell からの回帰の後で大幅に高速化されてもいます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-147">has also been sped up significantly after a regression from Windows PowerShell.</span></span>
<span data-ttu-id="e90a0-148">次の例では、26,616 行 6 列のテスト用 CSV を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e90a0-148">The following example uses a test CSV with 26,616 rows and six columns:</span></span>

```powershell
Measure-Command {$a = Import-Csv foo.csv}
```

|              | <span data-ttu-id="e90a0-149">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-149">Windows PowerShell 5.1</span></span> | <span data-ttu-id="e90a0-150">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="e90a0-150">PowerShell Core 6.0</span></span> | <span data-ttu-id="e90a0-151">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-151">PowerShell Core 6.1</span></span>    |
|--------------|------------------------|---------------------|------------------------|
| <span data-ttu-id="e90a0-152">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="e90a0-152">Time (sec)</span></span>   | <span data-ttu-id="e90a0-153">0.441</span><span class="sxs-lookup"><span data-stu-id="e90a0-153">0.441</span></span>                  | <span data-ttu-id="e90a0-154">1.069</span><span class="sxs-lookup"><span data-stu-id="e90a0-154">1.069</span></span>               | <span data-ttu-id="e90a0-155">0.268</span><span class="sxs-lookup"><span data-stu-id="e90a0-155">0.268</span></span>                  |
| <span data-ttu-id="e90a0-156">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-156">Speed-up (%)</span></span> | <span data-ttu-id="e90a0-157">なし</span><span class="sxs-lookup"><span data-stu-id="e90a0-157">N/A</span></span>                    | <span data-ttu-id="e90a0-158">-142.4%</span><span class="sxs-lookup"><span data-stu-id="e90a0-158">-142.4%</span></span>             | <span data-ttu-id="e90a0-159">74.9% (WPS から 39.2%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-159">74.9% (39.2% from WPS)</span></span> |

<span data-ttu-id="e90a0-160">最後に、JSON から `PSObject` への変換は、Windows PowerShell から 50% 以上スピードアップされました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-160">Lastly, conversion from JSON into `PSObject` has been sped up by more than 50% since Windows PowerShell.</span></span>
<span data-ttu-id="e90a0-161">次の例では、最大 2 MB のテスト用 JSON ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-161">The following example uses a ~2MB test JSON file:</span></span>

```powershell
Measure-Command {Get-Content .\foo.json | ConvertFrom-Json}
```

|              | <span data-ttu-id="e90a0-162">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-162">Windows PowerShell 5.1</span></span> | <span data-ttu-id="e90a0-163">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="e90a0-163">PowerShell Core 6.0</span></span> | <span data-ttu-id="e90a0-164">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="e90a0-164">PowerShell Core 6.1</span></span>    |
|--------------|------------------------|---------------------|------------------------|
| <span data-ttu-id="e90a0-165">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="e90a0-165">Time (sec)</span></span>   | <span data-ttu-id="e90a0-166">0.259</span><span class="sxs-lookup"><span data-stu-id="e90a0-166">0.259</span></span>                  | <span data-ttu-id="e90a0-167">0.577</span><span class="sxs-lookup"><span data-stu-id="e90a0-167">0.577</span></span>               | <span data-ttu-id="e90a0-168">0.125</span><span class="sxs-lookup"><span data-stu-id="e90a0-168">0.125</span></span>                  |
| <span data-ttu-id="e90a0-169">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-169">Speed-up (%)</span></span> | <span data-ttu-id="e90a0-170">なし</span><span class="sxs-lookup"><span data-stu-id="e90a0-170">N/A</span></span>                    | <span data-ttu-id="e90a0-171">-122.8%</span><span class="sxs-lookup"><span data-stu-id="e90a0-171">-122.8%</span></span>             | <span data-ttu-id="e90a0-172">78.3% (WPS から 51.7%)</span><span class="sxs-lookup"><span data-stu-id="e90a0-172">78.3% (51.7% from WPS)</span></span> |

## <a name="check-system32-for-compatible-in-box-modules-on-windows"></a><span data-ttu-id="e90a0-173">Windows で互換性のある組み込みモジュールについては `system32` を確認する</span><span class="sxs-lookup"><span data-stu-id="e90a0-173">Check `system32` for compatible in-box modules on Windows</span></span>

<span data-ttu-id="e90a0-174">Windows 10 1809 更新プログラムと Windows Server 2019 では、複数の組み込み PowerShell モジュールが更新され、PowerShell Core と互換性有りとマークされました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-174">In the Windows 10 1809 update and Windows Server 2019, we updated a number of in-box PowerShell modules to mark them as compatible with PowerShell Core.</span></span>

<span data-ttu-id="e90a0-175">PowerShell Core 6.1 は起動すると、`PSModulePath` 環境変数の一部として `$windir\System32` を自動的にインクルードします。</span><span class="sxs-lookup"><span data-stu-id="e90a0-175">When PowerShell Core 6.1 starts up, it will automatically include `$windir\System32` as part of the `PSModulePath` environment variable.</span></span>
<span data-ttu-id="e90a0-176">ただし、`CompatiblePSEdition` が `Core` と互換性有りとマークされている場合は、`Get-Module` および `Import-Module` に対してのみモジュールを公開します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-176">However, it only exposes modules to `Get-Module` and `Import-Module` if its `CompatiblePSEdition` is marked as compatible with `Core`.</span></span>


```powershell
Get-Module -ListAvailable
```

> [!NOTE]
> <span data-ttu-id="e90a0-177">インストールされている役割と機能によっては、使用可能として表示されるモジュールが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-177">You may see different available modules depending on what roles and features are installed.</span></span>

```Output
...
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, Get-AppxPackage, Get-AppxPacka...
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, Suspend-BitLocker, Resume-Bit...
Manifest   1.0.0.0    DnsClient                           Core,Desk {Resolve-DnsName, Clear-DnsClientCache, Get-DnsC...
Manifest   1.0.0.0    HgsDiagnostics                      Core,Desk {New-HgsTraceTarget, Get-HgsTrace, Get-HgsTraceF...
Binary     2.0.0.0    Hyper-V                             Core,Desk {Add-VMAssignableDevice, Add-VMDvdDrive, Add-VMF...
Binary     1.1        Hyper-V                             Core,Desk {Add-VMDvdDrive, Add-VMFibreChannelHba, Add-VMHa...
Manifest   2.0.0.0    NetAdapter                          Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetEventPacketCapture               Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                             Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                              Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                              Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                         Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam                       Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetWNV                              Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   2.0.0.0    TrustedPlatformModule               Core,Desk {Get-Tpm, Initialize-Tpm, Clear-Tpm, Unblock-Tpm...
...
```

<span data-ttu-id="e90a0-178">`-SkipEditionCheck` スイッチ パラメーターを使用すると、すべてのモジュールを表示するように、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-178">You can override this behavior to show all modules using the `-SkipEditionCheck` switch parameter.</span></span>
<span data-ttu-id="e90a0-179">また、テーブル出力に対して `PSEdition` プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-179">We've also added a `PSEdition` property to the table output.</span></span>

```powershell
Get-Module Net* -ListAvailable -SkipEditionCheck
```

```Output
    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                        PSEdition ExportedCommands
---------- -------    ----                        --------- ----------------
Manifest   2.0.0.0    NetAdapter                  Core,Desk {Disable-NetAdapter, Disable-NetAdapterBinding, ...
Manifest   1.0.0.0    NetConnection               Core,Desk {Get-NetConnectionProfile, Set-NetConnectionProf...
Manifest   1.0.0.0    NetDiagnostics              Desk      Get-NetView
Manifest   1.0.0.0    NetEventPacketCapture       Core,Desk {New-NetEventSession, Remove-NetEventSession, Ge...
Manifest   2.0.0.0    NetLbfo                     Core,Desk {Add-NetLbfoTeamMember, Add-NetLbfoTeamNic, Get-...
Manifest   1.0.0.0    NetNat                      Core,Desk {Get-NetNat, Get-NetNatExternalAddress, Get-NetN...
Manifest   2.0.0.0    NetQos                      Core,Desk {Get-NetQosPolicy, Set-NetQosPolicy, Remove-NetQ...
Manifest   2.0.0.0    NetSecurity                 Core,Desk {Get-DAPolicyChange, New-NetIPsecAuthProposal, N...
Manifest   1.0.0.0    NetSwitchTeam               Core,Desk {New-NetSwitchTeam, Remove-NetSwitchTeam, Get-Ne...
Manifest   1.0.0.0    NetTCPIP                    Core,Desk {Get-NetIPAddress, Get-NetIPInterface, Get-NetIP...
Manifest   1.0.0.0    NetWNV                      Core,Desk {Get-NetVirtualizationProviderAddress, Get-NetVi...
Manifest   1.0.0.0    NetworkConnectivityStatus   Core,Desk {Get-DAConnectionStatus, Get-NCSIPolicyConfigura...
Manifest   1.0.0.0    NetworkSwitchManager        Core,Desk {Disable-NetworkSwitchEthernetPort, Enable-Netwo...
Manifest   1.0.0.0    NetworkTransition           Core,Desk {Add-NetIPHttpsCertBinding, Disable-NetDnsTransi...
```

<span data-ttu-id="e90a0-180">この動作について詳しくは、[PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-180">For more information about this behavior, check out [PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md).</span></span>

## <a name="markdown-cmdlets-and-rendering"></a><span data-ttu-id="e90a0-181">Markdown のコマンドレットとレンダリング</span><span class="sxs-lookup"><span data-stu-id="e90a0-181">Markdown cmdlets and rendering</span></span>

<span data-ttu-id="e90a0-182">Markdown は、HTML にレンダリングできる基本的な書式設定で読むことができるプレーンテキスト ドキュメントを作成するための標準です。</span><span class="sxs-lookup"><span data-stu-id="e90a0-182">Markdown is a standard for creating readable plaintext documents with basic formatting that can be rendered into HTML.</span></span>

<span data-ttu-id="e90a0-183">6.1 では、Markdown ドキュメントを変換してコンソールにレンダリングできるコマンドレットがいくつか追加されました。次はその例です。</span><span class="sxs-lookup"><span data-stu-id="e90a0-183">We've added some cmdlets in 6.1 that allow you to convert and render Markdown documents in the console, including:</span></span>

- `ConvertFrom-Markdown`
- `Get-MarkdownOption`
- `Set-MarkdownOption`
- `Show-Markdown`

<span data-ttu-id="e90a0-184">たとえば、`Show-Markdown` はマークダウン ファイルをコンソールにレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="e90a0-184">For example, `Show-Markdown` renders a Markdown file in the console:</span></span>

![Show-Markdown の例](./images/markdown_example.png)

<span data-ttu-id="e90a0-186">これらのコマンドレットの動作について詳しくは、[こちらの RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-186">For more information about how these cmdlets work, check out [this RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md).</span></span>

## <a name="experimental-feature-flags"></a><span data-ttu-id="e90a0-187">試験機能フラグ</span><span class="sxs-lookup"><span data-stu-id="e90a0-187">Experimental feature flags</span></span>

<span data-ttu-id="e90a0-188">試験機能フラグを使用すると、確定した機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-188">Experimental feature flags enable users to turn on features that haven't been finalized.</span></span>
<span data-ttu-id="e90a0-189">これらの試験的機能はサポートされておらず、バグが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-189">These experimental features aren't supported and may have bugs.</span></span>

<span data-ttu-id="e90a0-190">この機能について詳しくは、[PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-190">You can learn more about this feature in [PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md).</span></span>

## <a name="web-cmdlet-improvements"></a><span data-ttu-id="e90a0-191">Web コマンドレットの機能強化</span><span class="sxs-lookup"><span data-stu-id="e90a0-191">Web cmdlet improvements</span></span>

<span data-ttu-id="e90a0-192">[@markekraus](https://github.com/markekraus) のおかげで、Web コマンドレット [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span><span class="sxs-lookup"><span data-stu-id="e90a0-192">Thanks to [@markekraus](https://github.com/markekraus), a whole slew of improvements have been made to our web cmdlets: [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span></span>
<span data-ttu-id="e90a0-193">および [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod) に対して多くの機能強化が行われました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-193">and [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod).</span></span>

- <span data-ttu-id="e90a0-194">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) - `application-json` 応答に対する既定のエンコードを UTF-8 に設定</span><span class="sxs-lookup"><span data-stu-id="e90a0-194">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) - default encoding set to UTF-8 for `application-json` responses</span></span>
- <span data-ttu-id="e90a0-195">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - 標準に準拠していない `Content-Type` ヘッダーを許可するための `-SkipHeaderValidation` パラメーター</span><span class="sxs-lookup"><span data-stu-id="e90a0-195">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - `-SkipHeaderValidation` parameter to allow `Content-Type` headers that aren't standards-compliant</span></span>
- <span data-ttu-id="e90a0-196">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - 簡略化された `multipart/form-data` をサポートするための `Form` パラメーター</span><span class="sxs-lookup"><span data-stu-id="e90a0-196">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - `Form` parameter to support simplified `multipart/form-data` support</span></span>
- <span data-ttu-id="e90a0-197">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) - 準拠、リレーション キーの大文字と小文字を区別しない処理</span><span class="sxs-lookup"><span data-stu-id="e90a0-197">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) - Compliant, case-insensitive handling of relation keys</span></span>
- <span data-ttu-id="e90a0-198">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) - Web コマンドレット用の `-Resume` パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="e90a0-198">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) - Add `-Resume` parameter for web cmdlets</span></span>

## <a name="remoting-improvements"></a><span data-ttu-id="e90a0-199">リモート処理の機能強化</span><span class="sxs-lookup"><span data-stu-id="e90a0-199">Remoting improvements</span></span>

### <a name="powershell-direct-for-containers-tries-to-use-powershell-core-first"></a><span data-ttu-id="e90a0-200">コンテナー用の PowerShell Direct は最初に PowerShell Core の使用を試みる</span><span class="sxs-lookup"><span data-stu-id="e90a0-200">PowerShell Direct for Containers tries to use PowerShell Core first</span></span>

<span data-ttu-id="e90a0-201">PowerShell と Hyper-V の機能である [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) を使用すると、ネットワーク接続または他のリモート管理サービスがなくても、Hyper-V VM またはコンテナーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-201">[PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) is a feature of PowerShell and Hyper-V that allows you to connect to a Hyper-V VM or Container without network connectivity or other remote management services.</span></span>

<span data-ttu-id="e90a0-202">以前の PowerShell Direct では、コンテナー上の組み込み Windows PowerShell インスタンスを使用して接続していました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-202">In the past, PowerShell Direct connected using the inbox Windows PowerShell instance on the Container.</span></span>
<span data-ttu-id="e90a0-203">現在の PowerShell Direct は、最初に、`PATH` 環境変数で使用可能な `pwsh.exe` を使用して接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-203">Now, PowerShell Direct first attempts to connect using any available `pwsh.exe` on the `PATH` environment variable.</span></span>
<span data-ttu-id="e90a0-204">`pwsh.exe` を使用できない場合、PowerShell Direct は `powershell.exe` を使用するようにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="e90a0-204">If `pwsh.exe` isn't available, PowerShell Direct falls back to use `powershell.exe`.</span></span>

### <a name="enable-psremoting-now-creates-separate-remoting-endpoints-for-preview-versions"></a><span data-ttu-id="e90a0-205">`Enable-PSRemoting` はプレビュー バージョン用に別のリモート処理エンドポイントを作成するようになった</span><span class="sxs-lookup"><span data-stu-id="e90a0-205">`Enable-PSRemoting` now creates separate remoting endpoints for preview versions</span></span>

`Enable-PSRemoting` <span data-ttu-id="e90a0-206">では、2 つのリモート処理セッション構成が作成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-206">now creates two remoting session configurations:</span></span>

- <span data-ttu-id="e90a0-207">PowerShell のメジャー バージョン用のセッション構成。</span><span class="sxs-lookup"><span data-stu-id="e90a0-207">One for the major version of PowerShell.</span></span> <span data-ttu-id="e90a0-208">たとえば、`PowerShell.6` のように指定します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-208">For example, `PowerShell.6`.</span></span> <span data-ttu-id="e90a0-209">このエンドポイントは、"システム全体" の PowerShell 6 セッション構成として、すべてのマイナー バージョン更新で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-209">This endpoint that can be relied upon across minor version updates as the "system-wide" PowerShell 6 session configuration</span></span>
- <span data-ttu-id="e90a0-210">1 つのバージョンに固有のセッション構成。例:</span><span class="sxs-lookup"><span data-stu-id="e90a0-210">One version-specific session configuration, for example:</span></span> `PowerShell.6.1.0`

<span data-ttu-id="e90a0-211">この動作は、同じコンピューターに PowerShell 6 の複数のバージョンをインストールしてアクセスできるようにしたい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e90a0-211">This behavior is useful if you want to have multiple PowerShell 6 versions installed and accessible on the same machine.</span></span>

<span data-ttu-id="e90a0-212">さらに、`Enable-PSRemoting` コマンドレットを実行した後で、PowerShell のプレビュー バージョンが独自のリモート処理セッション構成を持つようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-212">Additionally, preview versions of PowerShell now get their own remoting session configurations after running the `Enable-PSRemoting` cmdlet:</span></span>

```powershell
C:\WINDOWS\system32> Enable-PSRemoting
```

<span data-ttu-id="e90a0-213">前に WinRM を設定していない場合、出力が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-213">Your output may be different if you haven't set up WinRM before.</span></span>

```Output
WinRM is already set up to receive requests on this computer.
WinRM is already set up for remote management on this computer.
```

<span data-ttu-id="e90a0-214">PowerShell 6 のプレビュー ビルドと安定したビルドおよび特定バージョンごとに、異なる PowerShell セッション構成を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-214">Then you can see separate PowerShell session configurations for the preview and stable builds of PowerShell 6, and for each specific version.</span></span>

```powershell
Get-PSSessionConfiguration
```

```Output
Name          : PowerShell.6.2-preview.1
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : PowerShell.6-preview
PSVersion     : 6.2
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed

Name          : powershell.6.1.0
PSVersion     : 6.1
StartupScript :
RunAsUser     :
Permission    : NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed, BUILTIN\Remote Management Users AccessAllowed
```

### <a name="userhostport-syntax-supported-for-ssh"></a><span data-ttu-id="e90a0-215">SSH に対してサポートされる `user@host:port` 構文</span><span class="sxs-lookup"><span data-stu-id="e90a0-215">`user@host:port` syntax supported for SSH</span></span>

<span data-ttu-id="e90a0-216">SSH クライアントは、通常、`user@host:port` の形式で接続文字列をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e90a0-216">SSH clients typically support a connection string in the format `user@host:port`.</span></span>
<span data-ttu-id="e90a0-217">PowerShell リモート処理用のプロトコルとして SSH が追加されたことに伴い、この形式の接続文字列のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-217">With the addition of SSH as a protocol for PowerShell Remoting, we've added support for this format of connection string:</span></span>

`Enter-PSSession -HostName fooUser@ssh.contoso.com:2222`

## <a name="msi-option-to-add-explorer-shell-context-menu-on-windows"></a><span data-ttu-id="e90a0-218">Windows でエクスプローラー シェルのコンテキスト メニューを追加するための MSI オプション</span><span class="sxs-lookup"><span data-stu-id="e90a0-218">MSI option to add explorer shell context menu on Windows</span></span>

<span data-ttu-id="e90a0-219">[@bergmeister](https://github.com/bergmeister) の尽力により、Windows でコンテキスト メニューを有効にできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-219">Thanks to [@bergmeister](https://github.com/bergmeister), now you can enable a context menu on Windows.</span></span> <span data-ttu-id="e90a0-220">エクスプローラーで任意のフォルダーから PowerShell 6.1 のシステム全体のインストールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-220">Now you can open your system-wide installation of PowerShell 6.1 from any folder in the Windows Explorer:</span></span>

![PowerShell 6 のシェル コンテキスト メニュー](./images/shell_context_menu.png)

## <a name="goodies"></a><span data-ttu-id="e90a0-222">その他</span><span class="sxs-lookup"><span data-stu-id="e90a0-222">Goodies</span></span>

### <a name="run-as-administrator-in-the-windows-shortcut-jump-list"></a><span data-ttu-id="e90a0-223">Windows のショートカット ジャンプ リストでの [管理者として実行]</span><span class="sxs-lookup"><span data-stu-id="e90a0-223">"Run as Administrator" in the Windows shortcut jump list</span></span>

<span data-ttu-id="e90a0-224">[@bergmeister](https://github.com/bergmeister) のおかげで、PowerShell Core のショートカットのジャンプ リストに [管理者として実行] が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-224">Thanks to [@bergmeister](https://github.com/bergmeister), the PowerShell Core shortcut's jump list now includes "Run as Administrator":</span></span>

![PowerShell 6 のジャンプ リストにおける [管理者として実行]](./images/jumplist.png)

### <a name="cd---returns-to-previous-directory"></a><span data-ttu-id="e90a0-226">`cd -` は以前のディレクトリを返す</span><span class="sxs-lookup"><span data-stu-id="e90a0-226">`cd -` returns to previous directory</span></span>

```powershell
C:\Windows\System32> cd C:\
C:\> cd -
C:\Windows\System32>
```

<span data-ttu-id="e90a0-227">または Linux 上:</span><span class="sxs-lookup"><span data-stu-id="e90a0-227">Or on Linux:</span></span>

```ShellSession
PS /etc> cd /usr/bin
PS /usr/bin> cd -
PS /etc>
```

<span data-ttu-id="e90a0-228">また、`cd` と `cd --` は `$HOME` に変更します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-228">Also, `cd` and `cd --` change to `$HOME`.</span></span>

### `Test-Connection`

<span data-ttu-id="e90a0-229">[@iSazonov](https://github.com/iSazonov) のおかげで、[`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) コマンドレットが PowerShell Core に移植されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-229">Thanks to [@iSazonov](https://github.com/iSazonov), the [`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) cmdlet has been ported to PowerShell Core.</span></span>

### <a name="update-help-as-non-admin"></a><span data-ttu-id="e90a0-230">非管理者としての `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="e90a0-230">`Update-Help` as non-admin</span></span>

<span data-ttu-id="e90a0-231">要望が多かったので、`Update-Help` は管理者でなくても実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-231">By popular demand, `Update-Help` no longer needs to be run as an administrator.</span></span>
`Update-Help` <span data-ttu-id="e90a0-232">は既定でユーザー スコープのフォルダーにヘルプを保存するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-232">now defaults to saving help to a user-scoped folder.</span></span>

### <a name="new-methodsproperties-on-pscustomobject"></a><span data-ttu-id="e90a0-233">`PSCustomObject` での新しいメソッド/プロパティ</span><span class="sxs-lookup"><span data-stu-id="e90a0-233">New methods/properties on `PSCustomObject`</span></span>

<span data-ttu-id="e90a0-234">[@iSazonov](https://github.com/iSazonov) のおかげで、`PSCustomObject` に新しいメソッドとプロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-234">Thanks to [@iSazonov](https://github.com/iSazonov), we've added new methods and properties to `PSCustomObject`.</span></span>
`PSCustomObject` <span data-ttu-id="e90a0-235">には、他のオブジェクトと同じように `Count`/`Length` プロパティが含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-235">now includes a `Count`/`Length` property like other objects.</span></span>

```powershell
$PSCustomObject = [pscustomobject]@{foo = 1}

$PSCustomObject.Length
```

```Output
1
```

```powershell
$PSCustomObject.Count
```

```Output
1
```

<span data-ttu-id="e90a0-236">この作業には、`PSCustomObject` 項目を操作およびフィルター処理できる `ForEach` と `Where` メソッドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-236">This work also includes `ForEach` and `Where` methods that allow you to operate and filter on `PSCustomObject` items:</span></span>

```powershell
$PSCustomObject.ForEach({$_.foo + 1})
```

```Output
2
```

```powershell
$PSCustomObject.Where({$_.foo -gt 0})
```

```Output
foo
---
  1
```

### `Where-Object -Not`

<span data-ttu-id="e90a0-237">@SimonWahlin のおかげで、`-Not` パラメーターが `Where-Object` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-237">Thanks to @SimonWahlin, we've added the `-Not` parameter to `Where-Object`.</span></span>
<span data-ttu-id="e90a0-238">パイプラインのオブジェクトを、存在しないプロパティまたは null/空のプロパティ値でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-238">Now you can filter an object at the pipeline for the non-existence of a property, or a null/empty property value.</span></span>

<span data-ttu-id="e90a0-239">たとえば、次のコマンドでは、依存サービスが定義されていないすべてのサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-239">For example, this command returns all services that don't have any dependent services defined:</span></span>

```powershell
Get-Service | Where-Object -Not DependentServices
```

### <a name="new-modulemanifest-creates-a-bom-less-utf-8-document"></a><span data-ttu-id="e90a0-240">`New-ModuleManifest` では BOM のない UTF-8 ドキュメントが作成される</span><span class="sxs-lookup"><span data-stu-id="e90a0-240">`New-ModuleManifest` creates a BOM-less UTF-8 document</span></span>

<span data-ttu-id="e90a0-241">PowerShell 6.0 が BOM のない UTF-8 に移行したことに伴い、`New-ModuleManifest` コマンドレットが、UTF-16 のドキュメントではなく BOM なしの UTF-8 ドキュメントを作成するように更新されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-241">Given our move to BOM-less UTF-8 in PowerShell 6.0, we've updated the `New-ModuleManifest` cmdlet to create a BOM-less UTF-8 document instead of a UTF-16 one.</span></span>

### <a name="conversions-from-psmethod-to-delegate"></a><span data-ttu-id="e90a0-242">PSMethod からデリゲートへの変換</span><span class="sxs-lookup"><span data-stu-id="e90a0-242">Conversions from PSMethod to Delegate</span></span>

<span data-ttu-id="e90a0-243">[@powercode](https://github.com/powercode) のおかげで、`PSMethod` のデリゲートへの変換がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-243">Thanks to [@powercode](https://github.com/powercode), we now support the conversion of a `PSMethod` into a delegate.</span></span>
<span data-ttu-id="e90a0-244">これにより、`PSMethod` `[M]::DoubleStrLen` をデリゲート値として `[M]::AggregateString` に渡す、といったことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-244">This allows you to do things like passing `PSMethod` `[M]::DoubleStrLen` as a delegate value into `[M]::AggregateString`:</span></span>

```powershell
class M {
    static [int] DoubleStrLen([string] $value) { return 2 * $value.Length }

    static [long] AggregateString([string[]] $values, [func[string, int]] $selector) {
        [long] $res = 0
        foreach($s in $values){
            $res += $selector.Invoke($s)
        }
        return $res
    }
}

[M]::AggregateString((gci).Name, [M]::DoubleStrLen)
```

<span data-ttu-id="e90a0-245">この変更について詳しくは、[PR #5287](https://github.com/PowerShell/PowerShell/pull/5287) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-245">For more info on this change, check out [PR #5287](https://github.com/PowerShell/PowerShell/pull/5287).</span></span>

### <a name="standard-deviation-in-measure-object"></a><span data-ttu-id="e90a0-246">`Measure-Object` での標準偏差</span><span class="sxs-lookup"><span data-stu-id="e90a0-246">Standard deviation in `Measure-Object`</span></span>

<span data-ttu-id="e90a0-247">[@CloudyDino](https://github.com/CloudyDino) のおかげで、`StandardDeviation` プロパティが `Measure-Object` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-247">Thanks to [@CloudyDino](https://github.com/CloudyDino), we've added a `StandardDeviation` property to `Measure-Object`:</span></span>

```powershell
Get-Process | Measure-Object -Property CPU -AllStats
```

```Output
Count             : 308
Average           : 31.3720576298701
Sum               : 9662.59375
Maximum           : 4416.046875
Minimum           :
StandardDeviation : 264.389544720926
Property          : CPU
```

### `GetPfxCertificate -Password`

<span data-ttu-id="e90a0-248">[@maybe-hello-world](https://github.com/maybe-hello-world) のおかげで、`Get-PfxCertificate` に `Password` パラメーターが追加されました。このパラメーターは `SecureString` を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-248">Thanks to [@maybe-hello-world](https://github.com/maybe-hello-world), `Get-PfxCertificate` now has the `Password` parameter, which takes a `SecureString`.</span></span> <span data-ttu-id="e90a0-249">これにより、非対話的に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-249">This allows you to use it non-interactively:</span></span>

```powershell
$certFile = '\\server\share\pwd-protected.pfx'
$certPass = Read-Host -AsSecureString -Prompt 'Enter the password for certificate: '

$certThumbPrint = (Get-PfxCertificate -FilePath $certFile -Password $certPass ).ThumbPrint
```

### <a name="removal-of-the-more-function"></a><span data-ttu-id="e90a0-250">`more` 関数の削除</span><span class="sxs-lookup"><span data-stu-id="e90a0-250">Removal of the `more` function</span></span>

<span data-ttu-id="e90a0-251">以前の PowerShell には、`more.com` をラップする `more` という名前の Windows 上の関数がありました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-251">In the past, PowerShell shipped a function on Windows called `more` that wrapped `more.com`.</span></span>
<span data-ttu-id="e90a0-252">この関数は削除されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-252">That function has now been removed.</span></span>

<span data-ttu-id="e90a0-253">また、`help` 関数が変更され、Windows では `more.com` を、Windows 以外のプラットフォームでは `$env:PAGER` で指定されたシステムの既定のページャーを使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-253">Also, the `help` function changed to use `more.com` on Windows, or the system's default pager specified by `$env:PAGER` on non-Windows platforms.</span></span>

### <a name="cd-drivename-now-returns-users-to-the-current-working-directory-in-that-drive"></a><span data-ttu-id="e90a0-254">`cd DriveName:` では、そのドライブの現在の作業ディレクトリに戻るようになりました</span><span class="sxs-lookup"><span data-stu-id="e90a0-254">`cd DriveName:` now returns users to the current working directory in that drive</span></span>

<span data-ttu-id="e90a0-255">以前は、`Set-Location` または `cd` を使用して PSDrive に戻ると、ユーザーはそのドライブの既定の場所に送られました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-255">Previously, using `Set-Location` or `cd` to return to a PSDrive sent users to the default location for that drive.</span></span>

<span data-ttu-id="e90a0-256">[@mcbobke](https://github.com/mcbobke) のおかげで、ユーザーはそのセッションで最後に認識された現在の作業ディレクトリに送られるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-256">Thanks to [@mcbobke](https://github.com/mcbobke), users are now sent to the last known current working directory for that session.</span></span>

### <a name="windows-powershell-type-accelerators"></a><span data-ttu-id="e90a0-257">Windows PowerShell の型アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="e90a0-257">Windows PowerShell type accelerators</span></span>

<span data-ttu-id="e90a0-258">Windows PowerShell では、以下の型アクセラレータが追加されて、それぞれの型を使いやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-258">In Windows PowerShell, we included the following type accelerators to make it easier to work with their respective types:</span></span>

- `[adsi]`<span data-ttu-id="e90a0-259">:</span><span class="sxs-lookup"><span data-stu-id="e90a0-259">:</span></span> `System.DirectoryServices.DirectoryEntry`
- `[adsisearcher]`<span data-ttu-id="e90a0-260">:</span><span class="sxs-lookup"><span data-stu-id="e90a0-260">:</span></span> `System.DirectoryServices.DirectorySearcher`
- `[wmi]`<span data-ttu-id="e90a0-261">:</span><span class="sxs-lookup"><span data-stu-id="e90a0-261">:</span></span> `System.Management.ManagementObject`
- `[wmiclass]`<span data-ttu-id="e90a0-262">:</span><span class="sxs-lookup"><span data-stu-id="e90a0-262">:</span></span> `System.Management.ManagementClass`
- `[wmisearcher]`<span data-ttu-id="e90a0-263">:</span><span class="sxs-lookup"><span data-stu-id="e90a0-263">:</span></span> `System.Management.ManagementObjectSearcher`

<span data-ttu-id="e90a0-264">これらの型アクセラレータは、PowerShell 6 には含まれませんでしたが、Windows で実行される PowerShell 6.1 には追加されています。</span><span class="sxs-lookup"><span data-stu-id="e90a0-264">These type accelerators were not included in PowerShell 6, but have been added to PowerShell 6.1 running on Windows.</span></span>

<span data-ttu-id="e90a0-265">これらの型は、AD および WMI オブジェクトを簡単に構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-265">These types are useful in easily constructing AD and WMI objects.</span></span>

<span data-ttu-id="e90a0-266">たとえば、LDAP を使用してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-266">For example, you can query using LDAP:</span></span>

```powershell
[adsi]'LDAP://CN=FooUse,OU=People,DC=contoso,DC=com'
```

<span data-ttu-id="e90a0-267">次の例では、Win32_OperatingSystem CIM オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-267">Following example creates a Win32_OperatingSystem CIM object:</span></span>

```powershell
[wmi]"Win32_OperatingSystem=@"
```

```Output
SystemDirectory : C:\WINDOWS\system32
Organization    : Contoso IT
BuildNumber     : 18234
RegisteredUser  : Contoso Corp.
SerialNumber    : 12345-67890-ABCDE-F0123
Version         : 10.0.18234
```

<span data-ttu-id="e90a0-268">この例では、Win32_OperatingSystem クラスの ManagementClass オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-268">This example returns a ManagementClass object for Win32_OperatingSystem class.</span></span>

```powershell
[wmiclass]"Win32_OperatingSystem"
```

```Output
   NameSpace: ROOT\cimv2

Name                                Methods              Properties
----                                -------              ----------
Win32_OperatingSystem               {Reboot, Shutdown... {BootDevice, BuildNumber, BuildType, Caption...}
```

### <a name="-lp-alias-for-all--literalpath-parameters"></a><span data-ttu-id="e90a0-269">すべての `-LiteralPath` パラメーターに対する `-lp` エイリアス</span><span class="sxs-lookup"><span data-stu-id="e90a0-269">`-lp` alias for all `-LiteralPath` parameters</span></span>

<span data-ttu-id="e90a0-270">[@kvprasoon](https://github.com/kvprasoon) のおかげで、`-LiteralPath` パラメーターがあるすべての組み込み PowerShell コマンドレットに対し、パラメーター エイリアス `-lp` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-270">Thanks to [@kvprasoon](https://github.com/kvprasoon), we now have a parameter alias `-lp` for all the built-in PowerShell cmdlets that have a `-LiteralPath` parameter.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="e90a0-271">破壊的変更</span><span class="sxs-lookup"><span data-stu-id="e90a0-271">Breaking Changes</span></span>

### <a name="msi-based-installation-paths-on-windows"></a><span data-ttu-id="e90a0-272">Windows での MSI ベースのインストール パス</span><span class="sxs-lookup"><span data-stu-id="e90a0-272">MSI-based installation paths on Windows</span></span>

<span data-ttu-id="e90a0-273">Windows では、MSI パッケージは次のパスにインストールされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-273">On Windows, the MSI package now installs to the following path:</span></span>

- `$env:ProgramFiles\PowerShell\6\` <span data-ttu-id="e90a0-274">6.x の安定したインストールの場合</span><span class="sxs-lookup"><span data-stu-id="e90a0-274">for the stable installation of 6.x</span></span>
- `$env:ProgramFiles\PowerShell\6-preview\` <span data-ttu-id="e90a0-275">6.x のプレビュー インストールの場合</span><span class="sxs-lookup"><span data-stu-id="e90a0-275">for the preview installation of 6.x</span></span>

<span data-ttu-id="e90a0-276">この変更により、Microsoft Update で PowerShell Core を更新/保守できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-276">This change ensures that PowerShell Core can be updated/serviced by Microsoft Update.</span></span>

<span data-ttu-id="e90a0-277">詳しくは、[PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-277">For more information, check out [PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md).</span></span>

### <a name="telemetry-can-only-be-disabled-with-an-environment-variable"></a><span data-ttu-id="e90a0-278">テレメトリは環境変数でのみ無効にできる</span><span class="sxs-lookup"><span data-stu-id="e90a0-278">Telemetry can only be disabled with an environment variable</span></span>

<span data-ttu-id="e90a0-279">PowerShell Core は、起動されると基本的なテレメトリ データを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-279">PowerShell Core sends basic telemetry data to Microsoft when it is launched.</span></span> <span data-ttu-id="e90a0-280">データには、OS 名、OS バージョン、および PowerShell のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-280">The data includes the OS name, OS version, and PowerShell version.</span></span> <span data-ttu-id="e90a0-281">このデータにより、PowerShell が使用されている環境をより深く理解し、新機能と修正の優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e90a0-281">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>

<span data-ttu-id="e90a0-282">このテレメトリを無効にするには、環境変数 `POWERSHELL_TELEMETRY_OPTOUT` を `true`、`yes`、または `1` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e90a0-282">To opt-out of this telemetry, set the environment variable `POWERSHELL_TELEMETRY_OPTOUT` to `true`, `yes`, or `1`.</span></span> <span data-ttu-id="e90a0-283">ファイル `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` を削除することによるテレメトリの無効化はサポートされなくなっています。</span><span class="sxs-lookup"><span data-stu-id="e90a0-283">We no longer support deletion of the file `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` to disable telemetry.</span></span>

### <a name="disallowed-basic-auth-over-http-in-powershell-remoting-on-unix-platforms"></a><span data-ttu-id="e90a0-284">Unix プラットフォーム上の PowerShell リモート処理での HTTP による基本認証が許可されなくなった</span><span class="sxs-lookup"><span data-stu-id="e90a0-284">Disallowed Basic Auth over HTTP in PowerShell Remoting on Unix platforms</span></span>

<span data-ttu-id="e90a0-285">暗号化されていないトラフィックの使用を防ぐため、Unix プラットフォーム上の PowerShell リモート処理では、NTLM/ネゴシエートまたは HTTPS を使用することが必要になりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-285">To prevent the use of unencrypted traffic, PowerShell Remoting on Unix platforms now requires usage of NTLM/Negotiate or HTTPS.</span></span>

<span data-ttu-id="e90a0-286">これらの変更について詳しくは、[Issue #6779](https://github.com/PowerShell/PowerShell/issues/6779) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-286">For more information on these changes, check out [Issue #6779](https://github.com/PowerShell/PowerShell/issues/6779).</span></span>

### <a name="removed-visualbasic-as-a-supported-language-in-add-type"></a><span data-ttu-id="e90a0-287">Add-Type でサポートされる言語としての `VisualBasic` の削除</span><span class="sxs-lookup"><span data-stu-id="e90a0-287">Removed `VisualBasic` as a supported language in Add-Type</span></span>

<span data-ttu-id="e90a0-288">これまでは、`Add-Type` コマンドレットを使用して Visual Basic コードをコンパイルできました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-288">In the past, you could compile Visual Basic code using the `Add-Type` cmdlet.</span></span>
<span data-ttu-id="e90a0-289">Visual Basic は `Add-Type` ではほとんど使用されませんでした。</span><span class="sxs-lookup"><span data-stu-id="e90a0-289">Visual Basic was rarely used with `Add-Type`.</span></span> <span data-ttu-id="e90a0-290">この機能を削除して、PowerShell のサイズを小さくしました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-290">We removed this feature to reduce the size of PowerShell.</span></span>

### <a name="cleaned-up-uses-of-commandtypesworkflow-and-workflowinfocleaned"></a><span data-ttu-id="e90a0-291">`CommandTypes.Workflow` および `WorkflowInfoCleaned` の使用のクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="e90a0-291">Cleaned up uses of `CommandTypes.Workflow` and `WorkflowInfoCleaned`</span></span>

<span data-ttu-id="e90a0-292">これらの変更について詳しくは、[PR #6708](https://github.com/PowerShell/PowerShell/pull/6708) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-292">For more information on these changes, check out [PR #6708](https://github.com/PowerShell/PowerShell/pull/6708).</span></span>

### <a name="group-object-now-sorts-the-groups"></a><span data-ttu-id="e90a0-293">Group-Object でのグループの並べ替え</span><span class="sxs-lookup"><span data-stu-id="e90a0-293">Group-Object now sorts the groups</span></span>

<span data-ttu-id="e90a0-294">パフォーマンス向上の一環として、`Group-Object` でグループの並び替えられた一覧が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-294">As part of the performance improvement, `Group-Object` now returns a sorted listing of the groups.</span></span>
<span data-ttu-id="e90a0-295">順序に依存すべきではありませんが、最初のグループを必要としていた場合、この変更が破壊的になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e90a0-295">Although you should not rely on the order, you could be broken by this change if you wanted the first group.</span></span> <span data-ttu-id="e90a0-296">以前の動作に依存することの影響は低いため、このパフォーマンス向上には変更するだけの価値があると判断されました。</span><span class="sxs-lookup"><span data-stu-id="e90a0-296">We decided that this performance improvement was worth the change since the impact of being dependent on previous behavior is low.</span></span>

<span data-ttu-id="e90a0-297">この変更の詳細については、[問題 #7409](https://github.com/PowerShell/PowerShell/issues/7409) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e90a0-297">For more information on this change, see [Issue #7409](https://github.com/PowerShell/PowerShell/issues/7409).</span></span>
