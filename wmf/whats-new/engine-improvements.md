---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の PowerShell エンジン機能強化
ms.openlocfilehash: a0af702832c0a90c994650e25918ecacdc33fc4b
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855457"
---
# <a name="powershell-engine-improvements"></a><span data-ttu-id="26fc7-103">PowerShell エンジンの機能強化</span><span class="sxs-lookup"><span data-stu-id="26fc7-103">PowerShell Engine Improvements</span></span>

<span data-ttu-id="26fc7-104">コア PowerShell エンジンに対する以下の機能強化が WMF 5.1 に実装されました。</span><span class="sxs-lookup"><span data-stu-id="26fc7-104">The following improvements to the core PowerShell engine have been implemented in WMF 5.1:</span></span>

## <a name="performance"></a><span data-ttu-id="26fc7-105">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="26fc7-105">Performance</span></span>

<span data-ttu-id="26fc7-106">いくつかの重要な部分でパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="26fc7-106">Performance has improved in some important areas:</span></span>

- <span data-ttu-id="26fc7-107">起動</span><span class="sxs-lookup"><span data-stu-id="26fc7-107">Startup</span></span>
- <span data-ttu-id="26fc7-108">`ForEach-Object` や `Where-Object` などのコマンドレットに対するパイプライン処理が、約 50% 速くなりました</span><span class="sxs-lookup"><span data-stu-id="26fc7-108">Pipelining to cmdlets like `ForEach-Object` and `Where-Object` is approximately 50% faster</span></span>

<span data-ttu-id="26fc7-109">機能強化の例をいくつか示します (結果はハードウェアによって異なる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="26fc7-109">Some example improvements (your results may vary depending on your hardware):</span></span>

| <span data-ttu-id="26fc7-110">シナリオ</span><span class="sxs-lookup"><span data-stu-id="26fc7-110">Scenario</span></span> | <span data-ttu-id="26fc7-111">5.0 の時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="26fc7-111">5.0 Time (ms)</span></span> | <span data-ttu-id="26fc7-112">5.1 の時間 (ミリ秒)</span><span class="sxs-lookup"><span data-stu-id="26fc7-112">5.1 Time (ms)</span></span> |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | <span data-ttu-id="26fc7-113">900</span><span class="sxs-lookup"><span data-stu-id="26fc7-113">900</span></span> | <span data-ttu-id="26fc7-114">250</span><span class="sxs-lookup"><span data-stu-id="26fc7-114">250</span></span> |
| <span data-ttu-id="26fc7-115">PowerShell の初めての実行: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="26fc7-115">First ever PowerShell run: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="26fc7-116">30000</span><span class="sxs-lookup"><span data-stu-id="26fc7-116">30000</span></span> | <span data-ttu-id="26fc7-117">13000</span><span class="sxs-lookup"><span data-stu-id="26fc7-117">13000</span></span> |
| <span data-ttu-id="26fc7-118">コマンド分析キャッシュの構築: `powershell -command "Unknown-Command"`</span><span class="sxs-lookup"><span data-stu-id="26fc7-118">Command analysis cache built: `powershell -command "Unknown-Command"`</span></span> | <span data-ttu-id="26fc7-119">7000</span><span class="sxs-lookup"><span data-stu-id="26fc7-119">7000</span></span> | <span data-ttu-id="26fc7-120">520</span><span class="sxs-lookup"><span data-stu-id="26fc7-120">520</span></span> |
| <code>1..1000000 &#124; % { }</code> | <span data-ttu-id="26fc7-121">1400</span><span class="sxs-lookup"><span data-stu-id="26fc7-121">1400</span></span> | <span data-ttu-id="26fc7-122">750</span><span class="sxs-lookup"><span data-stu-id="26fc7-122">750</span></span> |

> [!NOTE]
> <span data-ttu-id="26fc7-123">起動に関連する 1 つの変更が、一部のサポートされていないシナリオに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26fc7-123">One change related to startup might impact some unsupported scenarios.</span></span> <span data-ttu-id="26fc7-124">PowerShell は `$pshome\*.ps1xml` ファイルを読み込まなくなりました。これらのファイルは、XML ファイルの処理でファイルと CPU にオーバーヘッドが発生しないよう、C# に変換されています。</span><span class="sxs-lookup"><span data-stu-id="26fc7-124">PowerShell no longer reads the files `$pshome\*.ps1xml` -- these files have been converted to C# to avoid some file and CPU overhead of processing the XML files.</span></span> <span data-ttu-id="26fc7-125">これらのファイルは V2 のサイド バイ サイド インストールをサポートするためにまだ存在するので、ファイルの内容を変更した場合、V5 には影響がなく、影響を受けるのは V2 だけです。</span><span class="sxs-lookup"><span data-stu-id="26fc7-125">The files still exist to support V2 side-by-side, so if you change the file contents, it will not have any effect to V5, only V2.</span></span> <span data-ttu-id="26fc7-126">これらのファイルの内容を変更するシナリオはサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="26fc7-126">Note that changing the contents of these files was never a supported scenario.</span></span>

<span data-ttu-id="26fc7-127">もう 1 つの明らかな変更は、システムにインストールされているモジュールのために PowerShell がエクスポートしたコマンドと他の情報をキャッシュするしくみです。</span><span class="sxs-lookup"><span data-stu-id="26fc7-127">Another visible change is how PowerShell caches the exported commands and other information for modules that are installed on a system.</span></span> <span data-ttu-id="26fc7-128">これまでは、このキャッシュは `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis` ディレクトリに保存されていました。</span><span class="sxs-lookup"><span data-stu-id="26fc7-128">Previously, this cache was stored in the directory `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`.</span></span> <span data-ttu-id="26fc7-129">WMF 5.1 では、キャッシュは `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイル 1 つだけになっています。</span><span class="sxs-lookup"><span data-stu-id="26fc7-129">In WMF 5.1, the cache is a single file `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="26fc7-130">詳細については、「[モジュール分析キャッシュ](release-notes.md#module-analysis-cache)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26fc7-130">See [Module Analysis Cache](release-notes.md#module-analysis-cache) for more details.</span></span>