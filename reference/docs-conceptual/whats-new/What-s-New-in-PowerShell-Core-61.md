---
title: PowerShell Core 6.1 の新機能
description: PowerShell Core 6.1 でリリースされた新機能と変更
ms.date: 09/13/2018
ms.openlocfilehash: 4ff70be239197c7a4f64019d2aab42433f82f36c
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354662"
---
# <a name="whats-new-in-powershell-core-61"></a><span data-ttu-id="364fe-103">PowerShell Core 6.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="364fe-103">What's New in PowerShell Core 6.1</span></span>

<span data-ttu-id="364fe-104">以下では、PowerShell Core 6.1 で導入された主要な新機能と変更点からいくつか選んで説明します。</span><span class="sxs-lookup"><span data-stu-id="364fe-104">Below is a selection of some of the major new features and changes that have been introduced in PowerShell Core 6.1.</span></span>

<span data-ttu-id="364fe-105">PowerShell をさらに速く安定したものにする **数多くの** "細かな新機能と変更" (それに多数のバグ修正) が他にもあります。</span><span class="sxs-lookup"><span data-stu-id="364fe-105">There's also **tons** of "boring stuff" that make PowerShell faster and more stable (plus lots and lots of bug fixes)!</span></span> <span data-ttu-id="364fe-106">すべての変更点のリストについては、[GitHub の変更ログ](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md)に関するページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="364fe-106">For a full list of changes, check out our [changelog on GitHub](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG.md).</span></span>

<span data-ttu-id="364fe-107">以下では何人かの名前を挙げていますが、このリリースを可能にしてくれた[コミュニティのすべての共同作成者](https://github.com/PowerShell/PowerShell/graphs/contributors)に感謝します。</span><span class="sxs-lookup"><span data-stu-id="364fe-107">And while we call out some names below, thank you to [all of the community contributors](https://github.com/PowerShell/PowerShell/graphs/contributors) that made this release possible.</span></span>

## <a name="net-core-21"></a><span data-ttu-id="364fe-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="364fe-108">.NET Core 2.1</span></span>

<span data-ttu-id="364fe-109">PowerShell Core 6.1 は [5 月のリリース](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/)後に .NET Core 2.1 に移行し、次のようないくつかの機能強化が行われました。</span><span class="sxs-lookup"><span data-stu-id="364fe-109">PowerShell Core 6.1 moved to .NET Core 2.1 after it was [released in May](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/), resulting in a number of improvements to PowerShell, including:</span></span>

- <span data-ttu-id="364fe-110">パフォーマンスの向上 ([後述](#performance-improvements)を参照)</span><span class="sxs-lookup"><span data-stu-id="364fe-110">performance improvements (see [below](#performance-improvements))</span></span>
- <span data-ttu-id="364fe-111">Alpine Linux のサポート (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="364fe-111">Alpine Linux support (preview)</span></span>
- <span data-ttu-id="364fe-112">[.NET グローバル ツールのサポート](/dotnet/core/tools/global-tools) - PowerShell では近日対応</span><span class="sxs-lookup"><span data-stu-id="364fe-112">[.NET global tool support](/dotnet/core/tools/global-tools) - coming soon to PowerShell</span></span>
- [`Span<T>`](/dotnet/api/system.span-1)

## <a name="windows-compatibility-pack-for-net-core"></a><span data-ttu-id="364fe-113">.NET Core 用の Windows 互換機能パック</span><span class="sxs-lookup"><span data-stu-id="364fe-113">Windows Compatibility Pack for .NET Core</span></span>

<span data-ttu-id="364fe-114">Windows の .NET チームが [.NET Core 用の Windows 互換機能パック](https://devblogs.microsoft.com/dotnet/announcing-the-windows-compatibility-pack-for-net-core/)を出荷しました。これは、削除された API を Windows の .NET Core に追加して戻すアセンブリのセットです。</span><span class="sxs-lookup"><span data-stu-id="364fe-114">On Windows, the .NET team shipped the [Windows Compatibility Pack for .NET Core](https://devblogs.microsoft.com/dotnet/announcing-the-windows-compatibility-pack-for-net-core/), a set of assemblies that add a number of removed APIs back to .NET Core on Windows.</span></span>

<span data-ttu-id="364fe-115">この Windows 互換機能パックを PowerShell Core 6.1 リリースに追加し、これらの API を使用するモジュールまたはスクリプトがそれらに依存できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="364fe-115">We've added the Windows Compatibility Pack to PowerShell Core 6.1 release so that any modules or scripts that use these APIs can rely on them being available.</span></span>

<span data-ttu-id="364fe-116">Windows 互換機能パックにより、PowerShell Core では **Windows 10 October 2018 Update および Windows Server 2019 に付属する 1900 を超えるコマンドレット** を使用できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-116">The Windows Compatibility Pack enables PowerShell Core to use **more than 1900 cmdlets that ship with Windows 10 October 2018 Update and Windows Server 2019**.</span></span>

## <a name="support-for-application-allow-lists"></a><span data-ttu-id="364fe-117">アプリケーション許可リストのサポート</span><span class="sxs-lookup"><span data-stu-id="364fe-117">Support for Application allow lists</span></span>

<span data-ttu-id="364fe-118">PowerShell Core 6.1 では、Windows PowerShell 5.1 と同じように、[AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) および [Device Guard](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control) のアプリケーション許可リストがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="364fe-118">PowerShell Core 6.1 has parity with Windows PowerShell 5.1 supporting [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview) and [Device Guard](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control) application allow lists.</span></span> <span data-ttu-id="364fe-119">アプリケーション許可リストを使用すると、PowerShell の[制約付き言語モード](https://devblogs.microsoft.com/powershell/powershell-constrained-language-mode/)で実行できるバイナリを細かく制御できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-119">Application allow lists allow granular control of what binaries are allowed to be executed used with PowerShell [Constrained Language mode](https://devblogs.microsoft.com/powershell/powershell-constrained-language-mode/).</span></span>

## <a name="performance-improvements"></a><span data-ttu-id="364fe-120">パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="364fe-120">Performance improvements</span></span>

<span data-ttu-id="364fe-121">PowerShell Core 6.0 では、いくつか大きなパフォーマンス向上が行われます。</span><span class="sxs-lookup"><span data-stu-id="364fe-121">PowerShell Core 6.0 made some significant performance improvements.</span></span> <span data-ttu-id="364fe-122">PowerShell Core 6.1 では引き続き、特定の操作の速度向上が行われています。</span><span class="sxs-lookup"><span data-stu-id="364fe-122">PowerShell Core 6.1 continues to improve the speed of certain operations.</span></span>

<span data-ttu-id="364fe-123">たとえば、`Group-Object` の速度は 66% 向上しました。</span><span class="sxs-lookup"><span data-stu-id="364fe-123">For example, `Group-Object` has been sped up by 66%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Group-Object }
```

|    <span data-ttu-id="364fe-124">メトリック</span><span class="sxs-lookup"><span data-stu-id="364fe-124">Metric</span></span>    | <span data-ttu-id="364fe-125">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="364fe-125">Windows PowerShell 5.1</span></span> | <span data-ttu-id="364fe-126">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="364fe-126">PowerShell Core 6.0</span></span> | <span data-ttu-id="364fe-127">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="364fe-127">PowerShell Core 6.1</span></span> |
| ------------ | ---------------------- | ------------------- | ------------------- |
| <span data-ttu-id="364fe-128">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="364fe-128">Time (sec)</span></span>   | <span data-ttu-id="364fe-129">25.178</span><span class="sxs-lookup"><span data-stu-id="364fe-129">25.178</span></span>                 | <span data-ttu-id="364fe-130">19.653</span><span class="sxs-lookup"><span data-stu-id="364fe-130">19.653</span></span>              | <span data-ttu-id="364fe-131">6.641</span><span class="sxs-lookup"><span data-stu-id="364fe-131">6.641</span></span>               |
| <span data-ttu-id="364fe-132">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="364fe-132">Speed-up (%)</span></span> | <span data-ttu-id="364fe-133">該当なし</span><span class="sxs-lookup"><span data-stu-id="364fe-133">N/A</span></span>                    | <span data-ttu-id="364fe-134">21.9%</span><span class="sxs-lookup"><span data-stu-id="364fe-134">21.9%</span></span>               | <span data-ttu-id="364fe-135">66.2%</span><span class="sxs-lookup"><span data-stu-id="364fe-135">66.2%</span></span>               |

<span data-ttu-id="364fe-136">同様に、次のような並べ替えのシナリオが 15% 以上向上しています。</span><span class="sxs-lookup"><span data-stu-id="364fe-136">Similarly, sorting scenarios like this one have improved by more than 15%:</span></span>

```powershell
Measure-Command { 1..100000 | % {Get-Random -Minimum 1 -Maximum 10000} | Sort-Object }
```

|    <span data-ttu-id="364fe-137">メトリック</span><span class="sxs-lookup"><span data-stu-id="364fe-137">Metric</span></span>    | <span data-ttu-id="364fe-138">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="364fe-138">Windows PowerShell 5.1</span></span> | <span data-ttu-id="364fe-139">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="364fe-139">PowerShell Core 6.0</span></span> | <span data-ttu-id="364fe-140">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="364fe-140">PowerShell Core 6.1</span></span> |
| ------------ | ---------------------- | ------------------- | ------------------- |
| <span data-ttu-id="364fe-141">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="364fe-141">Time (sec)</span></span>   | <span data-ttu-id="364fe-142">12.170</span><span class="sxs-lookup"><span data-stu-id="364fe-142">12.170</span></span>                 | <span data-ttu-id="364fe-143">8.493</span><span class="sxs-lookup"><span data-stu-id="364fe-143">8.493</span></span>               | <span data-ttu-id="364fe-144">7.08</span><span class="sxs-lookup"><span data-stu-id="364fe-144">7.08</span></span>                |
| <span data-ttu-id="364fe-145">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="364fe-145">Speed-up (%)</span></span> | <span data-ttu-id="364fe-146">該当なし</span><span class="sxs-lookup"><span data-stu-id="364fe-146">N/A</span></span>                    | <span data-ttu-id="364fe-147">30.2%</span><span class="sxs-lookup"><span data-stu-id="364fe-147">30.2%</span></span>               | <span data-ttu-id="364fe-148">16.6%</span><span class="sxs-lookup"><span data-stu-id="364fe-148">16.6%</span></span>               |

<span data-ttu-id="364fe-149">また、`Import-Csv` は Windows PowerShell からの後退の後で大幅に高速化されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-149">`Import-Csv` has also been sped up significantly after a regression from Windows PowerShell.</span></span>
<span data-ttu-id="364fe-150">次の例では、26,616 行 6 列のテスト用 CSV を使用しています。</span><span class="sxs-lookup"><span data-stu-id="364fe-150">The following example uses a test CSV with 26,616 rows and six columns:</span></span>

```powershell
Measure-Command {$a = Import-Csv foo.csv}
```

|    <span data-ttu-id="364fe-151">メトリック</span><span class="sxs-lookup"><span data-stu-id="364fe-151">Metric</span></span>    | <span data-ttu-id="364fe-152">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="364fe-152">Windows PowerShell 5.1</span></span> | <span data-ttu-id="364fe-153">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="364fe-153">PowerShell Core 6.0</span></span> |  <span data-ttu-id="364fe-154">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="364fe-154">PowerShell Core 6.1</span></span>   |
| ------------ | ---------------------- | ------------------- | ---------------------- |
| <span data-ttu-id="364fe-155">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="364fe-155">Time (sec)</span></span>   | <span data-ttu-id="364fe-156">0.441</span><span class="sxs-lookup"><span data-stu-id="364fe-156">0.441</span></span>                  | <span data-ttu-id="364fe-157">1.069</span><span class="sxs-lookup"><span data-stu-id="364fe-157">1.069</span></span>               | <span data-ttu-id="364fe-158">0.268</span><span class="sxs-lookup"><span data-stu-id="364fe-158">0.268</span></span>                  |
| <span data-ttu-id="364fe-159">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="364fe-159">Speed-up (%)</span></span> | <span data-ttu-id="364fe-160">該当なし</span><span class="sxs-lookup"><span data-stu-id="364fe-160">N/A</span></span>                    | <span data-ttu-id="364fe-161">-142.4%</span><span class="sxs-lookup"><span data-stu-id="364fe-161">-142.4%</span></span>             | <span data-ttu-id="364fe-162">74.9% (WPS から 39.2%)</span><span class="sxs-lookup"><span data-stu-id="364fe-162">74.9% (39.2% from WPS)</span></span> |

<span data-ttu-id="364fe-163">最後に、JSON から `PSObject` への変換は、Windows PowerShell から 50% 以上スピードアップされました。</span><span class="sxs-lookup"><span data-stu-id="364fe-163">Lastly, conversion from JSON into `PSObject` has been sped up by more than 50% since Windows PowerShell.</span></span>
<span data-ttu-id="364fe-164">次の例では、最大 2 MB のテスト用 JSON ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="364fe-164">The following example uses a ~2MB test JSON file:</span></span>

```powershell
Measure-Command {Get-Content .\foo.json | ConvertFrom-Json}
```

|    <span data-ttu-id="364fe-165">メトリック</span><span class="sxs-lookup"><span data-stu-id="364fe-165">Metric</span></span>    | <span data-ttu-id="364fe-166">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="364fe-166">Windows PowerShell 5.1</span></span> | <span data-ttu-id="364fe-167">PowerShell Core 6.0</span><span class="sxs-lookup"><span data-stu-id="364fe-167">PowerShell Core 6.0</span></span> |  <span data-ttu-id="364fe-168">PowerShell Core 6.1</span><span class="sxs-lookup"><span data-stu-id="364fe-168">PowerShell Core 6.1</span></span>   |
| ------------ | ---------------------- | ------------------- | ---------------------- |
| <span data-ttu-id="364fe-169">時間 (秒)</span><span class="sxs-lookup"><span data-stu-id="364fe-169">Time (sec)</span></span>   | <span data-ttu-id="364fe-170">0.259</span><span class="sxs-lookup"><span data-stu-id="364fe-170">0.259</span></span>                  | <span data-ttu-id="364fe-171">0.577</span><span class="sxs-lookup"><span data-stu-id="364fe-171">0.577</span></span>               | <span data-ttu-id="364fe-172">0.125</span><span class="sxs-lookup"><span data-stu-id="364fe-172">0.125</span></span>                  |
| <span data-ttu-id="364fe-173">高速化 (%)</span><span class="sxs-lookup"><span data-stu-id="364fe-173">Speed-up (%)</span></span> | <span data-ttu-id="364fe-174">該当なし</span><span class="sxs-lookup"><span data-stu-id="364fe-174">N/A</span></span>                    | <span data-ttu-id="364fe-175">-122.8%</span><span class="sxs-lookup"><span data-stu-id="364fe-175">-122.8%</span></span>             | <span data-ttu-id="364fe-176">78.3% (WPS から 51.7%)</span><span class="sxs-lookup"><span data-stu-id="364fe-176">78.3% (51.7% from WPS)</span></span> |

## <a name="check-system32-for-compatible-built-in-modules-on-windows"></a><span data-ttu-id="364fe-177">Windows の互換性のある組み込みモジュールについて、`system32` を確認する</span><span class="sxs-lookup"><span data-stu-id="364fe-177">Check `system32` for compatible built-in modules on Windows</span></span>

<span data-ttu-id="364fe-178">Windows 10 1809 更新プログラムと Windows Server 2019 では、複数の組み込み PowerShell モジュールが更新され、PowerShell Core との互換性があるとしてマークされました。</span><span class="sxs-lookup"><span data-stu-id="364fe-178">In the Windows 10 1809 update and Windows Server 2019, we updated a number of built-in PowerShell modules to mark them as compatible with PowerShell Core.</span></span>

<span data-ttu-id="364fe-179">PowerShell Core 6.1 は起動すると、`PSModulePath` 環境変数の一部として `$windir\System32` を自動的にインクルードします。</span><span class="sxs-lookup"><span data-stu-id="364fe-179">When PowerShell Core 6.1 starts up, it will automatically include `$windir\System32` as part of the `PSModulePath` environment variable.</span></span> <span data-ttu-id="364fe-180">ただし、`CompatiblePSEdition` が `Core` と互換性有りとマークされている場合は、`Get-Module` および `Import-Module` に対してのみモジュールを公開します。</span><span class="sxs-lookup"><span data-stu-id="364fe-180">However, it only exposes modules to `Get-Module` and `Import-Module` if its `CompatiblePSEdition` is marked as compatible with `Core`.</span></span>

```powershell
Get-Module -ListAvailable
```

> [!NOTE]
> <span data-ttu-id="364fe-181">インストールされている役割と機能によっては、使用可能として表示されるモジュールが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="364fe-181">You may see different available modules depending on what roles and features are installed.</span></span>

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

<span data-ttu-id="364fe-182">`-SkipEditionCheck` スイッチ パラメーターを使用すると、すべてのモジュールを表示するように、この動作をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="364fe-182">You can override this behavior to show all modules using the `-SkipEditionCheck` switch parameter.</span></span>
<span data-ttu-id="364fe-183">また、テーブル出力に対して `PSEdition` プロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-183">We've also added a `PSEdition` property to the table output.</span></span>

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

<span data-ttu-id="364fe-184">この動作について詳しくは、[PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-184">For more information about this behavior, check out [PowerShell RFC0025](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-PSCore6-and-Windows-Modules.md).</span></span>

## <a name="markdown-cmdlets-and-rendering"></a><span data-ttu-id="364fe-185">Markdown のコマンドレットとレンダリング</span><span class="sxs-lookup"><span data-stu-id="364fe-185">Markdown cmdlets and rendering</span></span>

<span data-ttu-id="364fe-186">Markdown は、HTML にレンダリングできる基本的な書式設定で読むことができるプレーンテキスト ドキュメントを作成するための標準です。</span><span class="sxs-lookup"><span data-stu-id="364fe-186">Markdown is a standard for creating readable plaintext documents with basic formatting that can be rendered into HTML.</span></span>

<span data-ttu-id="364fe-187">6\.1 では、Markdown ドキュメントを変換してコンソールにレンダリングできるコマンドレットがいくつか追加されました。次はその例です。</span><span class="sxs-lookup"><span data-stu-id="364fe-187">We've added some cmdlets in 6.1 that allow you to convert and render Markdown documents in the console, including:</span></span>

- `ConvertFrom-Markdown`
- `Get-MarkdownOption`
- `Set-MarkdownOption`
- `Show-Markdown`

<span data-ttu-id="364fe-188">たとえば、`Show-Markdown` はマークダウン ファイルをコンソールにレンダリングします。</span><span class="sxs-lookup"><span data-stu-id="364fe-188">For example, `Show-Markdown` renders a Markdown file in the console:</span></span>

![Show-Markdown の例](media/What-s-New-in-PowerShell-Core-61/markdown_example.png)

<span data-ttu-id="364fe-190">これらのコマンドレットの動作について詳しくは、[こちらの RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-190">For more information about how these cmdlets work, check out [this RFC](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0025-Native-Markdown-Rendering.md).</span></span>

## <a name="experimental-feature-flags"></a><span data-ttu-id="364fe-191">試験機能フラグ</span><span class="sxs-lookup"><span data-stu-id="364fe-191">Experimental feature flags</span></span>

<span data-ttu-id="364fe-192">[試験的機能][]のサポートが有効になりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-192">We enabled support for [Experimental Features][].</span></span> <span data-ttu-id="364fe-193">これにより、PowerShell の開発者は新しい機能を提供し、設計が完了する前にフィードバックを取得できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-193">This allows PowerShell developers to deliver new features and get feedback before the design is complete.</span></span> <span data-ttu-id="364fe-194">このようにすると、設計の進化に伴って破壊的変更が発生するのを回避できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-194">This way we avoid making breaking changes as the design evolves.</span></span>

<span data-ttu-id="364fe-195">使用できる試験的機能の一覧を取得するには、`Get-ExperimentalFeature` を使います。</span><span class="sxs-lookup"><span data-stu-id="364fe-195">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="364fe-196">これらの機能は、`Enable-ExperimentalFeature` および `Disable-ExperimentalFeature` で有効または無効にできます。</span><span class="sxs-lookup"><span data-stu-id="364fe-196">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

<span data-ttu-id="364fe-197">この機能について詳しくは、[PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-197">You can learn more about this feature in [PowerShell RFC0029](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0029-Support-Experimental-Features.md).</span></span>

## <a name="web-cmdlet-improvements"></a><span data-ttu-id="364fe-198">Web コマンドレットの機能強化</span><span class="sxs-lookup"><span data-stu-id="364fe-198">Web cmdlet improvements</span></span>

<span data-ttu-id="364fe-199">[@markekraus](https://github.com/markekraus) のおかげで、Web コマンドレット [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span><span class="sxs-lookup"><span data-stu-id="364fe-199">Thanks to [@markekraus](https://github.com/markekraus), a whole slew of improvements have been made to our web cmdlets: [`Invoke-WebRequest`](/powershell/module/microsoft.powershell.utility/invoke-webrequest)</span></span>
<span data-ttu-id="364fe-200">および [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod) に対して多くの機能強化が行われました。</span><span class="sxs-lookup"><span data-stu-id="364fe-200">and [`Invoke-RestMethod`](/powershell/module/microsoft.powershell.utility/invoke-restmethod).</span></span>

- <span data-ttu-id="364fe-201">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) - `application-json` 応答に対する既定のエンコードを UTF-8 に設定</span><span class="sxs-lookup"><span data-stu-id="364fe-201">[PR #6109](https://github.com/PowerShell/PowerShell/pull/6109) - default encoding set to UTF-8 for `application-json` responses</span></span>
- <span data-ttu-id="364fe-202">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - 標準に準拠していない `-SkipHeaderValidation` ヘッダーを許可するための `Content-Type` パラメーター</span><span class="sxs-lookup"><span data-stu-id="364fe-202">[PR #6018](https://github.com/PowerShell/PowerShell/pull/6018) - `-SkipHeaderValidation` parameter to allow `Content-Type` headers that aren't standards-compliant</span></span>
- <span data-ttu-id="364fe-203">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - 簡略化された `Form` をサポートするための `multipart/form-data` パラメーター</span><span class="sxs-lookup"><span data-stu-id="364fe-203">[PR #5972](https://github.com/PowerShell/PowerShell/pull/5972) - `Form` parameter to support simplified `multipart/form-data` support</span></span>
- <span data-ttu-id="364fe-204">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) - 準拠、リレーション キーの大文字と小文字を区別しない処理</span><span class="sxs-lookup"><span data-stu-id="364fe-204">[PR #6338](https://github.com/PowerShell/PowerShell/pull/6338) - Compliant, case-insensitive handling of relation keys</span></span>
- <span data-ttu-id="364fe-205">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) - Web コマンドレット用の `-Resume` パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="364fe-205">[PR #6447](https://github.com/PowerShell/PowerShell/pull/6447) - Add `-Resume` parameter for web cmdlets</span></span>

## <a name="remoting-improvements"></a><span data-ttu-id="364fe-206">リモート処理の機能強化</span><span class="sxs-lookup"><span data-stu-id="364fe-206">Remoting improvements</span></span>

### <a name="powershell-direct-for-containers-tries-to-use-powershell-core-first"></a><span data-ttu-id="364fe-207">コンテナー用の PowerShell Direct は最初に PowerShell Core の使用を試みる</span><span class="sxs-lookup"><span data-stu-id="364fe-207">PowerShell Direct for Containers tries to use PowerShell Core first</span></span>

<span data-ttu-id="364fe-208">PowerShell と Hyper-V の機能である [PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) を使用すると、ネットワーク接続または他のリモート管理サービスがなくても、Hyper-V VM またはコンテナーに接続できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-208">[PowerShell Direct](/virtualization/hyper-v-on-windows/user-guide/powershell-direct) is a feature of PowerShell and Hyper-V that allows you to connect to a Hyper-V VM or Container without network connectivity or other remote management services.</span></span>

<span data-ttu-id="364fe-209">以前の PowerShell Direct では、コンテナー上の組み込み Windows PowerShell インスタンスを使用して接続していました。</span><span class="sxs-lookup"><span data-stu-id="364fe-209">In the past, PowerShell Direct connected using the built-in Windows PowerShell instance on the Container.</span></span> <span data-ttu-id="364fe-210">現在の PowerShell Direct は、最初に、`PATH` 環境変数で使用可能な `pwsh.exe` を使用して接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="364fe-210">Now, PowerShell Direct first attempts to connect using any available `pwsh.exe` on the `PATH` environment variable.</span></span> <span data-ttu-id="364fe-211">`pwsh.exe` を使用できない場合、PowerShell Direct は `powershell.exe` を使用するようにフォールバックします。</span><span class="sxs-lookup"><span data-stu-id="364fe-211">If `pwsh.exe` isn't available, PowerShell Direct falls back to use `powershell.exe`.</span></span>

### <a name="enable-psremoting-now-creates-separate-remoting-endpoints-for-preview-versions"></a><span data-ttu-id="364fe-212">`Enable-PSRemoting` はプレビュー バージョン用に別のリモート処理エンドポイントを作成するようになった</span><span class="sxs-lookup"><span data-stu-id="364fe-212">`Enable-PSRemoting` now creates separate remoting endpoints for preview versions</span></span>

<span data-ttu-id="364fe-213">`Enable-PSRemoting` では、2 つのリモート処理セッション構成が作成されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-213">`Enable-PSRemoting` now creates two remoting session configurations:</span></span>

- <span data-ttu-id="364fe-214">PowerShell のメジャー バージョン用のセッション構成。</span><span class="sxs-lookup"><span data-stu-id="364fe-214">One for the major version of PowerShell.</span></span> <span data-ttu-id="364fe-215">たとえば、「 `PowerShell.6` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="364fe-215">For example, `PowerShell.6`.</span></span> <span data-ttu-id="364fe-216">このエンドポイントは、"システム全体" の PowerShell 6 セッション構成として、すべてのマイナー バージョン更新で利用できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-216">This endpoint that can be relied upon across minor version updates as the "system-wide" PowerShell 6 session configuration</span></span>
- <span data-ttu-id="364fe-217">1 つのバージョンに固有のセッション構成。たとえば、`PowerShell.6.1.0` などです。</span><span class="sxs-lookup"><span data-stu-id="364fe-217">One version-specific session configuration, for example: `PowerShell.6.1.0`</span></span>

<span data-ttu-id="364fe-218">この動作は、同じコンピューターに PowerShell 6 の複数のバージョンをインストールしてアクセスできるようにしたい場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="364fe-218">This behavior is useful if you want to have multiple PowerShell 6 versions installed and accessible on the same machine.</span></span>

<span data-ttu-id="364fe-219">さらに、`Enable-PSRemoting` コマンドレットを実行した後で、PowerShell のプレビュー バージョンが独自のリモート処理セッション構成を持つようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-219">Additionally, preview versions of PowerShell now get their own remoting session configurations after running the `Enable-PSRemoting` cmdlet:</span></span>

```powershell
C:\WINDOWS\system32> Enable-PSRemoting
```

<span data-ttu-id="364fe-220">前に WinRM を設定していない場合、出力が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="364fe-220">Your output may be different if you haven't set up WinRM before.</span></span>

```Output
WinRM is already set up to receive requests on this computer.
WinRM is already set up for remote management on this computer.
```

<span data-ttu-id="364fe-221">PowerShell 6 のプレビュー ビルドと安定したビルドおよび特定バージョンごとに、異なる PowerShell セッション構成を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="364fe-221">Then you can see separate PowerShell session configurations for the preview and stable builds of PowerShell 6, and for each specific version.</span></span>

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

### <a name="userhostport-syntax-supported-for-ssh"></a><span data-ttu-id="364fe-222">SSH に対してサポートされる `user@host:port` 構文</span><span class="sxs-lookup"><span data-stu-id="364fe-222">`user@host:port` syntax supported for SSH</span></span>

<span data-ttu-id="364fe-223">SSH クライアントは、通常、`user@host:port` の形式で接続文字列をサポートします。</span><span class="sxs-lookup"><span data-stu-id="364fe-223">SSH clients typically support a connection string in the format `user@host:port`.</span></span> <span data-ttu-id="364fe-224">PowerShell リモート処理用のプロトコルとして SSH が追加されたことに伴い、この形式の接続文字列のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-224">With the addition of SSH as a protocol for PowerShell Remoting, we've added support for this format of connection string:</span></span>

`Enter-PSSession -HostName fooUser@ssh.contoso.com:2222`

## <a name="msi-option-to-add-explorer-shell-context-menu-on-windows"></a><span data-ttu-id="364fe-225">Windows でエクスプローラー シェルのコンテキスト メニューを追加するための MSI オプション</span><span class="sxs-lookup"><span data-stu-id="364fe-225">MSI option to add explorer shell context menu on Windows</span></span>

<span data-ttu-id="364fe-226">[@bergmeister](https://github.com/bergmeister) の尽力により、Windows でコンテキスト メニューを有効にできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-226">Thanks to [@bergmeister](https://github.com/bergmeister), now you can enable a context menu on Windows.</span></span> <span data-ttu-id="364fe-227">エクスプローラーで任意のフォルダーから PowerShell 6.1 のシステム全体のインストールを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="364fe-227">Now you can open your system-wide installation of PowerShell 6.1 from any folder in the Windows Explorer:</span></span>

![PowerShell 6 のシェル コンテキスト メニュー](media/What-s-New-in-PowerShell-Core-61/shell_context_menu.png)

## <a name="goodies"></a><span data-ttu-id="364fe-229">その他</span><span class="sxs-lookup"><span data-stu-id="364fe-229">Goodies</span></span>

### <a name="run-as-administrator-in-the-windows-shortcut-jump-list"></a><span data-ttu-id="364fe-230">Windows のショートカット ジャンプ リストでの [管理者として実行]</span><span class="sxs-lookup"><span data-stu-id="364fe-230">"Run as Administrator" in the Windows shortcut jump list</span></span>

<span data-ttu-id="364fe-231">[@bergmeister](https://github.com/bergmeister) のおかげで、PowerShell Core のショートカットのジャンプ リストに [管理者として実行] が含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-231">Thanks to [@bergmeister](https://github.com/bergmeister), the PowerShell Core shortcut's jump list now includes "Run as Administrator":</span></span>

![PowerShell 6 のジャンプ リストにおける [管理者として実行]](media/What-s-New-in-PowerShell-Core-61/jumplist.png)

### <a name="cd---returns-to-previous-directory"></a><span data-ttu-id="364fe-233">`cd -` は以前のディレクトリを返す</span><span class="sxs-lookup"><span data-stu-id="364fe-233">`cd -` returns to previous directory</span></span>

```powershell
C:\Windows\System32> cd C:\
C:\> cd -
C:\Windows\System32>
```

<span data-ttu-id="364fe-234">または Linux 上:</span><span class="sxs-lookup"><span data-stu-id="364fe-234">Or on Linux:</span></span>

```ShellSession
PS /etc> cd /usr/bin
PS /usr/bin> cd -
PS /etc>
```

<span data-ttu-id="364fe-235">また、`cd` と `cd --` は `$HOME` に変更します。</span><span class="sxs-lookup"><span data-stu-id="364fe-235">Also, `cd` and `cd --` change to `$HOME`.</span></span>

### `Test-Connection`

<span data-ttu-id="364fe-236">[@iSazonov](https://github.com/iSazonov) のおかげで、[`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) コマンドレットが PowerShell Core に移植されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-236">Thanks to [@iSazonov](https://github.com/iSazonov), the [`Test-Connection`](/powershell/module/microsoft.powershell.management/test-connection) cmdlet has been ported to PowerShell Core.</span></span>

### <a name="update-help-as-non-admin"></a><span data-ttu-id="364fe-237">非管理者としての `Update-Help`</span><span class="sxs-lookup"><span data-stu-id="364fe-237">`Update-Help` as non-admin</span></span>

<span data-ttu-id="364fe-238">要望が多かったので、`Update-Help` は管理者でなくても実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-238">By popular demand, `Update-Help` no longer needs to be run as an administrator.</span></span> <span data-ttu-id="364fe-239">`Update-Help` は既定でユーザー スコープのフォルダーにヘルプを保存します。</span><span class="sxs-lookup"><span data-stu-id="364fe-239">`Update-Help` now defaults to saving help to a user-scoped folder.</span></span>

### <a name="new-methodsproperties-on-pscustomobject"></a><span data-ttu-id="364fe-240">`PSCustomObject` での新しいメソッド/プロパティ</span><span class="sxs-lookup"><span data-stu-id="364fe-240">New methods/properties on `PSCustomObject`</span></span>

<span data-ttu-id="364fe-241">[@iSazonov](https://github.com/iSazonov) のおかげで、`PSCustomObject` に新しいメソッドとプロパティが追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-241">Thanks to [@iSazonov](https://github.com/iSazonov), we've added new methods and properties to `PSCustomObject`.</span></span> <span data-ttu-id="364fe-242">`PSCustomObject` には、他のオブジェクトと同じように `Count`/`Length` プロパティが含まれるようになっています。</span><span class="sxs-lookup"><span data-stu-id="364fe-242">`PSCustomObject` now includes a `Count`/`Length` property like other objects.</span></span>

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

<span data-ttu-id="364fe-243">この作業には、`PSCustomObject` 項目を操作およびフィルター処理できる `ForEach` と `Where` メソッドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="364fe-243">This work also includes `ForEach` and `Where` methods that allow you to operate and filter on `PSCustomObject` items:</span></span>

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

<span data-ttu-id="364fe-244">@SimonWahlin のおかげで、`-Not` パラメーターが `Where-Object` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-244">Thanks to @SimonWahlin, we've added the `-Not` parameter to `Where-Object`.</span></span> <span data-ttu-id="364fe-245">パイプラインのオブジェクトを、存在しないプロパティまたは null/空のプロパティ値でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-245">Now you can filter an object at the pipeline for the non-existence of a property, or a null/empty property value.</span></span>

<span data-ttu-id="364fe-246">たとえば、次のコマンドでは、依存サービスが定義されていないすべてのサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="364fe-246">For example, this command returns all services that don't have any dependent services defined:</span></span>

```powershell
Get-Service | Where-Object -Not DependentServices
```

### <a name="new-modulemanifest-creates-a-bom-less-utf-8-document"></a><span data-ttu-id="364fe-247">`New-ModuleManifest` では BOM のない UTF-8 ドキュメントが作成される</span><span class="sxs-lookup"><span data-stu-id="364fe-247">`New-ModuleManifest` creates a BOM-less UTF-8 document</span></span>

<span data-ttu-id="364fe-248">PowerShell 6.0 が BOM のない UTF-8 に移行したことに伴い、`New-ModuleManifest` コマンドレットが、UTF-16 のドキュメントではなく BOM なしの UTF-8 ドキュメントを作成するように更新されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-248">Given our move to BOM-less UTF-8 in PowerShell 6.0, we've updated the `New-ModuleManifest` cmdlet to create a BOM-less UTF-8 document instead of a UTF-16 one.</span></span>

### <a name="conversions-from-psmethod-to-delegate"></a><span data-ttu-id="364fe-249">PSMethod からデリゲートへの変換</span><span class="sxs-lookup"><span data-stu-id="364fe-249">Conversions from PSMethod to Delegate</span></span>

<span data-ttu-id="364fe-250">[@powercode](https://github.com/powercode) のおかげで、`PSMethod` のデリゲートへの変換がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-250">Thanks to [@powercode](https://github.com/powercode), we now support the conversion of a `PSMethod` into a delegate.</span></span> <span data-ttu-id="364fe-251">これにより、`PSMethod` `[M]::DoubleStrLen` をデリゲート値として `[M]::AggregateString` に渡すといった操作ができるようになります。</span><span class="sxs-lookup"><span data-stu-id="364fe-251">This allows you to do things like passing `PSMethod` `[M]::DoubleStrLen` as a delegate value into `[M]::AggregateString`:</span></span>

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

<span data-ttu-id="364fe-252">この変更について詳しくは、[PR #5287](https://github.com/PowerShell/PowerShell/pull/5287) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-252">For more info on this change, check out [PR #5287](https://github.com/PowerShell/PowerShell/pull/5287).</span></span>

### <a name="standard-deviation-in-measure-object"></a><span data-ttu-id="364fe-253">`Measure-Object` での標準偏差</span><span class="sxs-lookup"><span data-stu-id="364fe-253">Standard deviation in `Measure-Object`</span></span>

<span data-ttu-id="364fe-254">[@CloudyDino](https://github.com/CloudyDino) のおかげで、`StandardDeviation` プロパティが `Measure-Object` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-254">Thanks to [@CloudyDino](https://github.com/CloudyDino), we've added a `StandardDeviation` property to `Measure-Object`:</span></span>

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

<span data-ttu-id="364fe-255">[@maybe-hello-world](https://github.com/maybe-hello-world) のおかげで、`Get-PfxCertificate` に `Password` パラメーターが追加されました。このパラメーターは `SecureString` を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="364fe-255">Thanks to [@maybe-hello-world](https://github.com/maybe-hello-world), `Get-PfxCertificate` now has the `Password` parameter, which takes a `SecureString`.</span></span> <span data-ttu-id="364fe-256">これにより、非対話的に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="364fe-256">This allows you to use it non-interactively:</span></span>

```powershell
$certFile = '\\server\share\pwd-protected.pfx'
$certPass = Read-Host -AsSecureString -Prompt 'Enter the password for certificate: '

$certThumbPrint = (Get-PfxCertificate -FilePath $certFile -Password $certPass ).ThumbPrint
```

### <a name="removal-of-the-more-function"></a><span data-ttu-id="364fe-257">`more` 関数の削除</span><span class="sxs-lookup"><span data-stu-id="364fe-257">Removal of the `more` function</span></span>

<span data-ttu-id="364fe-258">以前の PowerShell には、`more.com` をラップする `more` という名前の Windows 上の関数がありました。</span><span class="sxs-lookup"><span data-stu-id="364fe-258">In the past, PowerShell shipped a function on Windows called `more` that wrapped `more.com`.</span></span> <span data-ttu-id="364fe-259">この関数は削除されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-259">That function has now been removed.</span></span>

<span data-ttu-id="364fe-260">また、`help` 関数が変更され、Windows では `more.com` を、Windows 以外のプラットフォームでは `$env:PAGER` で指定されたシステムの既定のページャーを使用するようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-260">Also, the `help` function changed to use `more.com` on Windows, or the system's default pager specified by `$env:PAGER` on non-Windows platforms.</span></span>

### <a name="cd-drivename-now-returns-users-to-the-current-working-directory-in-that-drive"></a><span data-ttu-id="364fe-261">`cd DriveName:` では、そのドライブの現在の作業ディレクトリに戻るようになりました</span><span class="sxs-lookup"><span data-stu-id="364fe-261">`cd DriveName:` now returns users to the current working directory in that drive</span></span>

<span data-ttu-id="364fe-262">以前は、`Set-Location` または `cd` を使用して PSDrive に戻ると、ユーザーはそのドライブの既定の場所に送られました。</span><span class="sxs-lookup"><span data-stu-id="364fe-262">Previously, using `Set-Location` or `cd` to return to a PSDrive sent users to the default location for that drive.</span></span>

<span data-ttu-id="364fe-263">[@mcbobke](https://github.com/mcbobke) のおかげで、ユーザーはそのセッションで最後に認識された現在の作業ディレクトリに送られるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-263">Thanks to [@mcbobke](https://github.com/mcbobke), users are now sent to the last known current working directory for that session.</span></span>

### <a name="windows-powershell-type-accelerators"></a><span data-ttu-id="364fe-264">Windows PowerShell の型アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="364fe-264">Windows PowerShell type accelerators</span></span>

<span data-ttu-id="364fe-265">Windows PowerShell では、以下の型アクセラレータが追加されて、それぞれの型を使いやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-265">In Windows PowerShell, we included the following type accelerators to make it easier to work with their respective types:</span></span>

- <span data-ttu-id="364fe-266">`[adsi]`: `System.DirectoryServices.DirectoryEntry`</span><span class="sxs-lookup"><span data-stu-id="364fe-266">`[adsi]`: `System.DirectoryServices.DirectoryEntry`</span></span>
- <span data-ttu-id="364fe-267">`[adsisearcher]`: `System.DirectoryServices.DirectorySearcher`</span><span class="sxs-lookup"><span data-stu-id="364fe-267">`[adsisearcher]`: `System.DirectoryServices.DirectorySearcher`</span></span>
- <span data-ttu-id="364fe-268">`[wmi]`: `System.Management.ManagementObject`</span><span class="sxs-lookup"><span data-stu-id="364fe-268">`[wmi]`: `System.Management.ManagementObject`</span></span>
- <span data-ttu-id="364fe-269">`[wmiclass]`: `System.Management.ManagementClass`</span><span class="sxs-lookup"><span data-stu-id="364fe-269">`[wmiclass]`: `System.Management.ManagementClass`</span></span>
- <span data-ttu-id="364fe-270">`[wmisearcher]`: `System.Management.ManagementObjectSearcher`</span><span class="sxs-lookup"><span data-stu-id="364fe-270">`[wmisearcher]`: `System.Management.ManagementObjectSearcher`</span></span>

<span data-ttu-id="364fe-271">これらの型アクセラレータは、PowerShell 6 には含まれませんでしたが、Windows で実行される PowerShell 6.1 には追加されています。</span><span class="sxs-lookup"><span data-stu-id="364fe-271">These type accelerators were not included in PowerShell 6, but have been added to PowerShell 6.1 running on Windows.</span></span>

<span data-ttu-id="364fe-272">これらの型は、AD および WMI オブジェクトを簡単に構築するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="364fe-272">These types are useful in easily constructing AD and WMI objects.</span></span>

<span data-ttu-id="364fe-273">たとえば、LDAP を使用してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="364fe-273">For example, you can query using LDAP:</span></span>

```powershell
[adsi]'LDAP://CN=FooUse,OU=People,DC=contoso,DC=com'
```

<span data-ttu-id="364fe-274">次の例では、Win32_OperatingSystem CIM オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="364fe-274">Following example creates a Win32_OperatingSystem CIM object:</span></span>

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

<span data-ttu-id="364fe-275">この例では、Win32_OperatingSystem クラスの ManagementClass オブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="364fe-275">This example returns a ManagementClass object for Win32_OperatingSystem class.</span></span>

```powershell
[wmiclass]"Win32_OperatingSystem"
```

```Output
   NameSpace: ROOT\cimv2

Name                                Methods              Properties
----                                -------              ----------
Win32_OperatingSystem               {Reboot, Shutdown... {BootDevice, BuildNumber, BuildType, Caption...}
```

### <a name="-lp-alias-for-all--literalpath-parameters"></a><span data-ttu-id="364fe-276">すべての `-LiteralPath` パラメーターに対する `-lp` エイリアス</span><span class="sxs-lookup"><span data-stu-id="364fe-276">`-lp` alias for all `-LiteralPath` parameters</span></span>

<span data-ttu-id="364fe-277">[@kvprasoon](https://github.com/kvprasoon) のおかげで、`-lp` パラメーターがあるすべての組み込み PowerShell コマンドレットに対し、パラメーター エイリアス `-LiteralPath` が追加されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-277">Thanks to [@kvprasoon](https://github.com/kvprasoon), we now have a parameter alias `-lp` for all the built-in PowerShell cmdlets that have a `-LiteralPath` parameter.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="364fe-278">重大な変更</span><span class="sxs-lookup"><span data-stu-id="364fe-278">Breaking Changes</span></span>

### <a name="msi-based-installation-paths-on-windows"></a><span data-ttu-id="364fe-279">Windows での MSI ベースのインストール パス</span><span class="sxs-lookup"><span data-stu-id="364fe-279">MSI-based installation paths on Windows</span></span>

<span data-ttu-id="364fe-280">Windows では、MSI パッケージは次のパスにインストールされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-280">On Windows, the MSI package now installs to the following path:</span></span>

- <span data-ttu-id="364fe-281">`$env:ProgramFiles\PowerShell\6\`: 6.x の安定したインストールの場合</span><span class="sxs-lookup"><span data-stu-id="364fe-281">`$env:ProgramFiles\PowerShell\6\` for the stable installation of 6.x</span></span>
- <span data-ttu-id="364fe-282">`$env:ProgramFiles\PowerShell\6-preview\`: 6.x のプレビュー インストールの場合</span><span class="sxs-lookup"><span data-stu-id="364fe-282">`$env:ProgramFiles\PowerShell\6-preview\` for the preview installation of 6.x</span></span>

<span data-ttu-id="364fe-283">この変更により、Microsoft Update で PowerShell Core を更新/保守できるようになります。</span><span class="sxs-lookup"><span data-stu-id="364fe-283">This change ensures that PowerShell Core can be updated/serviced by Microsoft Update.</span></span>

<span data-ttu-id="364fe-284">詳しくは、[PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-284">For more information, check out [PowerShell RFC0026](https://github.com/PowerShell/PowerShell-RFC/blob/master/5-Final/RFC0026-MSI-Installation-Path.md).</span></span>

### <a name="telemetry-can-only-be-disabled-with-an-environment-variable"></a><span data-ttu-id="364fe-285">テレメトリは環境変数でのみ無効にできる</span><span class="sxs-lookup"><span data-stu-id="364fe-285">Telemetry can only be disabled with an environment variable</span></span>

<span data-ttu-id="364fe-286">PowerShell Core は、起動されると基本的なテレメトリ データを Microsoft に送信します。</span><span class="sxs-lookup"><span data-stu-id="364fe-286">PowerShell Core sends basic telemetry data to Microsoft when it is launched.</span></span> <span data-ttu-id="364fe-287">データには、OS 名、OS バージョン、および PowerShell のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="364fe-287">The data includes the OS name, OS version, and PowerShell version.</span></span> <span data-ttu-id="364fe-288">このデータにより、PowerShell が使用されている環境をより深く理解し、新機能と修正の優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="364fe-288">This data allows us to better understand the environments where PowerShell is used and enables us to prioritize new features and fixes.</span></span>

<span data-ttu-id="364fe-289">このテレメトリを無効にするには、環境変数 `POWERSHELL_TELEMETRY_OPTOUT` を `true`、`yes`、または `1` に設定します。</span><span class="sxs-lookup"><span data-stu-id="364fe-289">To opt-out of this telemetry, set the environment variable `POWERSHELL_TELEMETRY_OPTOUT` to `true`, `yes`, or `1`.</span></span> <span data-ttu-id="364fe-290">ファイル `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` を削除することによるテレメトリの無効化はサポートされなくなっています。</span><span class="sxs-lookup"><span data-stu-id="364fe-290">We no longer support deletion of the file `DELETE_ME_TO_DISABLE_CONSOLEHOST_TELEMETRY` to disable telemetry.</span></span>

### <a name="disallowed-basic-auth-over-http-in-powershell-remoting-on-unix-platforms"></a><span data-ttu-id="364fe-291">Unix プラットフォーム上の PowerShell リモート処理での HTTP による基本認証が許可されなくなった</span><span class="sxs-lookup"><span data-stu-id="364fe-291">Disallowed Basic Auth over HTTP in PowerShell Remoting on Unix platforms</span></span>

<span data-ttu-id="364fe-292">暗号化されていないトラフィックの使用を防ぐため、Unix プラットフォーム上の PowerShell リモート処理では、NTLM/ネゴシエートまたは HTTPS を使用することが必要になりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-292">To prevent the use of unencrypted traffic, PowerShell Remoting on Unix platforms now requires usage of NTLM/Negotiate or HTTPS.</span></span>

<span data-ttu-id="364fe-293">これらの変更について詳しくは、[Issue #6779](https://github.com/PowerShell/PowerShell/issues/6779) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-293">For more information on these changes, check out [Issue #6779](https://github.com/PowerShell/PowerShell/issues/6779).</span></span>

### <a name="removed-visualbasic-as-a-supported-language-in-add-type"></a><span data-ttu-id="364fe-294">Add-Type でサポートされる言語としての `VisualBasic` の削除</span><span class="sxs-lookup"><span data-stu-id="364fe-294">Removed `VisualBasic` as a supported language in Add-Type</span></span>

<span data-ttu-id="364fe-295">これまでは、`Add-Type` コマンドレットを使用して Visual Basic コードをコンパイルできました。</span><span class="sxs-lookup"><span data-stu-id="364fe-295">In the past, you could compile Visual Basic code using the `Add-Type` cmdlet.</span></span> <span data-ttu-id="364fe-296">Visual Basic は `Add-Type` ではほとんど使用されませんでした。</span><span class="sxs-lookup"><span data-stu-id="364fe-296">Visual Basic was rarely used with `Add-Type`.</span></span> <span data-ttu-id="364fe-297">この機能を削除して、PowerShell のサイズを小さくしました。</span><span class="sxs-lookup"><span data-stu-id="364fe-297">We removed this feature to reduce the size of PowerShell.</span></span>

### <a name="cleaned-up-uses-of-commandtypesworkflow-and-workflowinfocleaned"></a><span data-ttu-id="364fe-298">`CommandTypes.Workflow` および `WorkflowInfoCleaned` の使用のクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="364fe-298">Cleaned up uses of `CommandTypes.Workflow` and `WorkflowInfoCleaned`</span></span>

<span data-ttu-id="364fe-299">これらの変更について詳しくは、[PR #6708](https://github.com/PowerShell/PowerShell/pull/6708) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-299">For more information on these changes, check out [PR #6708](https://github.com/PowerShell/PowerShell/pull/6708).</span></span>

### <a name="group-object-now-sorts-the-groups"></a><span data-ttu-id="364fe-300">Group-Object でのグループの並べ替え</span><span class="sxs-lookup"><span data-stu-id="364fe-300">Group-Object now sorts the groups</span></span>

<span data-ttu-id="364fe-301">パフォーマンス向上の一環として、`Group-Object` でグループの並び替えられた一覧が返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="364fe-301">As part of the performance improvement, `Group-Object` now returns a sorted listing of the groups.</span></span>
<span data-ttu-id="364fe-302">順序に依存すべきではありませんが、最初のグループを必要としていた場合、この変更が破壊的になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="364fe-302">Although you should not rely on the order, you could be broken by this change if you wanted the first group.</span></span> <span data-ttu-id="364fe-303">以前の動作に依存することの影響は低いため、このパフォーマンス向上には変更するだけの価値があると判断されました。</span><span class="sxs-lookup"><span data-stu-id="364fe-303">We decided that this performance improvement was worth the change since the impact of being dependent on previous behavior is low.</span></span>

<span data-ttu-id="364fe-304">この変更の詳細については、[問題 #7409](https://github.com/PowerShell/PowerShell/issues/7409) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="364fe-304">For more information on this change, see [Issue #7409](https://github.com/PowerShell/PowerShell/issues/7409).</span></span>

<!-- URL references -->
[試験的機能]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
