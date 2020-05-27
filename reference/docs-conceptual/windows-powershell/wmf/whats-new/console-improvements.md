---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 のコンソール機能強化
ms.openlocfilehash: ae3d08a34a09bc32d40a8a45788999ee9c54a562
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808988"
---
# <a name="console-improvements-in-wmf-51"></a><span data-ttu-id="d11d8-103">WMF 5.1 のコンソール機能強化</span><span class="sxs-lookup"><span data-stu-id="d11d8-103">Console Improvements in WMF 5.1</span></span>

## <a name="powershell-console-improvements"></a><span data-ttu-id="d11d8-104">PowerShell コンソールの機能強化</span><span class="sxs-lookup"><span data-stu-id="d11d8-104">PowerShell console improvements</span></span>

<span data-ttu-id="d11d8-105">コンソールのエクスペリエンスを改善するため、WMF 5.1 の powershell.exe が次のように変更されました。</span><span class="sxs-lookup"><span data-stu-id="d11d8-105">The following changes have been made to powershell.exe in WMF 5.1 to improve the console experience:</span></span>

### <a name="vt100-support"></a><span data-ttu-id="d11d8-106">VT100 のサポート</span><span class="sxs-lookup"><span data-stu-id="d11d8-106">VT100 support</span></span>

<span data-ttu-id="d11d8-107">Windows 10 では、[VT100 エスケープ シーケンス](/windows/console/console-virtual-terminal-sequences)のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="d11d8-107">Windows 10 added support for [VT100 escape sequences](/windows/console/console-virtual-terminal-sequences).</span></span>
<span data-ttu-id="d11d8-108">PowerShell は、テーブルの幅を計算するとき、特定の VT100 書式指定エスケープ シーケンスを無視します。</span><span class="sxs-lookup"><span data-stu-id="d11d8-108">PowerShell will ignore certain VT100 formatting escape sequences when calculating table widths.</span></span>

<span data-ttu-id="d11d8-109">また、PowerShell に追加された新しい API を書式指定コードで使用すると、VT100 がサポートされているかどうかを判定できます。</span><span class="sxs-lookup"><span data-stu-id="d11d8-109">PowerShell also added a new API that can be used in formatting code to determine if VT100 is supported.</span></span> <span data-ttu-id="d11d8-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d11d8-110">For example:</span></span>

```powershell
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

<span data-ttu-id="d11d8-111">これは、[ からの一致を強調表示するために使用できる完全な](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7)例`Select-String`です。</span><span class="sxs-lookup"><span data-stu-id="d11d8-111">Here is a complete [example](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7) that can be used to highlight matches from `Select-String`.</span></span> <span data-ttu-id="d11d8-112">例を `MatchInfo.format.ps1xml` という名前のファイルに保存した後、使用するには、プロファイルまたはその他の場所で、`Update-FormatData -Prepend MatchInfo.format.ps1xml` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d11d8-112">Save the example in a file named `MatchInfo.format.ps1xml`, then to use it, in your profile or elsewhere, run `Update-FormatData -Prepend MatchInfo.format.ps1xml`.</span></span>

<span data-ttu-id="d11d8-113">VT100 エスケープ シーケンスは、Windows 10 Anniversary Update 以降でのみサポートされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d11d8-113">Note that VT100 escape sequences are only supported starting with the Windows 10 Anniversary update.</span></span>
<span data-ttu-id="d11d8-114">それより前のシステムではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="d11d8-114">They are not supported on earlier systems.</span></span>

### <a name="vi-mode-support-in-psreadline"></a><span data-ttu-id="d11d8-115">PSReadline での vi モードのサポート</span><span class="sxs-lookup"><span data-stu-id="d11d8-115">Vi mode support in PSReadline</span></span>

<span data-ttu-id="d11d8-116">[PSReadline](https://github.com/PowerShell/PSReadLine) は、vi モードのサポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="d11d8-116">[PSReadline](https://github.com/PowerShell/PSReadLine) adds support for vi mode.</span></span> <span data-ttu-id="d11d8-117">vi モードを使用するには、`Set-PSReadlineOption -EditMode Vi` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d11d8-117">To use vi mode, run `Set-PSReadlineOption -EditMode Vi`.</span></span>

### <a name="redirected-stdin-with-interactive-input"></a><span data-ttu-id="d11d8-118">対話型の入力を使用する stdin のリダイレクト</span><span class="sxs-lookup"><span data-stu-id="d11d8-118">Redirected stdin with interactive input</span></span>

<span data-ttu-id="d11d8-119">以前のバージョンでは、stdin がリダイレクトされ、コマンドを対話的に入力するときは、PowerShell を `powershell -File -` で起動する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d11d8-119">In earlier versions, starting PowerShell with `powershell -File -` was required when stdin was redirected and you wanted to enter commands interactively.</span></span>

<span data-ttu-id="d11d8-120">WMF 5.1 では、この見つけにくいオプションは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="d11d8-120">With WMF 5.1, this hard to discover option is no longer necessary.</span></span> <span data-ttu-id="d11d8-121">オプションを何も使わずに PowerShell を起動できます。</span><span class="sxs-lookup"><span data-stu-id="d11d8-121">You can start PowerShell without any options.</span></span>

<span data-ttu-id="d11d8-122">PSReadline ではリダイレクトされた stdin はサポートされておらず、リダイレクトされた stdin での組み込みコマンド ライン編集エクスペリエンスは、非常に限られたものであることに注意してください (たとえば、方向キーは機能しません)。</span><span class="sxs-lookup"><span data-stu-id="d11d8-122">Note that PSReadline does not support redirected stdin, and the built-in command-line editing experience with redirected stdin is extremely limited, for example, arrow keys don't work.</span></span> <span data-ttu-id="d11d8-123">PSReadline の将来のリリースではこの問題が対処されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d11d8-123">A future release of PSReadline should address this issue.</span></span>
