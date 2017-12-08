---
title: "WMF 5.1 のコンソール機能強化"
ms.date: 2016-07-13
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: fc0c78f59a2c4cda5c6aad625a5eaf5121485bad
ms.sourcegitcommit: 26f4e52f3dd008b51b7eae7b634f0216eec6200e
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="console-improvements-in-wmf-51"></a><span data-ttu-id="fceda-103">WMF 5.1 のコンソール機能強化</span><span class="sxs-lookup"><span data-stu-id="fceda-103">Console Improvements in WMF 5.1</span></span>#

## <a name="powershell-console-improvements"></a><span data-ttu-id="fceda-104">PowerShell コンソールの機能強化</span><span class="sxs-lookup"><span data-stu-id="fceda-104">PowerShell console improvements</span></span>

<span data-ttu-id="fceda-105">コンソールのエクスペリエンスを改善するため、WMF 5.1 の powershell.exe が次のように変更されました。</span><span class="sxs-lookup"><span data-stu-id="fceda-105">The following changes have been made to powershell.exe in WMF 5.1 to improve the console experience:</span></span>

###<a name="vt100-support"></a><span data-ttu-id="fceda-106">VT100 のサポート</span><span class="sxs-lookup"><span data-stu-id="fceda-106">VT100 support</span></span>

<span data-ttu-id="fceda-107">Windows 10 では、[VT100 エスケープ シーケンス](https://msdn.microsoft.com/en-us/library/windows/desktop/mt638032(v=vs.85).aspx)のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="fceda-107">Windows 10 added support for [VT100 escape sequences](https://msdn.microsoft.com/en-us/library/windows/desktop/mt638032(v=vs.85).aspx).</span></span>
<span data-ttu-id="fceda-108">PowerShell は、テーブルの幅を計算するとき、特定の VT100 書式指定エスケープ シーケンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="fceda-108">PowerShell will ignore certain VT100 formatting escape sequences when calculating table widths.</span></span>

<span data-ttu-id="fceda-109">また、PowerShell に追加された新しい API を書式指定コードで使用すると、VT100 がサポートされているかどうかを判定できます。</span><span class="sxs-lookup"><span data-stu-id="fceda-109">PowerShell also added a new API that can be used in formatting code to determine if VT100 is supported.</span></span> <span data-ttu-id="fceda-110">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fceda-110">For example:</span></span>

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
<span data-ttu-id="fceda-111">これは、Select-String からの一致を強調表示するために使用できる完全な[例](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7)です。</span><span class="sxs-lookup"><span data-stu-id="fceda-111">Here is a complete [example](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) that can be used to highlight matches from Select-String.</span></span>
<span data-ttu-id="fceda-112">例を `MatchInfo.format.ps1xml` という名前のファイルに保存した後、使用するには、プロファイルまたはその他の場所で、`Update-FormatData -Prepend MatchInfo.format.ps1xml` を実行します。</span><span class="sxs-lookup"><span data-stu-id="fceda-112">Save the example in a file named `MatchInfo.format.ps1xml`, then to use it, in your profile or elsewhere, run `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span></span>

<span data-ttu-id="fceda-113">VT100 エスケープ シーケンスは、Windows 10 Anniversary 更新以降でのみサポートされることに注意してください。それより前のシステムではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="fceda-113">Note that VT100 escape sequences are only supported starting with the Windows 10 Anniversary update; they are not supported on earlier systems.</span></span>   

### <a name="vi-mode-support-in-psreadline"></a><span data-ttu-id="fceda-114">PSReadline での vi モードのサポート</span><span class="sxs-lookup"><span data-stu-id="fceda-114">Vi mode support in PSReadline</span></span>

<span data-ttu-id="fceda-115">[PSReadline](https://github.com/lzybkr/PSReadLine) は、vi モードのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="fceda-115">[PSReadline](https://github.com/lzybkr/PSReadLine) adds support for vi mode.</span></span> <span data-ttu-id="fceda-116">vi モードを使用するには、`Set-PSReadlineOption -EditMode Vi` を実行します。</span><span class="sxs-lookup"><span data-stu-id="fceda-116">To use vi mode, run `Set-PSReadlineOption -EditMode Vi`.</span></span>

### <a name="redirected-stdin-with-interactive-input"></a><span data-ttu-id="fceda-117">対話型の入力を使用する stdin のリダイレクト</span><span class="sxs-lookup"><span data-stu-id="fceda-117">Redirected stdin with interactive input</span></span> 

<span data-ttu-id="fceda-118">以前のバージョンでは、stdin がリダイレクトされ、コマンドを対話的に入力するときは、PowerShell を `powershell -File -` で起動する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="fceda-118">In earlier versions, starting PowerShell with `powershell -File -` was required when stdin was redirected and you wanted to enter commands interactively.</span></span>

<span data-ttu-id="fceda-119">WMF 5.1 では、この見つけにくいオプションは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="fceda-119">With WMF 5.1, this hard to discover option is no longer necessary.</span></span> <span data-ttu-id="fceda-120">`powershell` のようなオプションを何も使わずに PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="fceda-120">You can start PowerShell without any options, e.g. `powershell`.</span></span>

<span data-ttu-id="fceda-121">PSReadline は現在はリダイレクトされた stdin をサポートせず、リダイレクトされた stdin での組み込みコマンド ライン編集エクスペリエンスは非常に限られたものであることに注意してください (たとえば、方向キーは機能しません)。</span><span class="sxs-lookup"><span data-stu-id="fceda-121">Note that PSReadline does not currently support redirected stdin, and the built-in command-line editing experience with redirected stdin is extremely limited, for example, arrow keys don't work.</span></span> <span data-ttu-id="fceda-122">PSReadline の将来のリリースではこの問題が対処されるはずです。</span><span class="sxs-lookup"><span data-stu-id="fceda-122">A future release of PSReadline should address this issue.</span></span>   
