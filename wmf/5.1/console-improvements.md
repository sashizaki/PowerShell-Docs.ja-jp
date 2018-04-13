---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 のコンソール機能強化
ms.openlocfilehash: 2abc02010c6c1d9f7fc617e9831b2d1243e0a3ee
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="console-improvements-in-wmf-51"></a><span data-ttu-id="d4ba9-103">WMF 5.1# のコンソール機能強化</span><span class="sxs-lookup"><span data-stu-id="d4ba9-103">Console Improvements in WMF 5.1#</span></span>

## <a name="powershell-console-improvements"></a><span data-ttu-id="d4ba9-104">PowerShell コンソールの機能強化</span><span class="sxs-lookup"><span data-stu-id="d4ba9-104">PowerShell console improvements</span></span>

<span data-ttu-id="d4ba9-105">コンソールのエクスペリエンスを改善するため、WMF 5.1 の powershell.exe が次のように変更されました。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-105">The following changes have been made to powershell.exe in WMF 5.1 to improve the console experience:</span></span>

###<a name="vt100-support"></a><span data-ttu-id="d4ba9-106">VT100 のサポート</span><span class="sxs-lookup"><span data-stu-id="d4ba9-106">VT100 support</span></span>

<span data-ttu-id="d4ba9-107">Windows 10 では、[VT100 エスケープ シーケンス](https://msdn.microsoft.com/en-us/library/windows/desktop/mt638032(v=vs.85).aspx)のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-107">Windows 10 added support for [VT100 escape sequences](https://msdn.microsoft.com/en-us/library/windows/desktop/mt638032(v=vs.85).aspx).</span></span>
<span data-ttu-id="d4ba9-108">PowerShell は、テーブルの幅を計算するとき、特定の VT100 書式指定エスケープ シーケンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-108">PowerShell will ignore certain VT100 formatting escape sequences when calculating table widths.</span></span>

<span data-ttu-id="d4ba9-109">また、PowerShell に追加された新しい API を書式指定コードで使用すると、VT100 がサポートされているかどうかを判定できます。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-109">PowerShell also added a new API that can be used in formatting code to determine if VT100 is supported.</span></span>
<span data-ttu-id="d4ba9-110">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-110">For example:</span></span>

```
if ($host.UI.SupportsVirtualTerminal)
{
    $esc = [char]0x1b
    "A yellow ${esc}[93mhello${esc}[0m"
}
else
{
    "A default hello"
}
```
<span data-ttu-id="d4ba9-111">これは、Select-String からの一致を強調表示するために使用できる完全な[例](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7)です。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-111">Here is a complete [example](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) that can be used to highlight matches from Select-String.</span></span>
<span data-ttu-id="d4ba9-112">例を `MatchInfo.format.ps1xml` という名前のファイルに保存した後、使用するには、プロファイルまたはその他の場所で、`Update-FormatData -Prepend MatchInfo.format.ps1xml` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-112">Save the example in a file named `MatchInfo.format.ps1xml`, then to use it, in your profile or elsewhere, run `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span></span>

<span data-ttu-id="d4ba9-113">VT100 エスケープ シーケンスは、Windows 10 Anniversary 更新以降でのみサポートされることに注意してください。それより前のシステムではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-113">Note that VT100 escape sequences are only supported starting with the Windows 10 Anniversary update; they are not supported on earlier systems.</span></span>

### <a name="vi-mode-support-in-psreadline"></a><span data-ttu-id="d4ba9-114">PSReadline での vi モードのサポート</span><span class="sxs-lookup"><span data-stu-id="d4ba9-114">Vi mode support in PSReadline</span></span>

<span data-ttu-id="d4ba9-115">[PSReadline](https://github.com/lzybkr/PSReadLine) は、vi モードのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-115">[PSReadline](https://github.com/lzybkr/PSReadLine) adds support for vi mode.</span></span> <span data-ttu-id="d4ba9-116">vi モードを使用するには、`Set-PSReadlineOption -EditMode Vi` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-116">To use vi mode, run `Set-PSReadlineOption -EditMode Vi`.</span></span>

### <a name="redirected-stdin-with-interactive-input"></a><span data-ttu-id="d4ba9-117">対話型の入力を使用する stdin のリダイレクト</span><span class="sxs-lookup"><span data-stu-id="d4ba9-117">Redirected stdin with interactive input</span></span>

<span data-ttu-id="d4ba9-118">以前のバージョンでは、stdin がリダイレクトされ、コマンドを対話的に入力するときは、PowerShell を `powershell -File -` で起動する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-118">In earlier versions, starting PowerShell with `powershell -File -` was required when stdin was redirected and you wanted to enter commands interactively.</span></span>

<span data-ttu-id="d4ba9-119">WMF 5.1 では、この見つけにくいオプションは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-119">With WMF 5.1, this hard to discover option is no longer necessary.</span></span>
<span data-ttu-id="d4ba9-120">`powershell` のようなオプションを何も使わずに PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-120">You can start PowerShell without any options, e.g. `powershell`.</span></span>

<span data-ttu-id="d4ba9-121">PSReadline は現在はリダイレクトされた stdin をサポートせず、リダイレクトされた stdin での組み込みコマンド ライン編集エクスペリエンスは非常に限られたものであることに注意してください (たとえば、方向キーは機能しません)。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-121">Note that PSReadline does not currently support redirected stdin, and the built-in command-line editing experience with redirected stdin is extremely limited, for example, arrow keys don't work.</span></span>
<span data-ttu-id="d4ba9-122">PSReadline の将来のリリースではこの問題が対処されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d4ba9-122">A future release of PSReadline should address this issue.</span></span>